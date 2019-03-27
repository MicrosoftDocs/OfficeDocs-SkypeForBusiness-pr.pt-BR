---
title: Verifique se o ambiente de legado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implantar o Skype para negócios 2019 de servidor em um estado de coexistência, você precisará verificar se os serviços de legado foi configurados e iniciados. É importante identificar os principais serviços e recursos que existem no seu ambiente herdado, antes de implantar um Skype para o pool piloto Business Server 2019. Antes de implantar o Microsoft Skype para Business Server 2019 XMPP em um estado de coexistência com uma implantação de XMPP herdado, você precisa verificar se os serviços XMPP herdados foram configurados e iniciados e identifique qual parceiro federado é a configuração de XMPP herdado dando suporte.
ms.openlocfilehash: 0f9812efe966d72eba1eeead9d74780f2ba16661
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887343"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="a4b63-105">Verificar o ambiente de legado</span><span class="sxs-lookup"><span data-stu-id="a4b63-105">Verify the legacy environment</span></span>

<span data-ttu-id="a4b63-106">Antes de implantar o Skype para negócios 2019 de servidor em um estado de coexistência, você precisará verificar se os serviços de legado foi configurados e iniciados.</span><span class="sxs-lookup"><span data-stu-id="a4b63-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="a4b63-107">É importante identificar os principais serviços e recursos que existem no seu ambiente herdado antes de implantar um Skype para o pool piloto Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a4b63-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="a4b63-108">Antes de implantar o Microsoft Skype para Business Server 2019 XMPP em um estado de coexistência com uma implantação de XMPP herdado, você precisa verificar se os serviços XMPP herdados foram configurados e foram iniciados e identificar quais federados parceiro XMPP herdado suporte a configuração.</span><span class="sxs-lookup"><span data-stu-id="a4b63-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="a4b63-109">Verificando a implantação herdada envolve o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a4b63-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="a4b63-110">Verificando se os serviços de legado foram iniciados</span><span class="sxs-lookup"><span data-stu-id="a4b63-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="a4b63-111">Analisando a topologia e os usuários</span><span class="sxs-lookup"><span data-stu-id="a4b63-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="a4b63-112">Verificando a federação e as configurações do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a4b63-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="a4b63-113">Verificando serviços XMPP e parceiros federados</span><span class="sxs-lookup"><span data-stu-id="a4b63-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="a4b63-114">Verificar se os serviços legados foram iniciados</span><span class="sxs-lookup"><span data-stu-id="a4b63-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="a4b63-115">No herdado servidor Front-End, navegue até o applet ferramentas administrativas \ Serviços.</span><span class="sxs-lookup"><span data-stu-id="a4b63-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="a4b63-116">Verifique se os seguintes serviços estão funcionando no servidor Front-End:</span><span class="sxs-lookup"><span data-stu-id="a4b63-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Lista de serviços em execução no servidor Front-End](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a4b63-118">Revise a topologia herdada no Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="a4b63-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a4b63-119">Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a4b63-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="a4b63-120">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a4b63-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a4b63-121">Selecione a **topologia**.</span><span class="sxs-lookup"><span data-stu-id="a4b63-121">Select **Topology**.</span></span> <span data-ttu-id="a4b63-122">Verificar se os vários servidores em sua implantação herdada estão listados.</span><span class="sxs-lookup"><span data-stu-id="a4b63-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Página de topologia do painel de controle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a4b63-124">Revise os usuários herdados do Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="a4b63-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a4b63-125">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a4b63-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="a4b63-126">Selecione **usuários**e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="a4b63-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="a4b63-127">Verifique se a coluna **Pool do registrador** aponta para o pool herdado para cada usuário listado.</span><span class="sxs-lookup"><span data-stu-id="a4b63-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Listar usuários do painel de controle](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="a4b63-129">Verificar as configurações de borda e federação de legado</span><span class="sxs-lookup"><span data-stu-id="a4b63-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="a4b63-130">Inicie o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="a4b63-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="a4b63-131">Selecione **Baixar topologia da implantação existente**.</span><span class="sxs-lookup"><span data-stu-id="a4b63-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="a4b63-132">Escolha um nome de arquivo e salve a topologia com o tipo de arquivo. tbxml padrão.</span><span class="sxs-lookup"><span data-stu-id="a4b63-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="a4b63-133">Expanda o nó de instalações herdadas para revelar várias funções de servidor na implantação.</span><span class="sxs-lookup"><span data-stu-id="a4b63-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="a4b63-134">Selecione o nó do site e verificar se um valor de **atribuição de rota de federação local** está definido.</span><span class="sxs-lookup"><span data-stu-id="a4b63-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Construtor de topologias, rota de Federação do Site](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="a4b63-136">Selecione o pool de front-end do servidor Standard Edition ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a4b63-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="a4b63-137">Determine se um pool de borda foi configurado para a mídia abaixo **associações**.</span><span class="sxs-lookup"><span data-stu-id="a4b63-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Construtor de topologia mostrando servidores e pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="a4b63-139">Selecione o pool de borda e identifique se um pool de próximo salto está configurado abaixo de **seleção do próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="a4b63-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Construtor de topologias, seleção do próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="a4b63-141">Verifique se o parceiro federado de XMPP herdado configuração</span><span class="sxs-lookup"><span data-stu-id="a4b63-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="a4b63-142">No servidor XMPP legado, navegue até o applet ferramentas administrativas \ Serviços.</span><span class="sxs-lookup"><span data-stu-id="a4b63-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="a4b63-143">Verifique se o serviço de Gateway XMPP do Office Communications Server é iniciado.</span><span class="sxs-lookup"><span data-stu-id="a4b63-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Serviço de Gateway XMPP do Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

