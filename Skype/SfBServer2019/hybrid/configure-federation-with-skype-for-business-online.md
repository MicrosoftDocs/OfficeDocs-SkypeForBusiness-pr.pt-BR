---
title: Configurar Skype para o híbrido de negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumo: Saiba como configurar a interoperabilidade entre sua implantação no local e Skype para Business Online.'
ms.openlocfilehash: db03636d412caa72a3b7a38d0c1d691c83d96a5b
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532774"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurar Skype para o híbrido de negócios

Para configurar o Skype para híbrido de negócios, você precisa:

- [Configure o ambiente local para estabelecer uma federação com o Office 365.](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [Configurar seu ambiente local para confiar no Office 365 e habilite o espaço de endereçamento SIP compartilhado com o Office 365.](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [Habilite o espaço de endereçamento SIP compartilhado no seu locatário do Office 365.](#configure-server-to-server-authentication-if-required)

> [!NOTE]
> Se você tiver o Exchange local, convém configurar OAuth entre o Exchange local e Skype para ambientes corporativos on-line. Para obter mais informações, consulte [Gerenciar a autenticação de servidor-para-servidor no Skype para Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) e [Planejar a integração do Skype para Exchange e de negócios](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Configurar seu serviço de borda de local para estabelecer uma federação com o Office 365

Federação permite que os usuários em sua implantação no local para se comunicar com usuários do Office 365 em sua organização. Para configurar a federação, execute o seguinte cmdlet no Skype do Shell de gerenciamento do servidor de negócios:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Configurar seu ambiente local para habilitar o espaço de endereçamento SIP compartilhado com o Office 365

Você também deve configurar seu ambiente local para confiar no Office 365 e habilitar o espaço de endereçamento SIP compartilhado com o Office 365. Isso significa o Office 365 podem hospedar contas de usuário para o mesmo conjunto de domínios SIP que seu ambiente local e as mensagens podem ser roteados entre usuários hospedados no local e online.  Para fazer isso, configurando um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com conforme descrito abaixo.

Primeiro, verifique se você já tiver um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com. Se houver, removê-lo usando o seguinte comando:

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Em seguida, crie um novo provedor de hospedagem, use o cmdlet New-CsHostingProvider da seguinte maneira: 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Habilitar o espaço de endereçamento SIP compartilhado no seu locatário do Office 365
  
Além da alteração feita na sua implantação no local, você precisará faça a alteração correspondente no seu locatário do Office 365 habilitado espaço de endereçamento SIP compartilhado com sua implantação no local.  

Para habilitar o espaço de endereçamento SIP compartilhado no seu locatário do Office 365, estabeleça uma sessão PowerShell remota com Skype para Business Online e, em seguida, execute o seguinte cmdlet:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> O atributo SharedSipAddressSpace deve permanecer "True" até a mudança para online ser final e não restar usuários locais. 
  
Para estabelecer uma sessão PowerShell remota com equipes ou Skype para Business Online, você precisará primeiro instalar o Skype para o módulo de conector Business Online para o Windows PowerShell, que você pode obter [aqui](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Para obter mais informações sobre como estabelecer uma sessão PowerShell remota com Skype para Business Online e como usar o Skype para módulo Business Connector Online, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Consulte também

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

