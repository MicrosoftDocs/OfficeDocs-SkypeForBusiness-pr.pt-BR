---
title: 'Lync Server 2013: usando cmdlets para reverter a preparação da floresta'
description: 'Lync Server 2013: usando cmdlets para reverter a preparação da floresta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acac87bdaeb7e730f93401fa62ea2678a713bb8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580387"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="8ba2e-103">Usando cmdlets para reverter a preparação da floresta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ba2e-103">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ba2e-104">_**Última modificação do tópico:** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="8ba2e-104">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="8ba2e-105">Use o cmdlet **Disable-CsAdForest** para reverter a etapa de preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="8ba2e-105">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8ba2e-106">Se você executar o cmdlet <STRONG>Disable-CsAdForest</STRONG> em um ambiente onde você também tem uma versão anterior do Lync Server implantada, as configurações globais da versão anterior também serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="8ba2e-106">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="8ba2e-107">Para usar cmdlets para reverter a preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="8ba2e-107">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="8ba2e-108">Faça o login em um computador que faz parte de um domínio como membro do grupo Administradores de Domínio no domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="8ba2e-108">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="8ba2e-109">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8ba2e-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8ba2e-110">Sejam</span><span class="sxs-lookup"><span data-stu-id="8ba2e-110">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="8ba2e-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8ba2e-111">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="8ba2e-112">O parâmetro Force especifica se deve forçar a execução da tarefa.</span><span class="sxs-lookup"><span data-stu-id="8ba2e-112">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="8ba2e-113">Se esse parâmetro não estiver presente, o comando não será executado se mesmo um domínio da floresta ainda estiver preparado para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ba2e-113">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="8ba2e-114">Se o parâmetro Force é especificado, a ação continuará independente do estado dos outros domínios na floresta.</span><span class="sxs-lookup"><span data-stu-id="8ba2e-114">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="8ba2e-115">Se você não especificar o parâmetro GroupDomain, o valor padrão é o domínio local.</span><span class="sxs-lookup"><span data-stu-id="8ba2e-115">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ba2e-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="8ba2e-116">See Also</span></span>


[<span data-ttu-id="8ba2e-117">Executando a preparação da floresta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ba2e-117">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="8ba2e-118">Preparando a floresta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ba2e-118">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

