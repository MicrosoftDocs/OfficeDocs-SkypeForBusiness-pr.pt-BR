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
ms.openlocfilehash: 5ee7cf175e2ca46a54f3c6505fe5f94b69120763
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="ab4eb-102">Configurar a Federação do Lync Server 2013 com o Lync Online</span><span class="sxs-lookup"><span data-stu-id="ab4eb-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab4eb-103">_**Tópico da última modificação:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="ab4eb-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="ab4eb-104">Siga as etapas desta seção para configurar a interoperabilidade entre a implantação local e o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="ab4eb-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="ab4eb-105">Configurar seu serviço de borda local para federação com o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ab4eb-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="ab4eb-106">A Federação permite que os usuários em sua implantação local se comuniquem com os usuários do Office 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ab4eb-106">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="ab4eb-107">Para configurar a Federação, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="ab4eb-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="ab4eb-108">Configurar seu locatário do Skype for Business online para um espaço de endereço SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="ab4eb-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="ab4eb-109">Um endereço de protocolo SIP (Session Initiation Protocol) é um identificador único para cada usuário em uma rede, semelhante a um número de telefone ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="ab4eb-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="ab4eb-110">Antes de tentar mover os usuários do Lync do local para o Skype for Business Online, você precisará configurar seu locatário do Office 365 para compartilhar o espaço de endereço SIP (protocolo de iniciação de sessão compartilhada) com a implantação local.</span><span class="sxs-lookup"><span data-stu-id="ab4eb-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="ab4eb-111">Se ele não estiver configurado, talvez você veja a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="ab4eb-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="ab4eb-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(O locatário deste usuário não está habilitado para o espaço de endereço sip compartilhado.)</span><span class="sxs-lookup"><span data-stu-id="ab4eb-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="ab4eb-113">Para configurar um espaço de endereço SIP compartilhado, estabeleça uma sessão remota do PowerShell com o Skype for Business Online e, em seguida, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ab4eb-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="ab4eb-114">Para estabelecer uma sessão remota do PowerShell com o Skype for Business Online, primeiro você precisa instalar o módulo do Skype for Business online para Windows PowerShell, que pode ser obtido [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)aqui:.</span><span class="sxs-lookup"><span data-stu-id="ab4eb-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="ab4eb-115">Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="ab4eb-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

<span data-ttu-id="ab4eb-116">Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Skype for Business Online, consulte [conectando-se ao Skype for Business online usando o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ab4eb-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="ab4eb-117">Para obter mais informações sobre como usar o módulo do PowerShell do Skype for Business Online, consulte [usando o Windows PowerShell para gerenciar o Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ab4eb-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab4eb-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="ab4eb-118">See Also</span></span>


[<span data-ttu-id="ab4eb-119">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="ab4eb-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

