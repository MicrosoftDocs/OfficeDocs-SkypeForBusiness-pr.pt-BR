---
title: 'Lync Server 2013: excluir um grupo de agentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ed86d1f7b9476626fe00e733407cd821c279cef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="79e42-102">Excluir um grupo de agentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e42-102">Delete an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79e42-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="79e42-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="79e42-104">Use um dos procedimentos a seguir para excluir um grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="79e42-104">Use one of the following procedures to delete an agent group.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a><span data-ttu-id="79e42-105">Para usar o painel de controle do Lync Server para excluir um grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="79e42-105">To use Lync Server Control Panel to delete an agent group</span></span>

1.  <span data-ttu-id="79e42-106">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="79e42-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="79e42-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79e42-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="79e42-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="79e42-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="79e42-109">Na barra de navegação esquerda, clique em **Grupos de Resposta** e clique em **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="79e42-109">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="79e42-110">Na página **grupos de resposta** , digite todo ou parte do nome do grupo de agentes que você deseja excluir no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="79e42-110">On the **Response Groups** page, type all or part of the name of the agent group that you want to delete in the search field.</span></span>

5.  <span data-ttu-id="79e42-111">Na lista resultante, clique no grupo que você deseja excluir, clique em **Editar**e em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="79e42-111">In the resulting list, click the group that you want to delete, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="79e42-112">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="79e42-112">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a><span data-ttu-id="79e42-113">Para usar o Windows PowerShell para excluir um grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="79e42-113">To use Windows PowerShell to delete an agent group</span></span>

1.  <span data-ttu-id="79e42-114">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="79e42-114">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="79e42-115">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="79e42-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="79e42-116">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="79e42-116">At the command line, run:</span></span>
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    <span data-ttu-id="79e42-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="79e42-117">For example:</span></span>
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79e42-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="79e42-118">See Also</span></span>


[<span data-ttu-id="79e42-119">Criar ou modificar um grupo de agentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e42-119">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  


[<span data-ttu-id="79e42-120">Remove-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="79e42-120">Remove-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[<span data-ttu-id="79e42-121">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="79e42-121">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

