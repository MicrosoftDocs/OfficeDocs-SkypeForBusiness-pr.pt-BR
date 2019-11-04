---
title: Desabilitar a migração híbrida para concluir a nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para desabilitar o híbrido como parte da consolidação em nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: f78c5a5cb792ecdb39125292c531097219dc58e3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924962"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Desabilitar a migração híbrida para concluir a nuvem

Após mover todos os usuários do local para a nuvem, você poderá encerrar a implantação do Skype for Business local. Além de remover qualquer hardware, uma etapa crítica é separar logicamente a implantação local do Office 365 desabilitando o híbrido. A desabilitação híbrida consiste em três etapas:

1. Atualizar registros DNS para apontar para o Office 365.
2. Desabilitar o domínio de divisão no locatário do Office 365.
3. Desabilitar a capacidade no local para se comunicar com o Office 365.


Essas etapas devem ser feitas juntas como uma unidade. Os detalhes são fornecidos abaixo. Além disso, diretrizes para o gerenciamento de números de telefone para usuários migrados, quando a implantação local é desconectada.

> [!Note] 
> Em casos raros, alterar o DNS de apontar para local para o Office 365 para sua organização pode fazer com que a Federação com algumas outras organizações pare de funcionar até que outra organização Atualize sua configuração de Federação:<ul><li>
Todas as organizações federadas que usam o modelo de Federação direta mais antigo (também conhecido como servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN do proxy. Esse modelo de Federação herdado não é baseado nos registros SRV DNS, portanto, essa configuração se tornará desatualizada quando sua organização for movida para a nuvem. </li><li>Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed. online. Lync. <span>com precisará atualizar sua configuração para habilitar isso. Essa situação só é possível se a organização federada estiver exclusivamente local e nunca federada com nenhum locatário híbrido ou online. Nesse caso, a Federação com essas organizações não funcionará até que o provedor de hospedagem seja habilitado.</li></ul>Se você suspeita que qualquer um dos seus parceiros federados pode usar Federação direta ou federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso ao se preparar para concluir a migração para a nuvem.

1.  *Atualize o DNS para apontar para o Office 365.*
O DNS externo da organização para a organização local precisa ser atualizado para que os registros do Skype for Business apontem para o Office 365 em vez da implantação local. Especificamente:

    |Tipo de registro|Nome|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls. _ TCP|3600|100 1 5061 sipfed. online. Lync. <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir. online. Lync. <span>com|
    |CNAME| lyncdiscover|   3600|   Webdir. online. Lync. <span>com|
    |CNAME| sip|    3600|   sipdir. online. Lync. <span>com|
    |CNAME| cumpra|   3600|   Webdir. online. Lync. <span>com|
    |CNAME| Dialin  |3600|  Webdir. online. Lync. <span>com|

2.  *Desabilitar o espaço de endereçamento SIP compartilhado no locatário do Office 365.*
O comando a seguir precisa ser feito de uma janela do PowerShell do Skype for Business online.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Desabilitar a capacidade no local para se comunicar com o Office 365.*  
O comando a seguir precisa ser feito a partir de uma janela do PowerShell local.  Se você importou uma sessão do Skype for Business online anteriormente, inicie uma nova sessão do PowerShell do Skype for Business.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

### <a name="managing-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Gerenciando números de telefone para usuários que foram migrados do local

Os administradores podem gerenciar os usuários que foram movidos anteriormente do Skype for Business Server local para a nuvem, mesmo depois que a implantação local é encerrada. Há duas possibilidades diferentes:
1.  Se o usuário tivesse um lineURI local antes da movimentação (supostamente porque o usuário foi habilitado para o Enterprise Voice), se você quiser alterar o lineURI, deverá fazer isso no AD local e deixar o valor fluir até o AAD. Isso não requer o Skype for Business Server local. Em vez disso, esse atributo, msRTCSIP, pode ser editado diretamente no Active Directory local, usando o snap-in usuários e computadores do Active Directory, ou por meio do PowerShell. Se estiver usando o snap-in do MMC, abra a página de propriedades do usuário e clique na guia Editor de atributos e localize msRTCSIP-line.

2.  Se o usuário não tiver um valor para lineURI local antes da movimentação, você poderá modificar o LineURI usando os parâmetros-onpremLineUri no cmdlet Set-CsUser no módulo PowerShell do Skype for Business online.

## <a name="see-also"></a>Confira também

[Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)
