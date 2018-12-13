---
title: Desabilitar híbrido para concluir a migração para a nuvem
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui as etapas detalhadas para desativando híbrida como parte da consolidação de nuvem para equipes e Skype para negócios.
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247602"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Desabilitar híbrido para concluir a migração para a nuvem

Depois que tiver movido todos os usuários no local para a nuvem, você poderá encerrar o Skype local para implantação de negócios. Além dos removendo qualquer hardware, uma etapa importante é separar logicamente essa implantação local do Office 365, desativando híbrida. Desabilitando híbrida consiste em 3 etapas:

1. Atualize registros DNS para apontar para o Office 365.
2. Desabilite a divisão de domínios no Office 365 inquilino.
3. Desabilite a capacidade em prem de se comunicar com o Office 365.


Estas etapas devem ser feitas juntos como uma unidade. Detalhes são fornecidas abaixo.

> [!Note] 
> Em casos raros, a mudança do DNS de apontando no local para o Office 365 para sua organização pode causar federação com outras organizações parem de funcionar até que a outra organização atualiza sua configuração de Federação:<ul><li>
Qualquer organizações federadas que estiver usando o modelo de Federação direta mais antigo (também conhecido como servidor de parceiro permitido) serão necessário atualizar suas entradas de domínios permitidos para sua organização remover o FQDN do proxy. Este modelo de Federação herdada não é baseado em registros SRV de DNS, portanto, tal configuração se tornará desatualizada depois que a sua organização se move para a nuvem. </li><li>Qualquer organização federada que não tem um provedor de hospedagem habilitado para sipfed.online.lync. <span>com precisará atualizem sua configuração para permitir que. Essa situação é possível apenas se a organização federada é puramente no local e nunca tiver federado com qualquer híbrido ou Locatário online. Nesse caso, a federação com essas organizações não funcionará até que eles permitem que o seu provedor de hospedagem.</li></ul>Se você suspeitar de que qualquer um dos seus parceiros federados podem estar usando a federação direta ou tenham federado com qualquer online ou organização híbrida, sugerimos que você envia-lhes uma comunicação sobre isso conforme você prepara para completar sua migração para a nuvem.

1.  *Atualize o DNS para apontar para o Office 365.*
O DNS externo para a organização local da organização precisa ser atualizada para que Skype para registros de negócios apontem para o Office 365, em vez de implantação no local. Especificamente:

    |Tipo de registro|Nome|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span>com|
    |CNAME| lyncdiscover|   3600|   WebDir.online.Lync. <span>com|
    |CNAME| SIP|    3600|   sipdir.online.Lync. <span>com|
    |CNAME| reunir|   3600|   WebDir.online.Lync. <span>com|
    |CNAME| Dialin  |3600|  WebDir.online.Lync. <span>com|

2.  *Desabilite o espaço de endereçamento SIP compartilhado no locatário do Office 365.*
O comando a seguir deve ser feito a partir de um Skype para negócios Online PowerShell janela.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Desabilite a capacidade em prem de se comunicar com o Office 365.*  
O comando a seguir deve ser feito a partir de uma janela do PowerShell no local.  Se você importou anteriormente um Skype para sessão Business Online, inicie um novo Skype para a sessão do PowerShell de negócios.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>Consulte também

[Consolidação de nuvem para equipes e Skype para negócios](cloud-consolidation.md)