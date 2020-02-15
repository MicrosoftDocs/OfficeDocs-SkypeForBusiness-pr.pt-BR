---
title: Implantar servidor de borda piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2227e4ca38039b60d9ef26c25bfe11c3cc7fff6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="cffc3-102">Implantar servidor de borda piloto</span><span class="sxs-lookup"><span data-stu-id="cffc3-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cffc3-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="cffc3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="cffc3-104">Este tópico destaca as definições de configuração que você deve estar ciente antes da implantação do servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cffc3-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="cffc3-105">Os processos de implantação e configuração do Lync Server 2013 são muito semelhantes aos do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cffc3-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="cffc3-106">Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto.</span><span class="sxs-lookup"><span data-stu-id="cffc3-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="cffc3-107">Para obter etapas detalhadas, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="cffc3-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="cffc3-p102">Conforme você navega pelo assistente **Definir Novo Pool de Borda**, reveja as principais definições de configuração exibidas nas etapas a seguir. Observe que somente algumas páginas do assistente **Definir Novo Pool de Borda** são mostradas.</span><span class="sxs-lookup"><span data-stu-id="cffc3-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="cffc3-110">**Definir um Pool de Borda**</span><span class="sxs-lookup"><span data-stu-id="cffc3-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="cffc3-111">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cffc3-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="cffc3-112">Navegue até o nó do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cffc3-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="cffc3-113">Clique com o botão direito em **Pools de borda** e clique em **Novo pool de borda**.</span><span class="sxs-lookup"><span data-stu-id="cffc3-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="cffc3-114">![Caixa de diálogo Definir novo pool de borda](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda")</span><span class="sxs-lookup"><span data-stu-id="cffc3-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="cffc3-115">Um pool de Borda pode ser um **Pool de vários computadores** ou **Pool de computador único**.</span><span class="sxs-lookup"><span data-stu-id="cffc3-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="cffc3-116">![Caixa de diálogo definir o FQDN do pool de borda](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Caixa de diálogo definir o FQDN do pool de borda")</span><span class="sxs-lookup"><span data-stu-id="cffc3-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="cffc3-117">Na página **Selecionar recursos**, não habilite a federação ou a federação XMPP.</span><span class="sxs-lookup"><span data-stu-id="cffc3-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="cffc3-118">A Federação e a Federação XMPP são roteadas atualmente através do servidor de borda do Lync Server 2010 herdado.</span><span class="sxs-lookup"><span data-stu-id="cffc3-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="cffc3-119">Estes recursos são configurados em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="cffc3-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="cffc3-120">![Caixa de diálogo Selecionar recursos](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Caixa de diálogo Selecionar recursos")</span><span class="sxs-lookup"><span data-stu-id="cffc3-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="cffc3-121">Em seguida, continue preenchendo as seguintes páginas do assistente: **FQDN's Externos**, **Definir o endereço IP interno** e **Definir o endereço IP externo**.</span><span class="sxs-lookup"><span data-stu-id="cffc3-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="cffc3-122">Na página **definir o próximo salto** , selecione o diretor do próximo salto do pool de borda do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cffc3-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="cffc3-123">![Caixa de diálogo Definir próximo salto](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Caixa de diálogo Definir próximo salto")</span><span class="sxs-lookup"><span data-stu-id="cffc3-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="cffc3-124">Na página **associar pools de front-ends ou de mediação** , não associe um pool a este pool de borda neste momento.</span><span class="sxs-lookup"><span data-stu-id="cffc3-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="cffc3-125">No momento, o tráfego de mídia externo é roteado através do servidor de borda do Lync Server 2010 herdado.</span><span class="sxs-lookup"><span data-stu-id="cffc3-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="cffc3-126">Esta definição será configurada em uma fase posterior de migração.</span><span class="sxs-lookup"><span data-stu-id="cffc3-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="cffc3-127">![Caixa de diálogo associar pools de front-ends](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Caixa de diálogo associar pools de front-ends")</span><span class="sxs-lookup"><span data-stu-id="cffc3-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="cffc3-128">Clique em **Concluir** e **Publique** a topologia.</span><span class="sxs-lookup"><span data-stu-id="cffc3-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="cffc3-129">Siga as etapas em [instalar servidores de borda para o Lync Server 2013](lync-server-2013-install-edge-servers.md) na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="cffc3-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="cffc3-130">É muito importante que você siga as diretrizes nos tópicos que [implantam o acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="cffc3-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="cffc3-131">Esta seção forneceu somente algumas informações sobre definições de configuração ao instalar estas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="cffc3-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="cffc3-132">Agora você deve ter um servidor de borda do Lync Server 2010 herdado implantado em paralelo com uma implantação do servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cffc3-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="cffc3-133">Verifique se ambas as implantações estão em execução adequadamente, se os serviços foram iniciados e se é possível administrar cada implantação antes de seguir para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="cffc3-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

