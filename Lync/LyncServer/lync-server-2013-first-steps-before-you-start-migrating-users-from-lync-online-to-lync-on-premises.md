---
title: 'Lync Server 2013: primeiras etapas antes de começar a migrar usuários do Lync Online para o Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4165df6829818b90a22eff4f90ac8072876b4831
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="d26db-102">Primeiras etapas antes de começar a migrar usuários do Lync Online para o Lync local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d26db-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d26db-103">_**Última modificação do tópico:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="d26db-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="d26db-104">Antes de começar a mover os usuários do Lync Online para o seu ambiente local, verifique se todas as opções a seguir são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="d26db-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="d26db-105">O ambiente local do Lync Server deve ser totalmente implantado e validado.</span><span class="sxs-lookup"><span data-stu-id="d26db-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="d26db-106">Para obter mais informações, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="d26db-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="d26db-107">Seu locatário do Lync Online deve ser configurado para acesso ao PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="d26db-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="d26db-108">Para fazer isso, primeiro instale o módulo do Lync Online para Windows PowerShell, que você pode obter aqui [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911):.</span><span class="sxs-lookup"><span data-stu-id="d26db-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="d26db-109">Após instalar o módulo, você pode estabelecer uma sessão remota digitando os seguintes cmdlets no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="d26db-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    <span data-ttu-id="d26db-110">Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Lync Online, consulte [conectar-se ao Lync Online usando o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d26db-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="d26db-111">Para obter mais informações sobre como usar o módulo PowerShell do Lync Online, consulte [using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d26db-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="d26db-112">O Lync Online deve estar configurado para o espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="d26db-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="d26db-113">Para fazer isso, primeiro inicie uma sessão remota do PowerShell com o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d26db-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="d26db-114">Em seguida, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d26db-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="d26db-115">Depois de concluir essas etapas, você pode passar para [migrar os usuários do Lync Online para o Lync no local no Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="d26db-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

