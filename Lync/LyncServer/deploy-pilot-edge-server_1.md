---
title: Implantar servidor de borda piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cbf3be6dd47f794768ba0f3c8140e7124a1cabb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="75304-102">Implantar servidor de borda piloto</span><span class="sxs-lookup"><span data-stu-id="75304-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75304-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="75304-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="75304-104">Este tópico destaca as definições de configuração que você deve estar ciente antes da implantação do servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75304-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="75304-105">Esta seção destaca somente os principais pontos a serem considerados como parte da implantação do seu pool de Borda piloto.</span><span class="sxs-lookup"><span data-stu-id="75304-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="75304-106">Para obter etapas detalhadas, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="75304-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="75304-p102">Conforme você navega pelo assistente **Definir Novo Pool de Borda**, reveja as principais definições de configuração exibidas nas etapas a seguir. Observe que somente algumas páginas do assistente **Definir Novo Pool de Borda** são mostradas.</span><span class="sxs-lookup"><span data-stu-id="75304-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="75304-109">**Definir um Pool de Borda**</span><span class="sxs-lookup"><span data-stu-id="75304-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="75304-110">Abra a topologia do pool piloto usando o Construtor de Topologia</span><span class="sxs-lookup"><span data-stu-id="75304-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="75304-111">Navegue até o nó do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75304-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="75304-112">Clique com o botão direito em **Pools de borda** e clique em **Novo pool de borda**.</span><span class="sxs-lookup"><span data-stu-id="75304-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="75304-113">![Caixa de diálogo Definir novo pool de borda](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda")</span><span class="sxs-lookup"><span data-stu-id="75304-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="75304-114">Um pool de Borda pode ser um **Pool de vários computadores** ou **Pool de computador único**.</span><span class="sxs-lookup"><span data-stu-id="75304-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="75304-115">![Caixa de diálogo definir o FQDN do pool de borda](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Caixa de diálogo definir o FQDN do pool de borda")</span><span class="sxs-lookup"><span data-stu-id="75304-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="75304-116">Na página **Selecionar recursos**, não habilite a federação ou a federação XMPP.</span><span class="sxs-lookup"><span data-stu-id="75304-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="75304-117">Atualmente, a Federação e a Federação do XMPP são roteadas através do servidor de borda herdado do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="75304-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="75304-118">Estes recursos são configurados em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="75304-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="75304-119">![Caixa de diálogo Selecionar recursos](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Caixa de diálogo Selecionar recursos")</span><span class="sxs-lookup"><span data-stu-id="75304-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="75304-120">Em seguida, continue preenchendo as seguintes páginas do assistente: **Selecionar opções de IP**, **FQDNs Externos**, **Definir um endereço IP interno** e **Definir um endereço IP externo**.</span><span class="sxs-lookup"><span data-stu-id="75304-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="75304-121">Na página **definir o próximo salto** , selecione o diretor do próximo salto do pool de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75304-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="75304-122">![Caixa de diálogo Definir novo pool de borda, lista de pool de próximo salto](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda, lista de pool de próximo salto")</span><span class="sxs-lookup"><span data-stu-id="75304-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="75304-123">Na página **associar pools de front-ends** , não associe um pool a este pool de borda neste momento.</span><span class="sxs-lookup"><span data-stu-id="75304-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="75304-124">No momento, o tráfego de mídia externo é roteado através do servidor de borda do Office Communications Server 2007 R2 herdado.</span><span class="sxs-lookup"><span data-stu-id="75304-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="75304-125">Esta definição será configurada em uma fase posterior de migração.</span><span class="sxs-lookup"><span data-stu-id="75304-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="75304-126">![Caixa de diálogo Definir novo pool de borda](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda")</span><span class="sxs-lookup"><span data-stu-id="75304-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="75304-127">Clique em **Concluir** e **Publique** a topologia.</span><span class="sxs-lookup"><span data-stu-id="75304-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="75304-128">Siga as etapas em [instalar servidores de borda para o Lync Server 2013](lync-server-2013-install-edge-servers.md) na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="75304-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="75304-129">É muito importante que você siga as diretrizes nos tópicos que [implantam o acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="75304-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="75304-130">Esta seção forneceu somente algumas informações sobre definições de configuração ao instalar estas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="75304-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="75304-131">Agora você deve ter uma implantação herdada do servidor de borda do Office Communications Server 2007 R2, indicada pela presença do BackCompatSite, em paralelo com uma implantação do servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75304-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="75304-132">A Federação é configurada para usar o diretor do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="75304-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="75304-133">Verifique se ambas as implantações estão em execução adequadamente, se os serviços foram iniciados e se é possível administrar cada implantação antes de seguir para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="75304-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="75304-134">![Construtor de topologia mostrando o servidor de borda do OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Construtor de topologia mostrando o servidor de borda do OCS")</span><span class="sxs-lookup"><span data-stu-id="75304-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

