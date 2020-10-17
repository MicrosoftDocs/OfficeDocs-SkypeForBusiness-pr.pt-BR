---
title: 'Lync Server 2013: pré-requisitos e funções de configuração do anúncio'
description: 'Lync Server 2013: pré-requisitos de configuração do comunicado e funções.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e6e7009adc6826c255e28ddda925b0e9be5fd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561887"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="55ceb-103">Pré-requisitos e funções de configuração de comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55ceb-103">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55ceb-104">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="55ceb-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="55ceb-105">O comunicado é um recurso de gerenciamento de chamadas do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="55ceb-105">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="55ceb-106">Este tópico descreve o que você precisa ter em vigor antes de configurar o comunicado e as atribuições de função necessárias para executar tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="55ceb-106">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="55ceb-107">Esta seção supõe que você leu a documentação de planejamento relacionada ao anúncio (consulte [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="55ceb-107">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="55ceb-108">Pré-requisitos de Configuração do Comunicado</span><span class="sxs-lookup"><span data-stu-id="55ceb-108">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="55ceb-109">O aplicativo de comunicado requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="55ceb-109">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="55ceb-110">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="55ceb-110">Application service</span></span>

  - <span data-ttu-id="55ceb-111">Aplicativo do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="55ceb-111">Response Group application</span></span>

  - <span data-ttu-id="55ceb-112">Repositório de Arquivos (para armazenar arquivos de áudio)</span><span class="sxs-lookup"><span data-stu-id="55ceb-112">File Store, to hold audio files</span></span>

<span data-ttu-id="55ceb-113">Todos estes componentes são instalados por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="55ceb-113">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="55ceb-114">Funções da configuração do Comunicado</span><span class="sxs-lookup"><span data-stu-id="55ceb-114">Announcement Configuration Roles</span></span>

<span data-ttu-id="55ceb-115">Você pode usar as seguintes ferramentas administrativas para configurar os Comunicados:</span><span class="sxs-lookup"><span data-stu-id="55ceb-115">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="55ceb-116">Painel de Controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="55ceb-116">Lync Server Control Panel</span></span>

  - <span data-ttu-id="55ceb-117">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="55ceb-117">Lync Server Management Shell</span></span>

<span data-ttu-id="55ceb-118">A configuração do aplicativo de anúncio requer uma das seguintes funções administrativas:</span><span class="sxs-lookup"><span data-stu-id="55ceb-118">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="55ceb-119">**CsVoiceAdministrator**     Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz, incluindo configurações de anúncio.</span><span class="sxs-lookup"><span data-stu-id="55ceb-119">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="55ceb-120">**CsServerAdministrator**     Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços e definir todas as configurações de comunicado.</span><span class="sxs-lookup"><span data-stu-id="55ceb-120">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="55ceb-121">**CsAdministrator**     Essa função de administrador pode realizar todas as tarefas administrativas e modificar todas as configurações.</span><span class="sxs-lookup"><span data-stu-id="55ceb-121">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="55ceb-122">**CsViewOnlyAdministrator**     Essa função de administrador pode exibir a implantação para monitorar a integridade da implantação.</span><span class="sxs-lookup"><span data-stu-id="55ceb-122">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55ceb-123">Para obter detalhes sobre os direitos de usuário administrativo, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="55ceb-123">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55ceb-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="55ceb-124">See Also</span></span>


[<span data-ttu-id="55ceb-125">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55ceb-125">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="55ceb-126">Planejamento de recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55ceb-126">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

