---
title: Remover BackCompatSite
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
ms.openlocfilehash: 792fcf29033a7495a7da340decb561e25084612d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="65b37-102">Remover BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="65b37-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65b37-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="65b37-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="65b37-104">Depois que todos os pools estão desativados e todos os Servidores de Borda desinstalados, execute o assistente de Mesclagem do Construtor de Topologia para remover o **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="65b37-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="65b37-105">Para remover o site BackCompat do Construtor de Topologia</span><span class="sxs-lookup"><span data-stu-id="65b37-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="65b37-106">Abra uma implantação existente  do Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="65b37-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="65b37-107">No menu **Ação**, clique em **Mesclar Topologia R2 2007**.</span><span class="sxs-lookup"><span data-stu-id="65b37-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="65b37-108">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="65b37-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="65b37-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span><span class="sxs-lookup"><span data-stu-id="65b37-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="65b37-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="65b37-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="65b37-111">![Assistente de topologia de mesclagem, especificar página de configuração de borda](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Assistente de topologia de mesclagem, especificar página de configuração de borda")</span><span class="sxs-lookup"><span data-stu-id="65b37-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="65b37-112">Na página **Especificar configuração da porta SIP interna**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="65b37-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="65b37-113">Na página **Resumo** , clique em **Avançar** para começar a mesclar as topologias para remover o site herdado.</span><span class="sxs-lookup"><span data-stu-id="65b37-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="65b37-114">Na coluna **Status**, verifique se o valor está como **Sucesso** e, então, clique em **Concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="65b37-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="65b37-115">No painel à esquerda do Construtor de Topologia, expanda o BackCompatSite e certifique-se que não há servidores listados.</span><span class="sxs-lookup"><span data-stu-id="65b37-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="65b37-116">Clique com o botão direito do mouse em **BackCompatSite** e cliquem, então, em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="65b37-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="65b37-117">No **Construtor de Topologia**, selecione o nó superior **Servidor Lync**.</span><span class="sxs-lookup"><span data-stu-id="65b37-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="65b37-118">No menu **Ação**, selecione **Publicar Topologia** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="65b37-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="65b37-119">Quando o **Assistente para Publicação** for concluído, clique em \*\*Concluir \*\* para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="65b37-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

