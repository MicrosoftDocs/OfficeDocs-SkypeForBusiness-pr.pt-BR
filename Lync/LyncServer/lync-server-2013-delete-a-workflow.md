---
title: 'Lync Server 2013: excluir um fluxo de trabalho'
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
ms.openlocfilehash: 4ed32780e23cce82027271e74a89fb87e194cc4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a><span data-ttu-id="0f6ec-102">Excluir um fluxo de trabalho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f6ec-102">Delete a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f6ec-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0f6ec-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0f6ec-104">Use um dos procedimentos a seguir para excluir um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-104">Use one of the following procedures to delete a workflow.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a><span data-ttu-id="0f6ec-105">Para usar o painel de controle do Lync Server excluir um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="0f6ec-105">To use Lync Server Control Panel delete a workflow</span></span>

1.  <span data-ttu-id="0f6ec-106">Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="0f6ec-107">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0f6ec-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0f6ec-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0f6ec-109">Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-109">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="0f6ec-110">Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-110">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="0f6ec-111">No campo **selecionar um serviço** de pesquisa, digite parte ou todo o nome do serviço **ApplicationServer** que hospeda o fluxo de trabalho que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-111">In the **Select a Service** search field, type part or all of the name of the **ApplicationServer** service that hosts the workflow that you want to delete.</span></span>

6.  <span data-ttu-id="0f6ec-112">Na lista de serviços, clique no serviço desejado e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-112">In the list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f6ec-113">A página da ferramenta de configuração de grupo de resposta é aberta.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-113">The Response Group Configuration Tool webpage opens.</span></span> <span data-ttu-id="0f6ec-114">Você também pode abrir a página da Web da ferramenta de configuração de grupo de resposta diretamente de um navegador da web conectando-se à <STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-114">You can also open the Response Group Configuration Tool webpage directly from a web browser by connecting to <STRONG>https://&lt;webPoolFqdn&gt;/RgsConfig</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="0f6ec-115">Em **gerenciar um fluxo de trabalho existente**, localize o fluxo de trabalho que você deseja excluir e, em seguida, em **ação**, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-115">Under **Manage an Existing Workflow**, locate the workflow you want to delete, and then under **Action**, click **Delete**.</span></span>

8.  <span data-ttu-id="0f6ec-116">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-116">Click **Yes**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a><span data-ttu-id="0f6ec-117">Para usar o Windows PowerShell para excluir um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="0f6ec-117">To use Windows PowerShell to delete a workflow</span></span>

1.  <span data-ttu-id="0f6ec-118">Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-118">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="0f6ec-119">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0f6ec-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0f6ec-120">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="0f6ec-120">At the command line, run:</span></span>
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    <span data-ttu-id="0f6ec-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0f6ec-121">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

