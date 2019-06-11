---
title: 'Lync Server 2013: primeiras etapas antes de começar a migrar usuários do Lync Online para o Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e278fcb1e63c1db1334e625765d65d5d556e934
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="4bbdd-102">Primeiras etapas antes de começar a migrar usuários do Lync Online para o Lync local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bbdd-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bbdd-103">_**Tópico da última modificação:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="4bbdd-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="4bbdd-104">Antes de começar a mover os usuários do Lync Online para o seu ambiente local, verifique se todas as seguintes opções são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="4bbdd-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="4bbdd-105">O ambiente local do Lync Server deve ser totalmente implantado e validado.</span><span class="sxs-lookup"><span data-stu-id="4bbdd-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="4bbdd-106">Para obter mais informações, consulte Implantando o [Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="4bbdd-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="4bbdd-107">Seu locatário do Lync Online deve ser configurado para acesso remoto do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4bbdd-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="4bbdd-108">Para fazer isso, primeiro instale o módulo do Lync Online para Windows PowerShell, que você pode obter aqui [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911):.</span><span class="sxs-lookup"><span data-stu-id="4bbdd-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="4bbdd-109">Depois de instalar o módulo, você pode estabelecer uma sessão remota digitando os seguintes cmdlets no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4bbdd-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
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
    
    <span data-ttu-id="4bbdd-110">Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Lync Online, consulte Conectando- [se ao Lync Online usando o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4bbdd-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="4bbdd-111">Para obter mais informações sobre como usar o módulo do PowerShell do Lync Online, consulte [usando o Windows PowerShell para gerenciar o Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4bbdd-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="4bbdd-112">Seu Lync Online deve estar configurado para espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="4bbdd-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="4bbdd-113">Para fazer isso, primeiro inicie uma sessão remota do PowerShell com o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="4bbdd-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="4bbdd-114">Em seguida, execute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4bbdd-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="4bbdd-115">Depois de concluir essas etapas, você pode migrar para [migrar os usuários do Lync Online para o Lync local no Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="4bbdd-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

