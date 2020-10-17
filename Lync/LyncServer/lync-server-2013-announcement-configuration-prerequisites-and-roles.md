---
title: 'Lync Server 2013: pré-requisitos e funções de configuração do anúncio'
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
ms.openlocfilehash: 46b5dac5c800f2e11829940445f9ebfe28c1a95c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531688"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="2e9a9-102">Pré-requisitos e funções de configuração de comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9a9-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e9a9-103">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="2e9a9-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="2e9a9-104">O comunicado é um recurso de gerenciamento de chamadas do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="2e9a9-105">Este tópico descreve o que você precisa ter em vigor antes de configurar o comunicado e as atribuições de função necessárias para executar tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="2e9a9-106">Esta seção supõe que você leu a documentação de planejamento relacionada ao anúncio (consulte [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="2e9a9-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="2e9a9-107">Pré-requisitos de Configuração do Comunicado</span><span class="sxs-lookup"><span data-stu-id="2e9a9-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="2e9a9-108">O aplicativo de comunicado requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="2e9a9-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="2e9a9-109">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2e9a9-109">Application service</span></span>

  - <span data-ttu-id="2e9a9-110">Aplicativo do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="2e9a9-110">Response Group application</span></span>

  - <span data-ttu-id="2e9a9-111">Repositório de Arquivos (para armazenar arquivos de áudio)</span><span class="sxs-lookup"><span data-stu-id="2e9a9-111">File Store, to hold audio files</span></span>

<span data-ttu-id="2e9a9-112">Todos estes componentes são instalados por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="2e9a9-113">Funções da configuração do Comunicado</span><span class="sxs-lookup"><span data-stu-id="2e9a9-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="2e9a9-114">Você pode usar as seguintes ferramentas administrativas para configurar os Comunicados:</span><span class="sxs-lookup"><span data-stu-id="2e9a9-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="2e9a9-115">Painel de Controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="2e9a9-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="2e9a9-116">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="2e9a9-116">Lync Server Management Shell</span></span>

<span data-ttu-id="2e9a9-117">A configuração do aplicativo de anúncio requer uma das seguintes funções administrativas:</span><span class="sxs-lookup"><span data-stu-id="2e9a9-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="2e9a9-118">**CsVoiceAdministrator**     Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz, incluindo configurações de anúncio.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="2e9a9-119">**CsServerAdministrator**     Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços e definir todas as configurações de comunicado.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="2e9a9-120">**CsAdministrator**     Essa função de administrador pode realizar todas as tarefas administrativas e modificar todas as configurações.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="2e9a9-121">**CsViewOnlyAdministrator**     Essa função de administrador pode exibir a implantação para monitorar a integridade da implantação.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e9a9-122">Para obter detalhes sobre os direitos de usuário administrativo, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2e9a9-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="2e9a9-123">See Also</span></span>


[<span data-ttu-id="2e9a9-124">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9a9-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="2e9a9-125">Planejamento de recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9a9-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

