---
title: Remover a associação do Servidor de Monitoramento
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aa78a49686ca555fdbc26d3ffd4953d88d64a95
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="f08df-102">Remover a associação do Servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="f08df-102">Remove the Monitoring server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f08df-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f08df-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f08df-104">Para remover o Monitoring Server, você precisa alterar ou limpar a dependência do pool de front-ends associado, servidor front-end, aparelho de filial persistente e servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="f08df-104">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="f08df-105">Edite as propriedades do pool de front-ends, servidor front-end, aparelho de filial persistente e servidor de filial persistente para remover a dependência.</span><span class="sxs-lookup"><span data-stu-id="f08df-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="f08df-106">Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto repositório de banco de dados associado no construtor de topologias também será excluído.</span><span class="sxs-lookup"><span data-stu-id="f08df-106">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="f08df-107">Para remover a associação do Servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="f08df-107">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="f08df-108">Abra o servidor front-end do Lync Server 2013, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f08df-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="f08df-109">Navegue até o nó do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f08df-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="f08df-110">No construtor de topologias, expanda **pools de front-ends Enterprise Edition**, **servidores front-end Standard Edition**ou **sites de filiais**, com base em onde o servidor de monitoramento está definido.</span><span class="sxs-lookup"><span data-stu-id="f08df-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="f08df-111">Se você tiver um servidor de filial persistente associado, expanda **sites de filial**, expanda o nome do site de filial e expanda **aparelhos de filial persistente**.</span><span class="sxs-lookup"><span data-stu-id="f08df-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f08df-112"><STRONG>Aparelhos de filial persistentes</STRONG> na interface do usuário aplicam-se ao servidor de filial persistente e ao aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="f08df-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="f08df-113">Clique com o botão direito do mouse no pool, servidor ou dispositivo associado ao servidor de monitoramento e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f08df-113">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="f08df-114">Em **Editar Propriedades**, em **Geral**, em **Associações**, limpe a caixa de seleção **Associar Servidor de Monitoramento** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f08df-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="f08df-115">Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f08df-115">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="f08df-116">Clique com o botão direito do mouse no servidor de monitoramento e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="f08df-116">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="f08df-117">Em **Excluir Repositórios Dependentes**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f08df-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="f08df-118">Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Lync Server, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f08df-118">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

