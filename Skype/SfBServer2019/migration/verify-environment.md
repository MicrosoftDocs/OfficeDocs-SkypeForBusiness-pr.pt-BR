---
title: Verificar o ambiente herdado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos existentes no seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identificar que parceiro federado a configuração XMPP herdada oferece suporte.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751673"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="43c0f-105">Verificar o ambiente herdado</span><span class="sxs-lookup"><span data-stu-id="43c0f-105">Verify the legacy environment</span></span>

<span data-ttu-id="43c0f-106">Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados.</span><span class="sxs-lookup"><span data-stu-id="43c0f-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="43c0f-107">É importante identificar os principais serviços e recursos existentes no seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="43c0f-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="43c0f-108">Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identificar o parceiro federado onde a configuração XMPP herdada oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="43c0f-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="43c0f-109">Verificar sua implantação herdada envolve o seguinte:</span><span class="sxs-lookup"><span data-stu-id="43c0f-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="43c0f-110">Verificando se os serviços herdados foram iniciados</span><span class="sxs-lookup"><span data-stu-id="43c0f-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="43c0f-111">Examinando a topologia e os usuários</span><span class="sxs-lookup"><span data-stu-id="43c0f-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="43c0f-112">Verificar as configurações de Federação e servidor de borda</span><span class="sxs-lookup"><span data-stu-id="43c0f-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="43c0f-113">Verificando os serviços XMPP e parceiros federados</span><span class="sxs-lookup"><span data-stu-id="43c0f-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="43c0f-114">Verificar se os serviços herdados foram iniciados</span><span class="sxs-lookup"><span data-stu-id="43c0f-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="43c0f-115">No servidor de front-end herdado, navegue até o mini-aplicativo applet administrativo.</span><span class="sxs-lookup"><span data-stu-id="43c0f-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="43c0f-116">Verifique se os serviços a seguir estão sendo executados no servidor Front End:</span><span class="sxs-lookup"><span data-stu-id="43c0f-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Lista de serviços em execução no servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="43c0f-118">Examinar a topologia herdada no painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="43c0f-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="43c0f-119">Faça o logon no Servidor Front-End com uma conta que seja membro do grupo RTCUniversalServerAdmins ou que tenha a função administrativa CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="43c0f-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="43c0f-120">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43c0f-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="43c0f-121">Selecione **Topologia**.</span><span class="sxs-lookup"><span data-stu-id="43c0f-121">Select **Topology**.</span></span> <span data-ttu-id="43c0f-122">Verifique se os vários servidores em sua implantação herdada estão listados.</span><span class="sxs-lookup"><span data-stu-id="43c0f-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Página de topologia do painel de controle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="43c0f-124">Revisar usuários herdados no painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="43c0f-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="43c0f-125">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43c0f-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="43c0f-126">Selecione **usuários**e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="43c0f-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="43c0f-127">Verifique se a coluna **pool do registrador** aponta para o pool herdado para cada usuário listado.</span><span class="sxs-lookup"><span data-stu-id="43c0f-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Painel de controle listando usuários](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="43c0f-129">Verificar configurações de Federação e borda herdadas</span><span class="sxs-lookup"><span data-stu-id="43c0f-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="43c0f-130">Inicie o Construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="43c0f-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="43c0f-131">Selecione **Download da topologia de uma implantação existente**.</span><span class="sxs-lookup"><span data-stu-id="43c0f-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="43c0f-132">Escolha um nome de arquivo e salve a topologia com o tipo de arquivo default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="43c0f-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="43c0f-133">Expanda o nó instalações herdadas para revelar as várias funções de servidor na implantação.</span><span class="sxs-lookup"><span data-stu-id="43c0f-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="43c0f-134">Selecione o nó do site e verifique se um valor de **atribuição da rota de Federação do site** está definido.</span><span class="sxs-lookup"><span data-stu-id="43c0f-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Construtor de topologias, rota de Federação do site](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="43c0f-136">Selecione o servidor Standard Edition ou o pool de front-ends Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="43c0f-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="43c0f-137">Determinar se um pool de borda foi configurado para a mídia abaixo de **associações**.</span><span class="sxs-lookup"><span data-stu-id="43c0f-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Construtor de topologia mostrando servidores e pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="43c0f-139">Selecione o pool de borda e identifique se um pool de próximo salto está configurado abaixo da **seleção do próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="43c0f-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Construtor de topologias, seleção de próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="43c0f-141">Verificar a configuração de parceiro federado XMPP herdado</span><span class="sxs-lookup"><span data-stu-id="43c0f-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="43c0f-142">No servidor XMPP legado, navegue até o applet Ferramentas administrativas\Serviços.</span><span class="sxs-lookup"><span data-stu-id="43c0f-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="43c0f-143">Verifique se o serviço do Gateway XMPP do Office Communications Server foi inicializado.</span><span class="sxs-lookup"><span data-stu-id="43c0f-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Serviço de Gateway XMPP do Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

