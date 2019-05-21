---
title: Verificar o ambiente herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos que existem em seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identifica qual parceiro federado a configuração de XMPP herdada é support.
ms.openlocfilehash: 9495c68085f3fc3495d4c2ced05be8b20039eb4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280657"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="1786a-105">Verificar o ambiente herdado</span><span class="sxs-lookup"><span data-stu-id="1786a-105">Verify the legacy environment</span></span>

<span data-ttu-id="1786a-106">Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados.</span><span class="sxs-lookup"><span data-stu-id="1786a-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="1786a-107">É importante identificar os principais serviços e recursos existentes em seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1786a-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="1786a-108">Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identificar qual parceiro federado a XMPP herdada a configuração tem suporte.</span><span class="sxs-lookup"><span data-stu-id="1786a-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="1786a-109">Verificar sua implantação herdada envolve o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1786a-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="1786a-110">Verificar se os serviços herdados foram iniciados</span><span class="sxs-lookup"><span data-stu-id="1786a-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="1786a-111">Revisando a topologia e os usuários</span><span class="sxs-lookup"><span data-stu-id="1786a-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="1786a-112">Verificando as configurações do servidor de Federação e de borda</span><span class="sxs-lookup"><span data-stu-id="1786a-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="1786a-113">Verificando os serviços do XMPP e parceiros federados</span><span class="sxs-lookup"><span data-stu-id="1786a-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="1786a-114">Verificar se os serviços herdados foram iniciados</span><span class="sxs-lookup"><span data-stu-id="1786a-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="1786a-115">No servidor front-end herdado, navegue até o applet de Tools\Services administrativo.</span><span class="sxs-lookup"><span data-stu-id="1786a-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="1786a-116">Verifique se os seguintes serviços estão em execução no servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="1786a-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Lista de serviços em execução no front-end Server](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="1786a-118">Examine a topologia herdada no painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1786a-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1786a-119">Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1786a-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="1786a-120">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1786a-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1786a-121">Selecione **topologia**.</span><span class="sxs-lookup"><span data-stu-id="1786a-121">Select **Topology**.</span></span> <span data-ttu-id="1786a-122">Verifique se os vários servidores na sua implantação herdada estão listados.</span><span class="sxs-lookup"><span data-stu-id="1786a-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Página de topologia do painel de controle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="1786a-124">Examine os usuários herdados no painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1786a-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1786a-125">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1786a-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1786a-126">Selecione **usuários**e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="1786a-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="1786a-127">Verifique se a coluna **pool** de registradores aponta para o pool herdado para cada usuário listado.</span><span class="sxs-lookup"><span data-stu-id="1786a-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Listar usuários do painel de controle](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="1786a-129">Verificar as configurações de borda e de Federação herdadas</span><span class="sxs-lookup"><span data-stu-id="1786a-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="1786a-130">Iniciar o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="1786a-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="1786a-131">Selecione **baixar a topologia na implantação existente**.</span><span class="sxs-lookup"><span data-stu-id="1786a-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="1786a-132">Escolha um nome de arquivo e salve a topologia com o tipo de arquivo default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="1786a-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="1786a-133">Expanda o nó instalações herdadas para revelar as várias funções de servidor na implantação.</span><span class="sxs-lookup"><span data-stu-id="1786a-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="1786a-134">Selecione o nó do site e verifique se um valor de **atribuição da rota de Federação do site** está definido.</span><span class="sxs-lookup"><span data-stu-id="1786a-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Construtor de topologias, roteiro de Federação do site](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="1786a-136">Selecione o servidor Standard Edition ou o pool Front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1786a-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="1786a-137">Determine se um pool de bordas foi configurado para mídia abaixo de **associações**.</span><span class="sxs-lookup"><span data-stu-id="1786a-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Construtor de topologias mostrando servidores e pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="1786a-139">Selecione o pool de bordas e identifique se um próximo pool de saltos está configurado abaixo da **próxima seleção de salto**.</span><span class="sxs-lookup"><span data-stu-id="1786a-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Construtor de topologias, seleção do próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="1786a-141">Verificar a configuração de parceiro federado do XMPP herdado</span><span class="sxs-lookup"><span data-stu-id="1786a-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="1786a-142">No servidor herdado XMPP, navegue até o applet administrador Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="1786a-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="1786a-143">Verifique se o serviço do Gateway XMPP do Office Communications Server foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="1786a-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Serviço de Gateway XMPP do Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

