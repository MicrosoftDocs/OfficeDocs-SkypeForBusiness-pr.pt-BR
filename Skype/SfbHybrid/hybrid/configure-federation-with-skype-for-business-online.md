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
description: 'Resumo: saiba como configurar a interoperabilidade entre sua implantação local e Teams.'
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305965"
---
# <a name="configure-skype-for-business-hybrid"></a>Configure o Skype for Business híbrido

Para configurar o Skype for Business híbrido, você precisa:

- [Configure seu serviço de Borda local para federar com](#configure-your-on-premises-edge-service-to-federate-with-teams)Teams .
- [Configure seu ambiente local para confiar Teams e habilitar o espaço de endereço SIP compartilhado.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)
- [Habilitar o espaço de endereço SIP compartilhado em sua Teams organização](#enable-shared-sip-address-space-in-your-organization).

Se você tiver Exchange local, talvez queira configurar o OAuth entre seus ambientes Exchange local e Skype for Business Online. Para obter mais informações, consulte [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and Plan to integrate Skype for Business and [Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>Configure seu serviço de Borda local para federar com Teams

A federação permite que os usuários em sua implantação local se comuniquem com Teams e Skype for Business online em sua organização. Para configurar a federação, execute o seguinte cmdlet no Shell Skype for Business Server Gerenciamento:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Se o valor '-EnablePartnerDiscovery' estiver definido como $True, o Skype for Business Server usará registros DNS para tentar descobrir domínios de parceiros não listados na lista AllowedDomains. Se o valor for definido como $False , Skype for Business Server federará apenas com domínios encontrados na lista AllowedDomains. Esse parâmetro é obrigatório caso se esteja utilizando o roteamento de serviço de DNS.

> [!NOTE]
> Para obter mais detalhes sobre a habilitação da federação entre usuários de sua implantação Skype for Business local e usuários de uma organização Microsoft 365, consulte [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>Configure seu ambiente local para habilitar o espaço de endereço SIP compartilhado com Teams

Você também deve configurar seu ambiente local para confiar Teams e habilitar o espaço de endereço SIP compartilhado. Essa configuração significa Teams pode hospedar contas de usuário para o mesmo conjunto de domínios SIP do seu ambiente local, e as mensagens podem ser roteadas entre usuários hospedados no local e online. Você configura um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com conforme descrito abaixo.

Primeiro, verifique se você já tem um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com. Se existir um, remova-o usando o seguinte comando no Shell de Gerenciamento Skype for Business Server:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Em seguida, crie um novo provedor de hospedagem usando o cmdlet New-CsHostingProvider da seguinte forma: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Habilitar o espaço de endereço SIP compartilhado em sua organização
  
Além da alteração feita em sua implantação local, você precisará fazer a alteração correspondente em sua organização Teams para habilitar o espaço de endereço SIP compartilhado com sua implantação local.  

Para habilitar o espaço de endereço SIP compartilhado em sua organização, estabeleça uma sessão remota do PowerShell com Teams e execute o seguinte cmdlet:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> O atributo SharedSipAddressSpace precisa permanecer "True" até que a mudança para online seja final e nenhum usuário permaneça no local. 
  
Para estabelecer uma sessão remota do PowerShell com Teams (ou Skype for Business Online), primeiro você precisa instalar o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install). O Teams powershell substitui o Skype para o módulo conector busines online, que foi retirado.
  
Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Teams e como usar o módulo Teams PowerShell, consulte [Configurar](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)seu computador para Windows PowerShell .
  


## <a name="see-also"></a>Também consulte

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
