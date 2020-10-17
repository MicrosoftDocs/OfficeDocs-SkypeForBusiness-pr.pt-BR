---
title: 'Lync Server 2013: configurar Federação com o Lync Online'
description: 'Lync Server 2013: configurar Federação com o Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3372a76b5ff7ad9dde5a00fd562b74877bd679a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553307"
---
# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="f1cc3-103">Configurar a Federação do Lync Server 2013 com o Lync Online</span><span class="sxs-lookup"><span data-stu-id="f1cc3-103">Configure federation of Lync Server 2013 with Lync Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1cc3-104">_**Última modificação do tópico:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="f1cc3-104">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="f1cc3-105">Siga as etapas desta seção para configurar a interoperabilidade entre a sua implantação local e o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="f1cc3-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="f1cc3-106">Configurar seu serviço de borda local para federação com o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f1cc3-106">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="f1cc3-107">A Federação permite que os usuários em sua implantação local se comuniquem com os usuários do Microsoft 365 ou do Office 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f1cc3-107">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="f1cc3-108">Para configurar a Federação, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f1cc3-108">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="f1cc3-109">Configurar seu locatário do Skype for Business online para um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="f1cc3-109">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="f1cc3-110">Um endereço SIP (Session Initiation Protocol) é um identificador exclusivo para cada usuário em uma rede, semelhante a um número de telefone ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="f1cc3-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="f1cc3-111">Antes de tentar mover os usuários do Lync do local para o Skype for Business Online, você precisará configurar sua organização do Microsoft 365 ou do Office 365 para compartilhar o espaço de endereço SIP (protocolo de iniciação de sessão compartilhada) com sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="f1cc3-111">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Microsoft 365 or Office 365 organization to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="f1cc3-112">Se isso não estiver configurado, você poderá ver a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="f1cc3-112">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="f1cc3-113">Move-CsUser: falha de HostedMigration: erro = (510), descrição = (o locatário deste usuário não está habilitado para o espaço de endereçamento SIP compartilhado.)</span><span class="sxs-lookup"><span data-stu-id="f1cc3-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="f1cc3-114">Para configurar um espaço de endereçamento SIP compartilhado, estabeleça uma sessão remota do PowerShell com o Skype for Business Online e, em seguida, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f1cc3-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="f1cc3-115">Para estabelecer uma sessão remota do PowerShell com o Skype for Business Online, primeiro você precisa instalar o módulo do Skype for Business online para Windows PowerShell, que pode ser obtido aqui: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .</span><span class="sxs-lookup"><span data-stu-id="f1cc3-115">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="f1cc3-116">Após instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f1cc3-116">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

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

<span data-ttu-id="f1cc3-117">Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Skype for Business Online, consulte [conectar-se ao Skype for Business online usando o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f1cc3-117">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="f1cc3-118">Para obter mais informações sobre como usar o módulo PowerShell do Skype for Business Online, consulte [usando o Windows PowerShell para gerenciar o Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f1cc3-118">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1cc3-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="f1cc3-119">See Also</span></span>


[<span data-ttu-id="f1cc3-120">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="f1cc3-120">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
