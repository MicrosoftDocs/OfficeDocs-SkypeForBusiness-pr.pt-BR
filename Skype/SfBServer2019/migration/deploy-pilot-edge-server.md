---
title: Implantar um Servidor de Borda piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tópico destaca as definições de configuração, que você deve estar ciente antes de implantar sua Skype para o servidor de borda de 2019 Business Server. Os processos de implantação e configuração de Skype para Business Server 2019 serão bastante similares às Skype para Business Server 2015. Esta seção destaca somente os principais pontos que devem ser considerados como parte da sua implantação do pool piloto. Para obter etapas detalhadas, consulte Implantando o acesso de usuário externo em Skype for Business Server 2019 na documentação de implantação, que descreve o processo de implantação e também oferece informações de configuração de acesso de usuário externo.
ms.openlocfilehash: 5b755d0ba8802c47a176cb3375a87b6523f35fad
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876195"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="d8013-106">Implantar um Servidor de Borda piloto</span><span class="sxs-lookup"><span data-stu-id="d8013-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="d8013-107">Este tópico destaca as definições de configuração, que você deve estar ciente antes de implantar sua Skype para o servidor de borda de 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8013-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="d8013-108">Os processos de implantação e configuração de Skype para Business Server 2019 serão bastante similares às Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d8013-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="d8013-109">Esta seção destaca somente os principais pontos que devem ser considerados como parte da sua implantação do pool piloto.</span><span class="sxs-lookup"><span data-stu-id="d8013-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="d8013-110">Enquanto você navega por meio do assistente **Definir Novo Pool de borda** , examine as definições de configuração de chave mostradas nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d8013-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="d8013-111">Observe que apenas algumas páginas do assistente **Definir Novo Pool de borda** são mostradas.</span><span class="sxs-lookup"><span data-stu-id="d8013-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="d8013-112">Para definir um Pool de borda</span><span class="sxs-lookup"><span data-stu-id="d8013-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="d8013-113">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d8013-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="d8013-114">Navegue até o Skype para Business Server 2019 nó.</span><span class="sxs-lookup"><span data-stu-id="d8013-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="d8013-115">Clique com o botão **pools de borda**e clique em **novo pool de borda**.</span><span class="sxs-lookup"><span data-stu-id="d8013-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Definir a caixa de diálogo Novo Pool de borda](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="d8013-117">Um pool de borda pode ser um **pool de vários computadores** ou **pool de computador único**.</span><span class="sxs-lookup"><span data-stu-id="d8013-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Definir a caixa de diálogo de FQDN do Pool de borda](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="d8013-119">Na página **Selecionar recursos** , não ative federação ou a federação XMPP.</span><span class="sxs-lookup"><span data-stu-id="d8013-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="d8013-120">Federação e federação XMPP são ambos atualmente roteadas pelo servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="d8013-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="d8013-121">Esses recursos serão configurados em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="d8013-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="d8013-122">Continue preenchendo as seguintes páginas do assistente: **FQDNs externos**, **definir o endereço IP interno**e **definir o endereço IP externo**.</span><span class="sxs-lookup"><span data-stu-id="d8013-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="d8013-123">Na página **definir o servidor de próximo salto** , selecione o diretor para o próximo salto do pool de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="d8013-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Definir a caixa de diálogo de próximo salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="d8013-125">Na página **associar Front-End ou pools de mediação** , não associe um pool com este pool de borda neste momento.</span><span class="sxs-lookup"><span data-stu-id="d8013-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="d8013-126">Atualmente, o tráfego de mídia externa é roteado por meio do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="d8013-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="d8013-127">Essa configuração será configurada em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="d8013-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Caixa de diálogo Associar Pools de Front-End](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="d8013-129">Clique em **Concluir**e, em seguida, **Publicar** a topologia.</span><span class="sxs-lookup"><span data-stu-id="d8013-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="d8013-130">Siga as etapas na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="d8013-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="d8013-131">É muito importante que você siga as diretrizes nos tópicos na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="d8013-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="d8013-132">Esta seção forneceu meramente algumas diretrizes nas definições de configuração ao instalar essas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="d8013-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="d8013-133">Agora, você deve ter um servidor de borda herdado implantado em paralelo com uma Skype para implantação de servidor de borda de 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8013-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="d8013-134">Verificar se as implantações estão em execução adequadamente, serviços foram iniciados e você pode administrar cada implantação antes de mover para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="d8013-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

