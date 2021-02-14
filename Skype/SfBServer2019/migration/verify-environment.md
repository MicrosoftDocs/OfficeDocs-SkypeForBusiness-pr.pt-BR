---
title: Verificar o ambiente herddo
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
description: Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos existentes em seu ambiente herdado, antes de implantar um pool piloto do Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação XMPP herdada, você precisa verificar se os serviços XMPP herdados foram configurados e iniciados e identificar a qual parceiro federado a configuração XMPP herdada é suportada.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751673"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="f7573-105">Verificar o ambiente herddo</span><span class="sxs-lookup"><span data-stu-id="f7573-105">Verify the legacy environment</span></span>

<span data-ttu-id="f7573-106">Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados.</span><span class="sxs-lookup"><span data-stu-id="f7573-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="f7573-107">É importante identificar os principais serviços e recursos existentes em seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f7573-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="f7573-108">Antes de implantar o XMPP do Microsoft Skype for Business Server 2019 em um estado de coexistência com uma implantação XMPP herdada, você precisa verificar se os serviços XMPP herdados foram configurados e iniciados e identificar a qual parceiro federado a configuração XMPP herdada é suportada.</span><span class="sxs-lookup"><span data-stu-id="f7573-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="f7573-109">A verificação da implantação herdda envolve o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f7573-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="f7573-110">Verificando se os serviços herddos foram iniciados</span><span class="sxs-lookup"><span data-stu-id="f7573-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="f7573-111">Revendo a topologia e os usuários</span><span class="sxs-lookup"><span data-stu-id="f7573-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="f7573-112">Verificando as configurações do servidor de borda e federação</span><span class="sxs-lookup"><span data-stu-id="f7573-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="f7573-113">Verificando serviços XMPP e parceiros federados</span><span class="sxs-lookup"><span data-stu-id="f7573-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="f7573-114">Verificar se os serviços herddos foram iniciados</span><span class="sxs-lookup"><span data-stu-id="f7573-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="f7573-115">No Servidor front-end herddo, navegue até o applet Ferramentas Administrativas\Serviços.</span><span class="sxs-lookup"><span data-stu-id="f7573-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="f7573-116">Verifique se os serviços a seguir estão sendo executados no servidor Front End:</span><span class="sxs-lookup"><span data-stu-id="f7573-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Lista de serviços em execução no Servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="f7573-118">Revisar a topologia herdada no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f7573-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f7573-119">Faça o logon no Servidor Front-End com uma conta que seja membro do grupo RTCUniversalServerAdmins ou que tenha a função administrativa CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f7573-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="f7573-120">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7573-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f7573-121">Selecione **Topologia**.</span><span class="sxs-lookup"><span data-stu-id="f7573-121">Select **Topology**.</span></span> <span data-ttu-id="f7573-122">Verifique se os vários servidores em sua implantação herdada estão listados.</span><span class="sxs-lookup"><span data-stu-id="f7573-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Página de topologia do Painel de Controle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="f7573-124">Revisar usuários herdado no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f7573-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f7573-125">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7573-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="f7573-126">Selecione **Usuários** e clique em **Encontrar.**</span><span class="sxs-lookup"><span data-stu-id="f7573-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="f7573-127">Verifique se a coluna **Pool do Registrador** aponta para o pool herdado de cada usuário listado.</span><span class="sxs-lookup"><span data-stu-id="f7573-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Painel de Controle listando usuários](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="f7573-129">Verificar configurações de federação e borda herddas</span><span class="sxs-lookup"><span data-stu-id="f7573-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="f7573-130">Inicie o Construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="f7573-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="f7573-131">Selecione **Download da topologia de uma implantação existente**.</span><span class="sxs-lookup"><span data-stu-id="f7573-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="f7573-132">Escolha um nome de arquivo e salve a topologia com o tipo de arquivo .tbxml padrão.</span><span class="sxs-lookup"><span data-stu-id="f7573-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="f7573-133">Expanda o nó de instalação herdados para revelar as várias funções de servidor na implantação.</span><span class="sxs-lookup"><span data-stu-id="f7573-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="f7573-134">Selecione o nó do site e verifique se um valor de atribuição **de rota de federação** do site está definido.</span><span class="sxs-lookup"><span data-stu-id="f7573-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Construtor de Topologias, Rota de Federação do Site](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="f7573-136">Selecione o pool de front-end do Servidor Standard Edition ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f7573-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="f7573-137">Determine se um pool de Borda foi configurado para mídia abaixo **de Associações**.</span><span class="sxs-lookup"><span data-stu-id="f7573-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Construtor de Topologia mostrando servidores e pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="f7573-139">Selecione o pool de Borda e identifique se um pool de próximo salto está configurado abaixo da **seleção de próximo salto.**</span><span class="sxs-lookup"><span data-stu-id="f7573-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Construtor de Topologias, Seleção do próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="f7573-141">Verificar configuração de parceiro federado XMPP herdado</span><span class="sxs-lookup"><span data-stu-id="f7573-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="f7573-142">No servidor XMPP legado, navegue até o applet Ferramentas administrativas\Serviços.</span><span class="sxs-lookup"><span data-stu-id="f7573-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="f7573-143">Verifique se o serviço do Gateway XMPP do Office Communications Server foi inicializado.</span><span class="sxs-lookup"><span data-stu-id="f7573-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Serviço de Gateway XMPP do Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

