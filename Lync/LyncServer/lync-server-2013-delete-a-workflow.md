---
title: 'Lync Server 2013: excluir um fluxo de trabalho'
description: 'Lync Server 2013: excluir um fluxo de trabalho.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a588a1dc0428660db95d4d492abbd1b157ca7a0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553697"
---
# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="26efc-103">Excluir um fluxo de trabalho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26efc-103">Delete a workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26efc-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="26efc-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="26efc-105">Use um dos procedimentos a seguir para excluir um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="26efc-105">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="26efc-106">Para usar o painel de controle do Lync Server excluir um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="26efc-106">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="26efc-107">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="26efc-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="26efc-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="26efc-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="26efc-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="26efc-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="26efc-110">Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="26efc-110">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="26efc-111">Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="26efc-111">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="26efc-112">No campo de pesquisa **Selecionar um Serviço**, insira parte ou todo o nome do serviço de **ApplicationServer** que hospeda o fluxo de trabalho que você quer excluir.</span><span class="sxs-lookup"><span data-stu-id="26efc-112">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="26efc-113">Na lista de serviços, clique no serviço que deseja e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="26efc-113">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26efc-114">A página da ferramenta de configuração do grupo de resposta é aberta.</span><span class="sxs-lookup"><span data-stu-id="26efc-114">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="26efc-115">Você também pode abrir a página da ferramenta de configuração do grupo de resposta diretamente de um navegador da web conectando-se ao <STRONG>https:// &lt; webPoolFqdn &gt; /RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="26efc-115">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="26efc-116">Sob **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você quer excluir e, sob **Ação**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="26efc-116">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="26efc-117">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="26efc-117">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="26efc-118">Para usar o Windows PowerShell para excluir um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="26efc-118">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="26efc-119">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="26efc-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="26efc-120">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="26efc-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="26efc-121">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="26efc-121">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="26efc-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="26efc-122">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

