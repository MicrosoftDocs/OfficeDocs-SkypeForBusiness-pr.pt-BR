---
title: Remover BackCompatSite
description: Remova o BackCompatSite.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809324320ec1869ac0c9d324b8fc270a3cf8f174
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570267"
---
# <a name="remove-backcompatsite"></a><span data-ttu-id="d5006-103">Remover BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="d5006-103">Remove BackCompatSite</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5006-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d5006-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d5006-105">Depois que todos os pools estão desativados e todos os Servidores de Borda desinstalados, execute o assistente de Mesclagem do Construtor de Topologia para remover o **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="d5006-105">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="d5006-106">Para remover o site BackCompat do Construtor de Topologia</span><span class="sxs-lookup"><span data-stu-id="d5006-106">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="d5006-107">Abra uma implantação existente  do Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="d5006-107">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="d5006-108">No menu **Ação**, clique em **Mesclar Topologia R2 2007**.</span><span class="sxs-lookup"><span data-stu-id="d5006-108">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="d5006-109">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="d5006-109">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="d5006-p101">Na página **Especificar borda herdada**, certifique-se de que a lista de Servidores de Borda está vazia. Se a lista não está vazia, use o botão **Remover** para remover todos os Servidores de Borda herdados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d5006-p101">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="d5006-112">![Assistente de topologia de mesclagem, especificar página de configuração de borda](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Assistente de topologia de mesclagem, especificar página de configuração de borda")</span><span class="sxs-lookup"><span data-stu-id="d5006-112">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="d5006-113">Na página **Especificar configuração da porta SIP interna**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d5006-113">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="d5006-114">Na página **Resumo** , clique em **Avançar** para começar a mesclar as topologias para remover o site herdado.</span><span class="sxs-lookup"><span data-stu-id="d5006-114">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="d5006-115">Na coluna **Status**, verifique se o valor está como **Sucesso** e, então, clique em **Concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="d5006-115">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="d5006-116">No painel à esquerda do Construtor de Topologia, expanda o BackCompatSite e certifique-se que não há servidores listados.</span><span class="sxs-lookup"><span data-stu-id="d5006-116">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="d5006-117">Clique com o botão direito do mouse em **BackCompatSite** e cliquem, então, em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d5006-117">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="d5006-118">No **Construtor de Topologia**, selecione o nó superior **Servidor Lync**.</span><span class="sxs-lookup"><span data-stu-id="d5006-118">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="d5006-119">No menu **Ação**, selecione **Publicar Topologia** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d5006-119">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="d5006-120">Quando o **Assistente para Publicação** for concluído, clique em \*\*Concluir \*\* para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="d5006-120">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

