---
title: Remover a associação de Servidor de Arquivamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bf1a5a3c68ab1123431543e08618c4eacb7559
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="9fd6d-102">Remover a associação de Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="9fd6d-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fd6d-103">_**Tópico da última modificação:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="9fd6d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="9fd6d-104">Para remover um servidor de arquivamento, você precisa alterar ou desmarcar a dependência do pool de front-ends associado, servidor front-end, aparelho para filiais e servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="9fd6d-105">Edite as propriedades do pool de front-end, servidor front-end, appliances para ramificação sobreviventes e servidor de ramificação sobreviventes para remover a dependência.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="9fd6d-106">Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto de repositório de banco de dados associado também será excluído.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="9fd6d-107">Para remover a associação do servidor de arquivamento</span><span class="sxs-lookup"><span data-stu-id="9fd6d-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="9fd6d-108">Abra o servidor front-end do Lync Server 2013, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="9fd6d-109">Navegue até o nó do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="9fd6d-110">No construtor de topologia, expanda **pools de front-end do Enterprise Edition**, **servidores front-end da edição padrão**ou **sites de filiais**com base em onde o servidor de arquivamento está definido.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="9fd6d-111">Se você tiver um servidor de ramificação sobreviventes associado, expanda **sites de ramificação**, expanda o nome do site da filial e expanda **aparelhos de ramificação sobreviventes**.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fd6d-112"><STRONG>Aparelhos de ramificação sobreviventes</STRONG> na interface do usuário se aplicam ao servidor de ramificação sobreviventes e ao aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="9fd6d-113">Clique com o botão direito do mouse no pool, no servidor ou no dispositivo associado ao servidor de arquivamento e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="9fd6d-114">Em **Editar propriedades**, em **geral**, em **associações**, desmarque a caixa de seleção **associar servidor de arquivamento** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="9fd6d-115">Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao servidor de arquivamento que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="9fd6d-116">Clique com o botão direito do mouse no servidor de arquivamento e, em seguida, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="9fd6d-117">Em **excluir repositórios dependentes**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="9fd6d-118">Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Lync Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

