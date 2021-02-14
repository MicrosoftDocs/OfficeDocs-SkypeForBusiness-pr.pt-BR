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
ms.openlocfilehash: 0df507fcc47157a9290018a199e1362cb203048b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221445"
---
# <a name="configure-skype-for-business-hybrid"></a>Configure o Skype for Business híbrido

Para configurar o Skype for Business híbrido, você precisa:

- Configure seu serviço de Borda local para federar com o [Microsoft 365 ou Office 365.](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)
- [Configure seu ambiente local para confiar no Microsoft 365 ou Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)e habilitar o espaço de endereço SIP compartilhado.
- [Habilita o espaço de endereço SIP compartilhado em sua organização do Microsoft 365 ou Office 365.](#enable-shared-sip-address-space-in-your-organization)

Observe que, se você tiver o Exchange no local, talvez queira configurar o OAuth entre seus ambientes locais do Exchange e do Skype for Business Online. Para obter mais informações, consulte Gerenciar a autenticação de servidor para servidor no [Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) e planejar a integração do Skype for Business e do [Exchange.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Configurar seu serviço de Borda local para federar com o Microsoft 365 ou Office 365

A federação permite que os usuários em sua implantação local se comuniquem com usuários do Microsoft 365 ou Office 365 em sua organização. Para configurar a federação, execute o seguinte cmdlet no Shell de Gerenciamento do Skype for Business Server:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Se o valor "-EnablePartnerDiscovery" estiver definido como $True, o Skype for Business Server usará registros DNS para tentar descobrir domínios parceiros não listados na lista AllowedDomains. Se o valor for definido como $False , o Skype for Business Server irá federar apenas com domínios encontrados na lista AllowedDomains. Esse parâmetro é obrigatório caso se esteja utilizando o roteamento de serviço de DNS.

> [!NOTE]
> Para obter mais detalhes sobre a habilitação da federação entre usuários de sua implantação local do Skype for Business e usuários de uma organização do Skype for Business Online, consulte Configurando o suporte de federação para um cliente do Skype for Business Online no [Skype for Business Server.](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Configurar seu ambiente local para habilitar o espaço de endereço SIP compartilhado com o Microsoft 365 ou o Office 365

Você também deve configurar seu ambiente local para confiar no Microsoft 365 ou Office 365 e habilitar o espaço de endereço SIP compartilhado. Isso significa que o Microsoft 365 ou o Office 365 pode hospedar contas de usuário para o mesmo conjunto de domínios SIP que seu ambiente local, e as mensagens podem ser roteadas entre usuários hospedados no local e online.  Você pode fazer isso configurando um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com conforme descrito abaixo.

Primeiro, verifique se você já tem um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com. Se houver, remova-o usando o seguinte comando:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Em seguida, crie um novo provedor de hospedagem, use New-CsHostingProvider cmdlet da seguinte forma: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Habilitar o espaço de endereço SIP compartilhado em sua organização
  
Além da alteração feita em sua implantação local, você precisará fazer a alteração correspondente em sua organização do Microsoft 365 ou Office 365 para habilitar o espaço de endereço SIP compartilhado com sua implantação local.  

Para habilitar o espaço de endereço SIP compartilhado em sua organização, estabeleça uma sessão remota do PowerShell com o Skype for Business Online e execute o seguinte cmdlet:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> O atributo SharedSipAddressSpace precisa permanecer "True" até que a mudança para online seja final e nenhum usuário permaneça no local. 
  
Para estabelecer uma sessão remota do PowerShell com o Teams ou o Skype for Business Online, primeiro você precisa instalar o módulo de conector do Skype for Business Online para o Windows PowerShell, que você pode obter [aqui.](https://go.microsoft.com/fwlink/p/?LinkId=391911)
  
Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Skype for Business Online e como usar o módulo conector do Skype for Business Online, consulte Configurar seu computador para [o Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
  


## <a name="see-also"></a>Confira também

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
