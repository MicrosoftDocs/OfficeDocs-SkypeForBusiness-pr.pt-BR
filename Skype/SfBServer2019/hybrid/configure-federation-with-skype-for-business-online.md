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
ms.openlocfilehash: df5fed224484a3c8f8957365f5304095a115b7b1
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839146"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurar Skype para o híbrido de negócios

Para configurar o Skype para híbrido de negócios, você precisa:

- [Configure a federação](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [Configurar um espaço de endereçamento compartilhado do protocolo de iniciação de sessão (SIP)](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [Configurar a autenticação de servidor-para-servidor, se necessário](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Configurar seu serviço de borda de local para federação com Skype para Business Online

Federação permite que os usuários em sua implantação no local para se comunicar com usuários do Office 365 em sua organização. Para configurar a federação, execute os cmdlets a seguir no Skype do Shell de gerenciamento do servidor de negócios:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurar seu Skype para locatário Business Online para um espaço de endereçamento SIP compartilhado

Um endereço de protocolo SIP (Session Initiation Protocol) é um identificador único para cada usuário em uma rede, semelhante a um número de telefone ou endereço de email. Antes de tentar mover os usuários no local para Skype para Business Online, você precisará configurar seu locatário do Office 365 para compartilhar o espaço de endereço de protocolo de iniciação de sessão (SIP) compartilhados com sua implantação no local. Se ele não estiver configurado, talvez você veja a seguinte mensagem de erro:
  
Move-CsUser: Falha de HostedMigration: Error=(510), descrição = (inquilino desse usuário não está habilitado para o espaço de endereçamento sip compartilhado.)
  
Para configurar um espaço de endereçamento SIP compartilhado, estabeleça uma sessão PowerShell remota com Skype para Business Online e, em seguida, execute o seguinte cmdlet:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> O atributo SharedSipAddressSpace deve permanecer "True" até a mudança para online ser final e não restar usuários locais. 
  
Para estabelecer uma sessão PowerShell remota com Skype para Business Online, você precisará primeiro instalar o Skype para o módulo de conector Business Online para o Windows PowerShell, que você pode obter [aqui](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

Para obter mais informações sobre como estabelecer uma sessão PowerShell remota com Skype para Business Online e como usar o Skype para módulo Business Connector Online, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="configure-server-to-server-authentication-if-required"></a>Configurar a autenticação de servidor-para-servidor, se necessário

Dependendo do tipo de ambiente híbrido que você está configurando, você precisará configurar a autenticação de servidor-para-servidor.  Para obter mais informações, consulte [Gerenciar a autenticação de servidor-para-servidor no Skype para Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).


## <a name="see-also"></a>Consulte também

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

