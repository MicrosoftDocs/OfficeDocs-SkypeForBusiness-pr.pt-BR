---
title: 'Lync Server 2013: Pré-requisitos de Estacionamento de Chamadas e direitos de usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="01d69-102">Pré-requisitos de Estacionamento de Chamadas e direitos de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01d69-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01d69-103">_**Tópico da última modificação:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="01d69-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="01d69-104">O estacionamento de chamadas é um recurso de gerenciamento de chamadas que é instalado por padrão quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="01d69-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="01d69-105">Este tópico descreve o que você precisa ter em vigor antes de poder configurar o estacionamento de chamadas e os direitos de usuário necessários para executar tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="01d69-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="01d69-106">Os arquivos personalizados de música em espera para o aplicativo de estacionamento de chamadas não são submetidos a backup como parte do processo de recuperação de desastre do Lync Server 2013, e os arquivos serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="01d69-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="01d69-107">Mantenha sempre uma cópia de backup separada dos arquivos de música de espera personalizados que você enviar ao Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="01d69-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="01d69-108">Esta seção pressupõe que você leu a documentação de planejamento relacionada ao estacionamento de chamadas (consulte [planejando os recursos de gerenciamento de chamadas no Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="01d69-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="01d69-109">Pré-requisitos de configuração do parque da chamada</span><span class="sxs-lookup"><span data-stu-id="01d69-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="01d69-110">O estacionamento de chamadas requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="01d69-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="01d69-111">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="01d69-111">Application service</span></span>

  - <span data-ttu-id="01d69-112">Aplicativo de Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="01d69-112">Call Park application</span></span>

<span data-ttu-id="01d69-113">Esses componentes são instalados automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="01d69-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="01d69-114">Se você quiser que os chamadores ouvissem música enquanto a chamada estiver estacionada, um arquivo de música em espera também será necessário.</span><span class="sxs-lookup"><span data-stu-id="01d69-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="01d69-115">Um arquivo de música em espera padrão é instalado automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="01d69-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="01d69-116">Você pode substituir o arquivo padrão pelo seu próprio arquivo de música em espera.</span><span class="sxs-lookup"><span data-stu-id="01d69-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="01d69-117">O parque de chamadas usa o armazenamento de arquivos para armazenar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="01d69-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="01d69-118">Direitos de usuário de configuração do estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="01d69-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="01d69-119">Você pode usar as seguintes ferramentas administrativas para configurar o parque de chamadas:</span><span class="sxs-lookup"><span data-stu-id="01d69-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="01d69-120">Painel de Controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="01d69-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="01d69-121">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="01d69-121">Lync Server Management Shell</span></span>

<span data-ttu-id="01d69-122">Use essas ferramentas para configurar a tabela órbita do parque de chamadas e para definir outras configurações usadas pelo parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="01d69-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="01d69-123">A configuração do estacionamento de chamadas requer qualquer uma das seguintes funções administrativas, dependendo da tarefa:</span><span class="sxs-lookup"><span data-stu-id="01d69-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="01d69-124">**CsVoiceAdministrator:** Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz.</span><span class="sxs-lookup"><span data-stu-id="01d69-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="01d69-125">**CsUserAdministrator:** Esta função de administrador pode habilitar o parque de chamadas na política de voz.</span><span class="sxs-lookup"><span data-stu-id="01d69-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="01d69-126">Essa função de administrador também tem acesso de exibição somente leitura a todas as configurações de voz.</span><span class="sxs-lookup"><span data-stu-id="01d69-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="01d69-127">**CsServerAdministrator:** Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços.</span><span class="sxs-lookup"><span data-stu-id="01d69-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="01d69-128">**CsAdministrator:** Essa função de administrador pode executar todas as tarefas de CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="01d69-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01d69-129">Para obter detalhes sobre direitos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planejando o controle de acesso baseado em função no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="01d69-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01d69-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="01d69-130">See Also</span></span>


[<span data-ttu-id="01d69-131">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01d69-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="01d69-132">Planejando os recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01d69-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

