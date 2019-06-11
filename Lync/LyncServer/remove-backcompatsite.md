---
title: Remover BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="44e9c-102">Remover BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="44e9c-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e9c-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="44e9c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="44e9c-104">Após a desativação de todos os pools e a desinstalação de todos os servidores de borda, execute o assistente de mesclagem do construtor de topologias para remover o **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="44e9c-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="44e9c-105">Para remover o site de adcompatibilidade do construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="44e9c-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="44e9c-106">Abrir uma implantação existente do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="44e9c-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="44e9c-107">No menu **ação** , clique em **Merge 2007 R2 Topology**.</span><span class="sxs-lookup"><span data-stu-id="44e9c-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="44e9c-108">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="44e9c-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="44e9c-109">Na página **especificar borda herdada** , certifique-se de que a lista de servidores de borda está vazia.</span><span class="sxs-lookup"><span data-stu-id="44e9c-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="44e9c-110">Se a lista não estiver vazia, use o botão **remover** para remover todos os servidores de borda herdados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="44e9c-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="44e9c-111">![Assistente de topologia de mesclagem, especificar a página de configuração de borda] (images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Assistente de topologia de mesclagem, especificar a página de configuração de borda")</span><span class="sxs-lookup"><span data-stu-id="44e9c-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="44e9c-112">Na página **especificar a configuração da porta SIP interna** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="44e9c-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="44e9c-113">Na página **Resumo** , clique em **Avançar** para começar a mesclar as topologias e remover o site herdado.</span><span class="sxs-lookup"><span data-stu-id="44e9c-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="44e9c-114">Na coluna **status** , verifique se o valor é **êxito** e clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="44e9c-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="44e9c-115">No painel esquerdo do construtor de topologias, expanda o BackCompatSite e assegure-se de que nenhum servidor esteja listado.</span><span class="sxs-lookup"><span data-stu-id="44e9c-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="44e9c-116">Clique com o botão direito do mouse no **BackCompatSite**e, em seguida, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="44e9c-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="44e9c-117">Em **Construtor de topologia**, selecione o nó mais superior do **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="44e9c-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="44e9c-118">No menu **ação** , selecione **publicar topologia** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="44e9c-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="44e9c-119">Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="44e9c-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

