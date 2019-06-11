---
title: 'Lync Server 2013: Configurando Grupo de Resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4d12d1ee21cfa5e480dea52a0de9f89b250715c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="2fccd-102">Configurando Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fccd-103">_**Tópico da última modificação:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="2fccd-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="2fccd-104">O grupo de resposta é um recurso de voz empresarial que roteia e enfileira chamadas de entrada para grupos de pessoas, chamados *agentes*, como um suporte técnico ou uma mesa de atendimento ao cliente.</span><span class="sxs-lookup"><span data-stu-id="2fccd-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="2fccd-105">Os componentes necessários para o grupo de resposta são instalados e habilitados automaticamente no servidor front-end ou no servidor Standard Edition ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2fccd-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="2fccd-106">Para disponibilizar o grupo de resposta para os usuários, você deve configurar grupos de agente e, em seguida, filas e fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2fccd-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="2fccd-107">Além disso, um administrador de grupo de resposta pode delegar a configuração de um fluxo de trabalho existente a um gerente de grupo de resposta, que pode, em seguida, modificar e reconfigurar o fluxo de trabalho e seus grupos e filas de agente associados.</span><span class="sxs-lookup"><span data-stu-id="2fccd-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="2fccd-108">Esta seção orienta você na configuração do grupo de respostas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2fccd-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="2fccd-109">Ele pressupõe que você já leu as seções de planejamento relacionadas ao grupo de resposta e implantou um servidor Enterprise Edition ou um servidor Standard Edition com Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2fccd-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2fccd-110">Para obter detalhes sobre como criar um grupo de resposta usando o Shell de gerenciamento do Lync Server, incluindo um exemplo de script, consulte "criando seu primeiro grupo de resposta <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>usando o Shell de gerenciamento do Lync Server" em.</span><span class="sxs-lookup"><span data-stu-id="2fccd-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2fccd-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2fccd-111">In This Section</span></span>

  - [<span data-ttu-id="2fccd-112">Permissões e pré-requisitos de configuração de Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="2fccd-113">Processo de implantação para o grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="2fccd-114">Visão geral dos cenários de criação do fluxo de trabalho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="2fccd-115">Criar grupos de agente do Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="2fccd-116">Criar filas do Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="2fccd-117">Adicionais Definir o horário comercial do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="2fccd-118">Adicionais Definir conjuntos de feriados do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="2fccd-119">Criar fluxos de trabalho de Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="2fccd-120">Adicionais Verificar a implantação do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2fccd-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="2fccd-121">See Also</span></span>


[<span data-ttu-id="2fccd-122">Planejando os recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fccd-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

