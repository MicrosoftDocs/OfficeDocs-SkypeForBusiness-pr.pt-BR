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
ms.openlocfilehash: 2ed2a44ccd1730de2ebede4b08c1a4d3d7e0da9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="5ea2e-102">Chamadas em grupo escolha pré-requisitos de configuração e direitos de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea2e-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea2e-103">_**Tópico da última modificação:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="5ea2e-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="5ea2e-104">O recebimento de chamadas em grupo é um recurso de gerenciamento de chamadas que é instalado por padrão quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="5ea2e-105">Este tópico descreve o que você precisa ter em vigor antes de poder configurar o recebimento de chamadas em grupo e os direitos de usuário necessários para executar tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="5ea2e-106">Esta seção pressupõe que você leu a documentação de planejamento relacionada à retirada de chamadas em grupo (consulte [planejar a coleta de chamadas em grupo no Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="5ea2e-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="5ea2e-107">Pré-requisitos de configuração de recebimento de chamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="5ea2e-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="5ea2e-108">O recebimento de chamadas em grupo requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="5ea2e-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="5ea2e-109">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="5ea2e-109">Application service</span></span>

  - <span data-ttu-id="5ea2e-110">Aplicativo de Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="5ea2e-110">Call Park application</span></span>

<span data-ttu-id="5ea2e-111">Esses componentes são instalados automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="5ea2e-112">Direitos de usuário de configuração de recebimento de chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="5ea2e-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="5ea2e-113">Use as seguintes ferramentas administrativas para configurar o recebimento de chamadas em grupo:</span><span class="sxs-lookup"><span data-stu-id="5ea2e-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="5ea2e-114">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5ea2e-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="5ea2e-115">Ferramenta SEFAUtil Resource Kit</span><span class="sxs-lookup"><span data-stu-id="5ea2e-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="5ea2e-116">Use o Shell de gerenciamento do Lync Server para criar e gerenciar grupos de recebimento de chamadas na tabela órbita do estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="5ea2e-117">Use a ferramenta kit de recursos do SEFAUtil para atribuir um grupo de encaminhamento de chamadas e habilitar o recurso de recebimento de chamadas em grupo para usuários ou para desabilitar a retirada de chamadas em grupo para usuários.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="5ea2e-118">A configuração da retirada de chamadas em grupo requer qualquer uma das seguintes funções administrativas, dependendo da tarefa:</span><span class="sxs-lookup"><span data-stu-id="5ea2e-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="5ea2e-119">**CsVoiceAdministrator:** Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="5ea2e-120">**CsUserAdministrator:** Essa função de administrador pode permitir que o recebimento de chamadas em grupo seja usuário.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="5ea2e-121">Essa função de administrador também tem acesso de exibição somente leitura a todas as configurações de voz.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="5ea2e-122">**CsServerAdministrator:** Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="5ea2e-123">**CsAdministrator:** Essa função de administrador pode executar todas as tarefas de CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5ea2e-124">Para obter detalhes sobre direitos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planejando o controle de acesso baseado em função no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ea2e-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="5ea2e-125">See Also</span></span>


[<span data-ttu-id="5ea2e-126">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea2e-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="5ea2e-127">Planejando os recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea2e-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

