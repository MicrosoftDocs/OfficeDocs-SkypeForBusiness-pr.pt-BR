---
title: 'Lync Server 2013: configurar a Federação com o Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d690b21614ec416d82834761772cee05ee16f26e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Configurar a Federação do Lync Server 2013 com o Lync Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-08-15_

Siga as etapas desta seção para configurar a interoperabilidade entre a implantação local e o Skype for Business online.

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Configurar seu serviço de borda local para federação com o Skype for Business Online

A Federação permite que os usuários em sua implantação local se comuniquem com os usuários do Office 365 em sua organização. Para configurar a Federação, execute os seguintes cmdlets:

   ```
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurar seu locatário do Skype for Business online para um espaço de endereço SIP compartilhado

Um endereço de protocolo SIP (Session Initiation Protocol) é um identificador único para cada usuário em uma rede, semelhante a um número de telefone ou endereço de email. Antes de tentar mover os usuários do Lync do local para o Skype for Business Online, você precisará configurar seu locatário do Office 365 para compartilhar o espaço de endereço SIP (protocolo de iniciação de sessão compartilhada) com a implantação local. Se ele não estiver configurado, talvez você veja a seguinte mensagem de erro:

Move-CsUser : HostedMigration fault: Error=(510), Description=(O locatário deste usuário não está habilitado para o espaço de endereço sip compartilhado.)

Para configurar um espaço de endereço SIP compartilhado, estabeleça uma sessão remota do PowerShell com o Skype for Business Online e, em seguida, execute o seguinte cmdlet:

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

Para estabelecer uma sessão remota do PowerShell com o Skype for Business Online, primeiro você precisa instalar o módulo do Skype for Business online para Windows PowerShell, que pode ser obtido [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)aqui:.

Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:

   ```
    Import-Module LyncOnlineConnector
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

Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Skype for Business Online, consulte [conectando-se ao Skype for Business online usando o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Para obter mais informações sobre como usar o módulo do PowerShell do Skype for Business Online, consulte [usando o Windows PowerShell para gerenciar o Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

<div>

## <a name="see-also"></a>Confira também


[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

