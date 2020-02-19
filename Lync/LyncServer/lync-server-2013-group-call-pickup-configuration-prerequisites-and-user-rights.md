---
title: Pré-requisitos de configuração de recebimento de chamadas de grupo e direitos de usuário
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
ms.openlocfilehash: 6344dea7e4ba4273905af6549ced3f900922e4e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="9f7a8-102">Pré-requisitos de configuração de recebimento de chamadas de grupo e direitos de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f7a8-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f7a8-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="9f7a8-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="9f7a8-104">O recebimento de chamadas em grupo é um recurso de gerenciamento de chamadas que é instalado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="9f7a8-105">Este tópico descreve o que você precisa ter em vigor antes de poder configurar o recebimento de chamadas em grupo e os direitos de usuário necessários para executar tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="9f7a8-106">Esta seção supõe que você leu a documentação de planejamento relacionada ao recebimento de chamadas em grupo (consulte [Planning for Group Call pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="9f7a8-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="9f7a8-107">Pré-requisitos de configuração de recebimento de chamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="9f7a8-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="9f7a8-108">O recebimento de chamadas em grupo requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="9f7a8-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="9f7a8-109">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="9f7a8-109">Application service</span></span>

  - <span data-ttu-id="9f7a8-110">Call Park application</span><span class="sxs-lookup"><span data-stu-id="9f7a8-110">Call Park application</span></span>

<span data-ttu-id="9f7a8-111">Esses componentes são instalados automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="9f7a8-112">Direitos de usuário de configuração de recebimento de chamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="9f7a8-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="9f7a8-113">Use as seguintes ferramentas administrativas para configurar o recebimento de chamadas em grupo:</span><span class="sxs-lookup"><span data-stu-id="9f7a8-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="9f7a8-114">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="9f7a8-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="9f7a8-115">Ferramenta SEFAUtil Resource Kit</span><span class="sxs-lookup"><span data-stu-id="9f7a8-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="9f7a8-116">Use o Shell de gerenciamento do Lync Server para criar e gerenciar grupos de recebimento de chamada na tabela de órbita de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="9f7a8-117">Use a ferramenta SEFAUtil Resource Kit para atribuir um grupo de recebimento de chamadas e habilitar o recebimento de chamadas em grupo para usuários ou para desabilitar o recebimento de chamadas em grupo para usuários.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="9f7a8-118">A configuração de recebimento de chamadas em grupo exige qualquer uma das seguintes funções administrativas, dependendo da tarefa:</span><span class="sxs-lookup"><span data-stu-id="9f7a8-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="9f7a8-119">**CsVoiceAdministrator:** Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="9f7a8-120">**CsUserAdministrator:** Essa função de administrador pode habilitar o recebimento de chamadas em grupo para usuários.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="9f7a8-121">Esta função de administração também pode ter acesso de exibição somente leitura para todas as configurações de voz.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="9f7a8-122">**CsServerAdministrator:** Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="9f7a8-123">**CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9f7a8-124">Para obter detalhes sobre os direitos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="9f7a8-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f7a8-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="9f7a8-125">See Also</span></span>


[<span data-ttu-id="9f7a8-126">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f7a8-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="9f7a8-127">Planejamento de recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f7a8-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

