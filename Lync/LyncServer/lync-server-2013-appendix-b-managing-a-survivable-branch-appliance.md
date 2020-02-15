---
title: 'Lync Server 2013: Apêndice B: gerenciando um aparelho de filial persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b98dbf9fa99c5dcfdea3b9b1517c533340329f24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="d661b-102">Apêndice B: gerenciando um aparelho de filial persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d661b-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d661b-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d661b-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d661b-104">Este tópico descreve os procedimentos para o gerenciamento de um aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="d661b-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="d661b-105">Especificamente, como substituir e renomear um aparelho de filial persistente e como alterar o pool de front-ends do Lync Server 2013 ao qual o aparelho de filial persistente está associado.</span><span class="sxs-lookup"><span data-stu-id="d661b-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="d661b-106">Para substituir um aplicativo de filial persistente</span><span class="sxs-lookup"><span data-stu-id="d661b-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="d661b-107">Pare todos os serviços do Lync Server 2013 no aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="d661b-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="d661b-108">(Consulte a documentação do fornecedor do Aparelho de Filial Persistente.)</span><span class="sxs-lookup"><span data-stu-id="d661b-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="d661b-109">Recomenda Remova o aparelho de filial persistente do domínio.</span><span class="sxs-lookup"><span data-stu-id="d661b-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="d661b-110">Exclua o objeto de computador aparelho de filial persistente nos serviços de domínio do Active Directory, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d661b-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="d661b-111">Faça logon em um servidor membro como um membro do grupo Administração de Empresa.</span><span class="sxs-lookup"><span data-stu-id="d661b-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="d661b-112">Clique em **Iniciar**, **Ferramentas Administrativas** e em **Usuários e Computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d661b-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="d661b-113">Clique com o botão direito do mouse no objeto aparelho de filial persistente e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="d661b-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="d661b-114">Adicione novamente o objeto computador de aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="d661b-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="d661b-115">(Consulte [Adicionar um aparelho de filial persistente ao Active Directory no Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span><span class="sxs-lookup"><span data-stu-id="d661b-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="d661b-116">Aguarde a replicação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d661b-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="d661b-117">Abra o Shell de gerenciamento do Lync Server e digite **Enable-CSTopology**.</span><span class="sxs-lookup"><span data-stu-id="d661b-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="d661b-118">Conecte o novo aparelho de filial persistente à rede e siga as etapas em [implantando um servidor ou aparelho de filial persistente com o Lync server 2013 – tarefas de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implantar um aparelho de filial persistente ou servidor com o Lync Server 2013-tarefa do site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="d661b-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="d661b-119">Para renomear um aplicativo de filial persistente</span><span class="sxs-lookup"><span data-stu-id="d661b-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="d661b-120">Mova os usuários para o site central.</span><span class="sxs-lookup"><span data-stu-id="d661b-120">Move users to the central site.</span></span> <span data-ttu-id="d661b-121">Para obter detalhes, consulte [move users to a outro pool no Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d661b-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="d661b-122">Pare todos os serviços do Lync Server 2013 no aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="d661b-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="d661b-123">(Consulte a documentação do fornecedor do Aparelho de Filial Persistente.)</span><span class="sxs-lookup"><span data-stu-id="d661b-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="d661b-124">Remova o aparelho de filial persistente da topologia, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d661b-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="d661b-125">Clique em \*\*Iniciar \*\*, em \*\*Todos os Programas \*\*, em \*\*Microsoft Lync Server 2010 \*\* e em **Construtor de Topologia do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d661b-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="d661b-126">Na árvore do console, expanda **Branch sites**, clique no aparelho de filial persistente e, em seguida, clique em **excluir** no painel ação.</span><span class="sxs-lookup"><span data-stu-id="d661b-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="d661b-127">Remova o aparelho de filial persistente do domínio.</span><span class="sxs-lookup"><span data-stu-id="d661b-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="d661b-128">Exclua o objeto de computador aparelho de filial persistente no Active Directory, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d661b-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="d661b-129">Faça logon em um controlador de domínio como membro do grupo Administração de Empresa.</span><span class="sxs-lookup"><span data-stu-id="d661b-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="d661b-130">Clique em **Iniciar**, depois em **Ferramentas Administrativas** e, em seguida, clique em **Usuários e Computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d661b-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="d661b-131">Clique com o botão direito do mouse no objeto aparelho de filial persistente e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="d661b-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="d661b-132">Restaure o aparelho de filial persistente para os padrões de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d661b-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="d661b-133">(Consulte a documentação do fornecedor do Aparelho de Filial Persistente.)</span><span class="sxs-lookup"><span data-stu-id="d661b-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="d661b-134">Siga as etapas em [implantando um servidor ou aparelho de filial persistente com o Lync server 2013-tarefas do site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implantar um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefa do site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="d661b-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="d661b-135">Mova os usuários para o aparelho de filial persistente renomeado.</span><span class="sxs-lookup"><span data-stu-id="d661b-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="d661b-136">Para obter detalhes, consulte [move users to a outro pool no Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d661b-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="d661b-137">Para alterar o pool de front-end do Lync Server que o aplicativo de filial persistente está associado</span><span class="sxs-lookup"><span data-stu-id="d661b-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="d661b-138">Mova os usuários do aparelho de filial persistente para o pool de front-ends do Lync Server no site central.</span><span class="sxs-lookup"><span data-stu-id="d661b-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="d661b-139">Para obter detalhes, consulte [move users to a outro pool no Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d661b-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="d661b-140">Pare todos os serviços do Lync Server no aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="d661b-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="d661b-141">(Consulte a documentação do fornecedor do aparelho de filial persistente).</span><span class="sxs-lookup"><span data-stu-id="d661b-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="d661b-142">Atualize o pool de front-ends do Lync Server ao qual o aparelho de filial persistente está associado, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d661b-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="d661b-143">Clique em \*\*Iniciar \*\*, em \*\*Todos os Programas \*\*, em \*\*Microsoft Lync Server 2010 \*\* e em **Construtor de Topologia do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d661b-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="d661b-144">Expanda **Sites de filial**.</span><span class="sxs-lookup"><span data-stu-id="d661b-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="d661b-145">Clique com o botão direito do mouse no objeto aparelho de filial persistente para modificar e clique em **Editar propriedades**</span><span class="sxs-lookup"><span data-stu-id="d661b-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="d661b-146">Em resiliência, selecione o novo pool de front-ends ao qual o aparelho de filial persistente está associado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d661b-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="d661b-147">Na árvore do console, clique com o botão direito do mouse no novo dispositivo de filial persistente, clique em **topologia**e em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="d661b-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="d661b-148">Reinicie todos os serviços do Lync Server no aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="d661b-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="d661b-149">Teste o aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="d661b-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="d661b-150">Para obter detalhes, consulte [usuários domésticos em um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="d661b-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="d661b-151">Mova os usuários do pool de front-ends do Lync Server no site central para o aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="d661b-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

