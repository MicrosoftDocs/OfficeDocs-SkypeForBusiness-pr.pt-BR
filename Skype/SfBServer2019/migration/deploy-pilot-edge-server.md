---
title: Implantar um Servidor de Borda piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tópico destaca as configurações de configuração das quais você deve estar ciente antes de implantar seu servidor de borda do Skype for Business Server 2019. Os processos de implantação e configuração do Skype for Business Server 2019 são muito semelhantes ao Skype for Business Server 2015. Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto. Para obter etapas detalhadas, consulte Implantando o acesso de usuários externos no Skype for Business Server 2019 na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para o acesso de usuários externos.
ms.openlocfilehash: f692eb5ad4a24b47a8bab7a56be218eab04af7dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280914"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="145fe-106">Implantar um Servidor de Borda piloto</span><span class="sxs-lookup"><span data-stu-id="145fe-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="145fe-107">Este tópico destaca as configurações de configuração das quais você deve estar ciente antes de implantar seu servidor de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="145fe-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="145fe-108">Os processos de implantação e configuração do Skype for Business Server 2019 são muito semelhantes ao Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="145fe-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="145fe-109">Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto.</span><span class="sxs-lookup"><span data-stu-id="145fe-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="145fe-110">Ao navegar pelo assistente **definir novo pool de borda** , examine as configurações de chave de configuração mostradas nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="145fe-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="145fe-111">Observe que apenas algumas páginas do assistente para **definir novo pool de borda** são mostradas.</span><span class="sxs-lookup"><span data-stu-id="145fe-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="145fe-112">Para definir um pool de bordas</span><span class="sxs-lookup"><span data-stu-id="145fe-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="145fe-113">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="145fe-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="145fe-114">Navegue até o nó Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="145fe-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="145fe-115">Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.</span><span class="sxs-lookup"><span data-stu-id="145fe-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Definir a caixa de diálogo novo pool de bordas](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="145fe-117">Um pool de bordas pode ser um **pool de vários computadores** ou um **único pool de computadores**.</span><span class="sxs-lookup"><span data-stu-id="145fe-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Definir a caixa de diálogo FQDN do pool de bordas](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="145fe-119">Na página **selecionar recursos** , não habilite Federação ou Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="145fe-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="145fe-120">A Federação e a Federação do XMPP são roteadas atualmente por meio do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="145fe-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="145fe-121">Esses recursos serão configurados em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="145fe-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="145fe-122">Continue a concluir as seguintes páginas do assistente: **FQDNs externos**, **defina o endereço IP interno**e **defina o endereço IP externo**.</span><span class="sxs-lookup"><span data-stu-id="145fe-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="145fe-123">Na página **definir o servidor de salto seguinte** , selecione o diretor para o próximo nó do pool de bordas herdado.</span><span class="sxs-lookup"><span data-stu-id="145fe-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Definir a caixa de diálogo salto seguinte](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="145fe-125">Na página **associar front-end ou pool** de mediação, não associe um pool a este pool de bordas no momento.</span><span class="sxs-lookup"><span data-stu-id="145fe-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="145fe-126">No momento, o tráfego de mídia externo é roteado pelo servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="145fe-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="145fe-127">Essa configuração será configurada em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="145fe-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Caixa de diálogo associar grupos de front-end](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="145fe-129">Clique em **concluir**e **publique** a topologia.</span><span class="sxs-lookup"><span data-stu-id="145fe-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="145fe-130">Siga as etapas na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="145fe-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="145fe-131">É muito importante que você siga as diretrizes nos tópicos da documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="145fe-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="145fe-132">Esta seção simplesmente forneceu algumas diretrizes sobre as definições de configuração durante a instalação dessas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="145fe-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="145fe-133">Agora você deve ter um servidor de borda herdado implantado em paralelo com uma implantação do servidor de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="145fe-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="145fe-134">Verifique se as duas implantações estão funcionando corretamente, se os serviços foram iniciados e você pode administrar cada implantação antes de passar para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="145fe-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

