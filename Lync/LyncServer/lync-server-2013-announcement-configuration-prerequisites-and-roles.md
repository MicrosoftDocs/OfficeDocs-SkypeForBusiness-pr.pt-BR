---
title: 'Lync Server 2013: Pré-requisitos e funções de configuração de Comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb5f909170e1de2566e21e9305175211c306fee6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="9fa41-102">Pré-requisitos e funções de configuração de Comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fa41-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fa41-103">_**Tópico da última modificação:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="9fa41-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="9fa41-104">O anúncio é um recurso de gerenciamento de chamadas de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="9fa41-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="9fa41-105">Este tópico descreve o que você precisa ter em vigor antes de poder configurar as atribuições de anúncio e de função necessárias para executar tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="9fa41-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="9fa41-106">Esta seção pressupõe que você leu a documentação de planejamento relacionada ao anúncio (consulte [planejando os recursos de gerenciamento de chamadas no Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="9fa41-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="9fa41-107">Pré-requisitos de configuração do comunicado</span><span class="sxs-lookup"><span data-stu-id="9fa41-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="9fa41-108">O aplicativo de anúncio requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="9fa41-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="9fa41-109">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="9fa41-109">Application service</span></span>

  - <span data-ttu-id="9fa41-110">Aplicativo Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="9fa41-110">Response Group application</span></span>

  - <span data-ttu-id="9fa41-111">Armazenamento de arquivos, para armazenar arquivos de áudio</span><span class="sxs-lookup"><span data-stu-id="9fa41-111">File Store, to hold audio files</span></span>

<span data-ttu-id="9fa41-112">Todos esses componentes são instalados por padrão quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9fa41-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="9fa41-113">Funções de configuração do anúncio</span><span class="sxs-lookup"><span data-stu-id="9fa41-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="9fa41-114">Você pode usar as seguintes ferramentas administrativas para configurar comunicados:</span><span class="sxs-lookup"><span data-stu-id="9fa41-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="9fa41-115">Painel de Controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="9fa41-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="9fa41-116">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="9fa41-116">Lync Server Management Shell</span></span>

<span data-ttu-id="9fa41-117">A configuração do aplicativo de anúncio requer uma das seguintes funções administrativas:</span><span class="sxs-lookup"><span data-stu-id="9fa41-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="9fa41-118">**CsVoiceAdministrator**   essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz, incluindo configurações de lançamento.</span><span class="sxs-lookup"><span data-stu-id="9fa41-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="9fa41-119">**CsServerAdministrator**   essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços e configurar todas as configurações de anúncio.</span><span class="sxs-lookup"><span data-stu-id="9fa41-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="9fa41-120">**CsAdministrator**   essa função de administrador pode executar todas as tarefas administrativas e modificar todas as configurações.</span><span class="sxs-lookup"><span data-stu-id="9fa41-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="9fa41-121">**CsViewOnlyAdministrator**   essa função de administrador pode exibir a implantação para monitorar a integridade da implantação.</span><span class="sxs-lookup"><span data-stu-id="9fa41-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9fa41-122">Para obter detalhes sobre direitos de usuário administrativo, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planejando o controle de acesso baseado em função no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="9fa41-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9fa41-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="9fa41-123">See Also</span></span>


[<span data-ttu-id="9fa41-124">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fa41-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="9fa41-125">Planejando os recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fa41-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

