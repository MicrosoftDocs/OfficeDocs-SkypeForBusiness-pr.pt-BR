---
title: Pré-requisitos de configuração de recebimento de chamadas de grupo e direitos de usuário
description: Pré-requisitos de configuração de recebimento de chamadas de grupo e direitos de usuário.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554447"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="e4d5b-103">Pré-requisitos de configuração de recebimento de chamadas de grupo e direitos de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d5b-103">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4d5b-104">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e4d5b-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e4d5b-105">O recebimento de chamadas em grupo é um recurso de gerenciamento de chamadas que é instalado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-105">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e4d5b-106">Este tópico descreve o que você precisa ter em vigor antes de poder configurar o recebimento de chamadas em grupo e os direitos de usuário necessários para executar tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-106">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="e4d5b-107">Esta seção supõe que você leu a documentação de planejamento relacionada ao recebimento de chamadas em grupo (consulte [Planning for Group Call pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="e4d5b-107">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="e4d5b-108">Pré-requisitos de configuração de recebimento de chamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="e4d5b-108">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="e4d5b-109">O recebimento de chamadas em grupo requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="e4d5b-109">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="e4d5b-110">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="e4d5b-110">Application service</span></span>

  - <span data-ttu-id="e4d5b-111">Call Park application</span><span class="sxs-lookup"><span data-stu-id="e4d5b-111">Call Park application</span></span>

<span data-ttu-id="e4d5b-112">Esses componentes são instalados automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-112">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="e4d5b-113">Direitos de usuário de configuração de recebimento de chamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="e4d5b-113">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="e4d5b-114">Use as seguintes ferramentas administrativas para configurar o recebimento de chamadas em grupo:</span><span class="sxs-lookup"><span data-stu-id="e4d5b-114">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="e4d5b-115">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="e4d5b-115">Lync Server Management Shell</span></span>

  - <span data-ttu-id="e4d5b-116">Ferramenta SEFAUtil Resource Kit</span><span class="sxs-lookup"><span data-stu-id="e4d5b-116">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="e4d5b-117">Use o Shell de gerenciamento do Lync Server para criar e gerenciar grupos de recebimento de chamada na tabela de órbita de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-117">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="e4d5b-118">Use a ferramenta SEFAUtil Resource Kit para atribuir um grupo de recebimento de chamadas e habilitar o recebimento de chamadas em grupo para usuários ou para desabilitar o recebimento de chamadas em grupo para usuários.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-118">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="e4d5b-119">A configuração de recebimento de chamadas em grupo exige qualquer uma das seguintes funções administrativas, dependendo da tarefa:</span><span class="sxs-lookup"><span data-stu-id="e4d5b-119">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="e4d5b-120">**CsVoiceAdministrator:** Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-120">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="e4d5b-121">**CsUserAdministrator:** Essa função de administrador pode habilitar o recebimento de chamadas em grupo para usuários.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-121">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="e4d5b-122">Esta função de administração também pode ter acesso de exibição somente leitura para todas as configurações de voz.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-122">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="e4d5b-123">**CsServerAdministrator:** Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-123">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="e4d5b-124">**CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-124">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e4d5b-125">Para obter detalhes sobre os direitos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="e4d5b-125">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4d5b-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="e4d5b-126">See Also</span></span>


[<span data-ttu-id="e4d5b-127">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d5b-127">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="e4d5b-128">Planejamento de recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d5b-128">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

