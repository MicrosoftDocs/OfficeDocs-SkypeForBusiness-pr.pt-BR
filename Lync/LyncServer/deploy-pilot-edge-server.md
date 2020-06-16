---
title: Implantar um Servidor de Borda piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba616f6a5ce86e0f94c3b52afd60aaba34b7635
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="6b93a-102">Implantar um Servidor de Borda piloto</span><span class="sxs-lookup"><span data-stu-id="6b93a-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b93a-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6b93a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6b93a-104">Este tópico destaca as definições de configuração que você deve estar ciente antes da implantação do servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b93a-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="6b93a-105">Os processos de implantação e configuração do Lync Server 2013 são muito semelhantes aos do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6b93a-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="6b93a-106">Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto.</span><span class="sxs-lookup"><span data-stu-id="6b93a-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="6b93a-107">Para obter etapas detalhadas, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="6b93a-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="6b93a-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span><span class="sxs-lookup"><span data-stu-id="6b93a-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="6b93a-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span><span class="sxs-lookup"><span data-stu-id="6b93a-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="6b93a-110">**Definir um Pool de Borda**</span><span class="sxs-lookup"><span data-stu-id="6b93a-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="6b93a-111">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6b93a-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="6b93a-112">Navegue até o nó do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b93a-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="6b93a-113">Clique com o botão direito em **Pools de borda** e clique em **Novo pool de borda**.</span><span class="sxs-lookup"><span data-stu-id="6b93a-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="6b93a-114">![Caixa de diálogo Definir novo pool de borda](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda")</span><span class="sxs-lookup"><span data-stu-id="6b93a-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="6b93a-115">Um pool de Borda pode ser um **Pool de vários computadores** ou **Pool de computador único**.</span><span class="sxs-lookup"><span data-stu-id="6b93a-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="6b93a-116">![Caixa de diálogo definir o FQDN do pool de borda](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Caixa de diálogo definir o FQDN do pool de borda")</span><span class="sxs-lookup"><span data-stu-id="6b93a-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="6b93a-117">Na página **Selecionar recursos**, não habilite a federação ou a federação XMPP.</span><span class="sxs-lookup"><span data-stu-id="6b93a-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="6b93a-118">A Federação e a Federação XMPP são roteadas atualmente através do servidor de borda do Lync Server 2010 herdado.</span><span class="sxs-lookup"><span data-stu-id="6b93a-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="6b93a-119">Estes recursos são configurados em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="6b93a-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="6b93a-120">![Caixa de diálogo Selecionar recursos](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Caixa de diálogo Selecionar recursos")</span><span class="sxs-lookup"><span data-stu-id="6b93a-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="6b93a-121">Em seguida, continue preenchendo as seguintes páginas do assistente: **FQDN's Externos**, **Definir o endereço IP interno** e **Definir o endereço IP externo**.</span><span class="sxs-lookup"><span data-stu-id="6b93a-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="6b93a-122">Na página **definir o próximo salto** , selecione o diretor do próximo salto do pool de borda do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6b93a-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="6b93a-123">![Caixa de diálogo Definir próximo salto](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Caixa de diálogo Definir próximo salto")</span><span class="sxs-lookup"><span data-stu-id="6b93a-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="6b93a-124">Na página **associar pools de front-ends ou de mediação** , não associe um pool a este pool de borda neste momento.</span><span class="sxs-lookup"><span data-stu-id="6b93a-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="6b93a-125">No momento, o tráfego de mídia externo é roteado através do servidor de borda do Lync Server 2010 herdado.</span><span class="sxs-lookup"><span data-stu-id="6b93a-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="6b93a-126">Esta definição será configurada em uma fase posterior de migração.</span><span class="sxs-lookup"><span data-stu-id="6b93a-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="6b93a-127">![Caixa de diálogo associar pools de front-ends](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Caixa de diálogo associar pools de front-ends")</span><span class="sxs-lookup"><span data-stu-id="6b93a-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="6b93a-128">Clique em **Concluir** e **Publique** a topologia.</span><span class="sxs-lookup"><span data-stu-id="6b93a-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="6b93a-129">Siga as etapas em [instalar servidores de borda para o Lync Server 2013](lync-server-2013-install-edge-servers.md) na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="6b93a-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="6b93a-130">É muito importante que você siga as diretrizes nos tópicos que [implantam o acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6b93a-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="6b93a-131">Esta seção forneceu somente algumas informações sobre definições de configuração ao instalar estas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="6b93a-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="6b93a-132">Agora você deve ter um servidor de borda do Lync Server 2010 herdado implantado em paralelo com uma implantação do servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b93a-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="6b93a-133">Verifique se ambas as implantações estão em execução adequadamente, se os serviços foram iniciados e se é possível administrar cada implantação antes de seguir para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="6b93a-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

