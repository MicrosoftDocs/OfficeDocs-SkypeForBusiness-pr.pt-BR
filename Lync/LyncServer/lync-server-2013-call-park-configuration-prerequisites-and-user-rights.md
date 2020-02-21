---
title: 'Lync Server 2013: pré-requisitos de configuração do estacionamento de chamadas e direitos de usuário'
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
ms.openlocfilehash: 2f357a840c4fdb08ea63e24b3a80394030dfbcb6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="b9ac2-102">Pré-requisitos de configuração do estacionamento de chamadas e direitos de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9ac2-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9ac2-103">_**Última modificação do tópico:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="b9ac2-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="b9ac2-104">O estacionamento de chamada é um recurso de gerenciamento de chamadas que é instalado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b9ac2-105">Este tópico descreve o que você precisa ter em vigor antes de poder configurar o estacionamento de chamadas e os direitos de usuário necessários para executar tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b9ac2-106">Não é feito backup dos arquivos de música em espera personalizados para o aplicativo de estacionamento de chamada como parte do processo de recuperação de desastres do Lync Server 2013, e os arquivos serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="b9ac2-107">Mantenha sempre uma cópia de backup separada dos arquivos de música em espera personalizados que você carregou para o estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="b9ac2-108">Esta seção supõe que você leu a documentação de planejamento relacionada ao estacionamento de chamada (consulte [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="b9ac2-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="b9ac2-109">Pré-requisitos de configuração do estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="b9ac2-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="b9ac2-110">O estacionamento de chamada requer os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="b9ac2-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="b9ac2-111">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b9ac2-111">Application service</span></span>

  - <span data-ttu-id="b9ac2-112">Call Park application</span><span class="sxs-lookup"><span data-stu-id="b9ac2-112">Call Park application</span></span>

<span data-ttu-id="b9ac2-113">Esses componentes são instalados automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="b9ac2-114">Se você deseja que os chamadores ouçam música enquanto a chamada estiver estacionada, um arquivo de música em espera também é necessário.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="b9ac2-115">Um arquivo de música em espera padrão é instalado automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b9ac2-116">É possível substituir o arquivo padrão com seu próprio arquivo de música em espera.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="b9ac2-117">O estacionamento de chamada usa o repositório de arquivos para armazenar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="b9ac2-118">Direitos do usuário de configuração do estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="b9ac2-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="b9ac2-119">Você pode usar as seguintes ferramentas administrativas para configurar o estacionamento de chamada:</span><span class="sxs-lookup"><span data-stu-id="b9ac2-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="b9ac2-120">Painel de Controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="b9ac2-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="b9ac2-121">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="b9ac2-121">Lync Server Management Shell</span></span>

<span data-ttu-id="b9ac2-122">Use essas ferramentas para configurar a tabela de órbita de estacionamento de chamadas e para definir outras configurações usadas pelo estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="b9ac2-123">A configuração do estacionamento de chamadas exige qualquer uma das funções administrativas a seguir, dependendo da tarefa:</span><span class="sxs-lookup"><span data-stu-id="b9ac2-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="b9ac2-124">**CsVoiceAdministrator:** Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="b9ac2-125">**CsUserAdministrator:** Essa função de administrador pode habilitar o estacionamento de chamada na política de voz.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="b9ac2-126">Esta função de administração também pode ter acesso de exibição somente leitura para todas as configurações de voz.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="b9ac2-127">**CsServerAdministrator:** Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="b9ac2-128">**CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9ac2-129">Para obter detalhes sobre os direitos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="b9ac2-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9ac2-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9ac2-130">See Also</span></span>


[<span data-ttu-id="b9ac2-131">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9ac2-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="b9ac2-132">Planejamento de recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9ac2-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

