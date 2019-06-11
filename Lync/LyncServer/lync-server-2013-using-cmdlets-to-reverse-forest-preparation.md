---
title: 'Lync Server 2013: Usando cmdlets para reverter preparação da floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd186fc3b2c6171b49cf3fd4c9e78b8e66b4cc71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="de7a8-102">Usando cmdlets para reverter preparação da floresta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de7a8-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de7a8-103">_**Tópico da última modificação:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="de7a8-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="de7a8-104">Use o cmdlet **Disable-CsAdForest** para reverter a etapa de preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="de7a8-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="de7a8-105">Se você executar o cmdlet <STRONG>Disable-CsAdForest</STRONG> em um ambiente em que você também tenha uma versão anterior do Lync Server implantada, as configurações globais para a versão anterior também serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="de7a8-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="de7a8-106">Para usar cmdlets para reverter a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="de7a8-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="de7a8-107">Faça logon em um computador que esteja associado a um domínio como membro do grupo Domain admins no domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="de7a8-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="de7a8-108">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="de7a8-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="de7a8-109">Execute:</span><span class="sxs-lookup"><span data-stu-id="de7a8-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="de7a8-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="de7a8-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="de7a8-111">O parâmetro Force especifica se deve forçar a execução da tarefa.</span><span class="sxs-lookup"><span data-stu-id="de7a8-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="de7a8-112">Se esse parâmetro não estiver presente, o comando não será executado se mesmo um domínio na floresta ainda estiver preparado para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de7a8-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="de7a8-113">Se o parâmetro Force for especificado, a ação continuará independentemente do estado de outros domínios na floresta.</span><span class="sxs-lookup"><span data-stu-id="de7a8-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="de7a8-114">Se você não especificar o parâmetro GroupDomain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="de7a8-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="de7a8-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="de7a8-115">See Also</span></span>


[<span data-ttu-id="de7a8-116">Executando preparação de floresta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de7a8-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="de7a8-117">Preparando a floresta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de7a8-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

