---
title: Configurar federação com o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Resumo: Saiba como configurar a interoperabilidade entre sua implantação no local e Skype para Business Online.'
ms.openlocfilehash: 7367a1fa7bf7eb305a8b72582e488cfd6ba6fa1c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884117"
---
# <a name="configure-federation-with-skype-for-business-online"></a>Configurar federação com o Skype for Business Online
 
**Resumo:** Saiba como configurar a interoperabilidade entre sua implantação no local e Skype para Business Online.
  
Siga as etapas nesta seção para configurar a interoperabilidade entre sua implantação no local e Skype para Business Online.
  
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
  
Para estabelecer uma sessão PowerShell remota com Skype para Business Online, você precisará primeiro instalar o Skype para Business Online do módulo do conector para o Windows PowerShell, que você pode obter aqui: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
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

Para obter mais informações sobre como usar o PowerShell com Skype para Business Online, consulte [Configurar o computador para o Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

  
## <a name="see-also"></a>Consulte também

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)