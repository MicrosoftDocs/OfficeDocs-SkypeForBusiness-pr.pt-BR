---
title: Configure o Skype for Business híbrido
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumo: saiba como configurar a interoperabilidade entre sua implantação local e o Skype for Business Online.'
ms.openlocfilehash: e2af514ef1a10d652abae7bdd39a923dc52e1c4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118940"
---
# <a name="configure-skype-for-business-hybrid"></a>Configure o Skype for Business híbrido

Para configurar o Skype for Business híbrido, você precisa:

- Configure seu serviço de Borda local para federar com [o Microsoft 365 ou o Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).
- Configure seu ambiente local para confiar [no Microsoft 365 ou Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)e habilitar o espaço de endereço SIP compartilhado.
- [Habilitar o espaço de endereço SIP compartilhado em sua organização do Microsoft 365 ou Office 365.](#enable-shared-sip-address-space-in-your-organization)

Observe que, se você tiver o Exchange local, talvez queira configurar o OAuth entre seus ambientes locais do Exchange e do Skype for Business Online. Para obter mais informações, consulte  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and Plan to integrate Skype for Business and [Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Configurar seu serviço de Borda local para federar com o Microsoft 365 ou o Office 365

A federação permite que os usuários em sua implantação local se comuniquem com usuários do Microsoft 365 ou Office 365 em sua organização. Para configurar a federação, execute o seguinte cmdlet no Shell de Gerenciamento do Skype for Business Server:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Se o valor '-EnablePartnerDiscovery' estiver definido como $True, o Skype for Business Server usará registros DNS para tentar descobrir domínios de parceiros não listados na lista AllowedDomains. Se o valor for definido como $False, o Skype for Business Server só se federará com domínios encontrados na lista AllowedDomains. Esse parâmetro é obrigatório caso se esteja utilizando o roteamento de serviço de DNS.

> [!NOTE]
> Para obter mais detalhes sobre como habilizar a federação entre usuários da implantação local do Skype for Business e usuários de uma organização do Skype for Business Online, consulte [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Configure seu ambiente local para habilitar o espaço de endereço SIP compartilhado com o Microsoft 365 ou o Office 365

Você também deve configurar seu ambiente local para confiar no Microsoft 365 ou Office 365 e habilitar o espaço de endereço SIP compartilhado. Isso significa que o Microsoft 365 ou o Office 365 podem potencialmente hospedar contas de usuário para o mesmo conjunto de domínios SIP do seu ambiente local, e as mensagens podem ser roteadas entre usuários hospedados no local e online.  Você faz isso configurando um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com conforme descrito abaixo.

Primeiro, verifique se você já tem um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com. Se houver um, remova-o usando o seguinte comando:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Em seguida, crie um novo provedor de hospedagem, use o cmdlet New-CsHostingProvider da seguinte forma: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Habilitar o espaço de endereço SIP compartilhado em sua organização
  
Além da alteração feita em sua implantação local, você precisará fazer a alteração correspondente em sua organização do Microsoft 365 ou office 365 para habilitar o espaço de endereço SIP compartilhado com sua implantação local.  

Para habilitar o espaço de endereço SIP compartilhado em sua organização, estabeleça uma sessão remota do PowerShell com o Skype for Business Online e execute o seguinte cmdlet:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> O atributo SharedSipAddressSpace precisa permanecer "True" até que a mudança para online seja final e nenhum usuário permaneça no local. 
  
Para estabelecer uma sessão remota do PowerShell com o Teams ou o Skype for Business Online, primeiro você precisa instalar o [módulo do Teams PowerShell.](/microsoftteams/teams-powershell-install)
  
Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Skype for Business Online e como usar o módulo conector do Skype for Business Online, consulte [Configurar](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)seu computador para Windows PowerShell .
  


## <a name="see-also"></a>Confira também

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)