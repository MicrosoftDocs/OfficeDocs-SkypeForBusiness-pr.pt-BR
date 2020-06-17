---
title: Implantar um Servidor de Borda piloto
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
description: Este tópico destaca as definições de configuração que você deve estar ciente antes da implantação do servidor de borda do Skype for Business Server 2019. Os processos de implantação e configuração do Skype for Business Server 2019 são muito semelhantes ao Skype for Business Server 2015. Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto. Para obter etapas detalhadas, consulte Deploying external User Access in Skype for Business Server 2019 na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para acesso de usuário externo.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752863"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="3d7dc-106">Implantar um Servidor de Borda piloto</span><span class="sxs-lookup"><span data-stu-id="3d7dc-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="3d7dc-107">Este tópico realça as definições de configuração que você deve estar ciente antes de implantar seu servidor de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="3d7dc-108">Os processos de implantação e configuração do Skype for Business Server 2019 são muito semelhantes ao Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="3d7dc-109">Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="3d7dc-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="3d7dc-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="3d7dc-112">Para definir um pool de borda</span><span class="sxs-lookup"><span data-stu-id="3d7dc-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="3d7dc-113">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="3d7dc-114">Navegue até o nó do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="3d7dc-115">Clique com o botão direito em **Pools de borda** e clique em **Novo pool de borda**.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Caixa de diálogo Definir novo pool de borda](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="3d7dc-117">Um pool de Borda pode ser um **Pool de vários computadores** ou **Pool de computador único**.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Caixa de diálogo definir o FQDN do pool de borda](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="3d7dc-119">Na página **Selecionar recursos**, não habilite a federação ou a federação XMPP.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="3d7dc-120">A Federação e a Federação XMPP são roteadas atualmente através do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="3d7dc-121">Estes recursos são configurados em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="3d7dc-122">Continue preenchendo as seguintes páginas do assistente: **FQDNs externos**, **defina o endereço IP interno**e **defina o endereço IP externo**.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="3d7dc-123">Na página **definir o servidor de próximo salto** , selecione o diretor para o próximo salto do pool de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Caixa de diálogo Definir próximo salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="3d7dc-125">Na página **associar pools de front-ends ou de mediação** , não associe um pool a este pool de borda neste momento.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="3d7dc-126">No momento, o tráfego de mídia externo é roteado através do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="3d7dc-127">Esta definição será configurada em uma fase posterior de migração.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Caixa de diálogo associar pools de front-ends](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="3d7dc-129">Clique em **concluir**e **publique** a topologia.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="3d7dc-130">Siga as etapas na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="3d7dc-131">É muito importante que você siga as diretrizes nos tópicos da documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="3d7dc-132">Esta seção forneceu somente algumas informações sobre definições de configuração ao instalar estas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="3d7dc-133">Agora você deve ter um servidor de borda herdado implantado em paralelo com uma implantação do servidor de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="3d7dc-134">Verifique se ambas as implantações estão em execução adequadamente, se os serviços foram iniciados e se você pode administrar cada implantação antes de seguir para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="3d7dc-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

