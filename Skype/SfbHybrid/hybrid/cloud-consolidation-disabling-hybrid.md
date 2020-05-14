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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para desabilitar o híbrido como parte da consolidação em nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: a049491550ed26c61c587824034035a4c3a40a07
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221495"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Desabilitar a migração híbrida para concluir a nuvem

Depois de mover todos os usuários do local para a nuvem, você poderá desativar a implantação do Skype for Business local. Além de remover qualquer hardware, uma etapa crítica é separar logicamente a implantação local do Microsoft 365 ou do Office 365 desabilitando o híbrido. A desabilitação híbrida consiste em três etapas:

1. Atualizar registros DNS para apontar para o Microsoft 365 ou o Office 365.

2. Desabilite o domínio dividido na organização do Microsoft 365 ou do Office 365.

3. Desabilite a capacidade no local para se comunicar com o Microsoft 365 ou o Office 365.

Essas etapas devem ser feitas juntas como uma unidade. Os detalhes são fornecidos abaixo. Além disso, as diretrizes são fornecidas para o gerenciamento de números de telefone para usuários migrados depois que a implantação local é desconectada.

> [!Important] 
>Você deve continuar a permitir que os atributos do msRTCSIP no Active Directory sincronizem por meio do Azure AD Connect no Azure AD.  Não desmarque nenhum desses atributos, a menos que seja direcionado por suporte.  Não execute disable-CsUser no ambiente local. Se você precisar modificar o endereço SIP de um usuário, faça isso em seu Active Directory local e permita que essa alteração seja sincronizada no Azure AD por meio do Azure AD Connect, conforme descrito abaixo. Da mesma forma, se você precisar alterar um número de telefone e o LineURI do usuário já estiver definido no local, você deverá modificá-lo no Active Directory local.
>A limpeza dos atributos do msRTCSIP no local após a migração do local pode resultar em perda de serviço para usuários!

> [!Note] 
> Em casos raros, alterar o DNS de apontar para o local para o Microsoft 365 ou o Office 365 para sua organização pode fazer com que a Federação com algumas outras organizações pare de funcionar até que outra organização Atualize sua configuração de Federação:<ul><li>
Todas as organizações federadas que usam o modelo de Federação direta mais antigo (também conhecido como servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN do proxy. Esse modelo de Federação herdado não é baseado nos registros SRV DNS, portanto, essa configuração se tornará desatualizada quando sua organização for movida para a nuvem. </li><li>Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed. online. Lync. <span> com precisará atualizar sua configuração para habilitar isso. Essa situação só é possível se a organização federada estiver exclusivamente local e nunca federada com nenhum locatário híbrido ou online. Nesse caso, a Federação com essas organizações não funcionará até que o provedor de hospedagem seja habilitado.</li></ul>Se você suspeita que qualquer um dos seus parceiros federados pode usar Federação direta ou federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso ao se preparar para concluir a migração para a nuvem.

1.  *Atualize o DNS para apontar para o Microsoft 365 ou o Office 365.*
O DNS externo da organização para a organização local precisa ser atualizado para que os registros do Skype for Business apontem para o Microsoft 365 ou o Office 365 em vez da implantação local. Especificamente:

    |Tipo de registro|Nome|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls. _tcp|3600|100 1 5061 sipfed. online. Lync. <span> suplementos|
    |SRV|_sip. _tls|3600|100 1 443 sipdir. online. Lync. <span> suplementos|
    |CNAME| lyncdiscover|   3600|   Webdir. online. Lync. <span> suplementos|
    |CNAME| sip|    3600|   sipdir. online. Lync. <span> suplementos|
    |CNAME| cumpra|   3600|   Webdir. online. Lync. <span> suplementos|
    |CNAME| Dialin  |3600|  Webdir. online. Lync. <span> suplementos|

    Além disso, os registros CNAME para atender ou discar (se houver) podem ser excluídos. Por fim, os registros DNS do Skype for Business em sua rede interna devem ser removidos.

    > [!Note] 
    > Em casos raros, alterar o DNS de apontar para local para o Office 365 para sua organização pode fazer com que a Federação com algumas outras organizações pare de funcionar até que outra organização Atualize sua configuração de Federação:
    >
    > - Todas as organizações federadas que usam o modelo de Federação direta mais antigo (também conhecido como servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN do proxy. Esse modelo de Federação herdado não é baseado nos registros SRV DNS, portanto, essa configuração se tornará desatualizada quando sua organização for movida para a nuvem.
    > 
    > - Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed. online. Lync. <span> com precisará atualizar sua configuração para habilitar isso. Essa situação só é possível se a organização federada for puramente local e nunca federada com nenhum locatário híbrido ou online. Nesse caso, a Federação com essas organizações não funcionará até que o provedor de hospedagem seja habilitado.
    >
    > Se você suspeita que qualquer um dos seus parceiros federados pode estar usando a Federação direta ou não tenha federado com nenhuma organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso ao se preparar para concluir a migração para a nuvem.


2.  *Desabilitar o espaço de endereçamento SIP compartilhado no Microsoft 365 ou na organização do Office 365.*
O comando a seguir precisa ser feito de uma janela do PowerShell do Skype for Business online.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Desabilitar a capacidade no local para se comunicar com o Microsoft 365 ou o Office 365.*  
O comando abaixo precisa ser feito de uma janela do PowerShell local:

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Gerenciar endereços SIP e números de telefone para usuários que foram migrados do local

Os administradores podem gerenciar os usuários que foram movidos anteriormente de um Skype for Business Server local para a nuvem, mesmo depois que a implantação local é descomissionada. Se você quiser fazer alterações no endereço SIP de um usuário ou no URI da linha de um usuário (e o endereço SIP ou o URI da linha já estiver definido no Active Directory local), você deve fazer isso no Active Directory local e permitir que o (s) valor (es) flua para o Azure AD. Isso não requer o Skype for Business Server local. Em vez disso, você pode modificar esses atributos diretamente no Active Directory local, usando o snap-in usuários e computadores do Active Directory do MMC ou usando o PowerShell. Se você estiver usando o snap-in do MMC, abra a página de propriedades do usuário, clique na guia Editor de atributos e encontre os atributos apropriados para modificar:

- Para modificar o endereço SIP de um usuário, modifique o `msRTCSIP-PrimaryUserAddress` . Além disso, se o `ProxyAddresses` atributo contiver um valor SIP, atualize esse valor SIP para corresponder ao novo valor de `msRTCSIP-PrimaryUserAddress` . Se não contiver um valor SIP, você pode deixá-lo em branco.

- Para modificar o número de telefone de um usuário, modifique `msRTCSIP-Line` *se ele já tiver um valor*.

  ![Ferramenta usuários e computadores do Active Directory](../media/disable-hybrid-1.png)
  
Se o usuário não tiver originalmente um valor para `LineURI` o local antes da movimentação, você poderá modificar o LineURI usando o `onpremLineUri` parâmetro-CsUser no [cmdlet Set-](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) no módulo PowerShell do Skype for Business online.


## <a name="see-also"></a>Confira também

[Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)
