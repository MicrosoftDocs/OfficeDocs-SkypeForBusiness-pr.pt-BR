---
title: 'Lync Server 2013: Shell de gerenciamento do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f367ec9ff3f990c410a95289c159bb021b053cec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="e1bed-102">Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1bed-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1bed-103">_**Última modificação do tópico:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="e1bed-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1bed-104">A referência de cmdlet do Skype for Business foi movida para o docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e1bed-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="e1bed-105">Clicando nos links abaixo, você será retirado da nova página do docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e1bed-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="e1bed-106">O conteúdo agora é aberto e está disponível para contribuições da Comunidade por meio do GitHub.</span><span class="sxs-lookup"><span data-stu-id="e1bed-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="e1bed-107">Interessado em contribuir?</span><span class="sxs-lookup"><span data-stu-id="e1bed-107">Interested in contributing?</span></span> <span data-ttu-id="e1bed-108">Confira o LEIAme no repositório aqui:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="e1bed-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="e1bed-109">O Microsoft Lync Server 2010 introduziu um amplo conjunto de recursos novos e aprimorados em comparação com o que estava disponível no Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e1bed-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="e1bed-110">Uma melhoria é a maneira como você gerencia sua implementação.</span><span class="sxs-lookup"><span data-stu-id="e1bed-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="e1bed-111">Por exemplo, há uma nova interface de usuário, chamada painel de controle do Lync Server, que representa uma grande mudança do que a maioria das pessoas usa com o console de gerenciamento da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1bed-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="e1bed-112">A outra grande melhoria da capacidade de gerenciamento é a inclusão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1bed-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="e1bed-113">O Windows PowerShell permite que você gerencie aplicativos da Microsoft a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="e1bed-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="e1bed-114">Ele inclui um ambiente de linha de comando, comandos específicos do produto e uma linguagem de script completa.</span><span class="sxs-lookup"><span data-stu-id="e1bed-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="e1bed-115">O Windows PowerShell foi introduzido pela primeira vez como uma versão baixável para o sistema operacional Windows no final de 2006 e foi incorporado como a interface de linha de comando para a capacidade de gerenciamento do Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e1bed-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="e1bed-116">A partir desse ponto, ela continuou crescendo e foi incorporada na maioria dos produtos de servidor da Microsoft, sendo que a última delas é o Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1bed-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e1bed-117">O Lync Server 2010 introduziu próximo a 550 cmdlets específicos do produto que você pode usar para gerenciar todos os aspectos da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="e1bed-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="e1bed-118">As seções a seguir contêm uma lista de cmdlets e suas descrições.</span><span class="sxs-lookup"><span data-stu-id="e1bed-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="e1bed-119">Essas informações também estão disponíveis diretamente na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="e1bed-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="e1bed-120">Basta digitar o seguinte no prompt de comando do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="e1bed-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="e1bed-121">Por exemplo, para recuperar a ajuda do prompt de comando no cmdlet **New-CsVoicePolicy** , digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e1bed-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="e1bed-122">Coisas que você precisa saber sobre o Windows PowerShell no Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="e1bed-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="e1bed-123">Para executar os cmdlets do Lync Server, abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1bed-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e1bed-124">Se você abrir uma janela do Windows PowerShell em vez do Shell de gerenciamento do Lync Server, por padrão, não será possível executar os cmdlets do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1bed-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="e1bed-125">Para executar os cmdlets do Lync Server no Windows PowerShell, primeiro digite o seguinte no prompt de comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e1bed-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="e1bed-126">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="e1bed-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="e1bed-127">O Shell de gerenciamento do Lync Server é instalado automaticamente em todos os servidores front-end do Lync Server Enterprise Edition ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e1bed-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="e1bed-128">Informações novas e atualizadas, exemplos de scripts e ajuda para introdução e saiba mais sobre o Windows PowerShell e os cmdlets do Microsoft Lync Server 2013 estão disponíveis no blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)do Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1bed-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

