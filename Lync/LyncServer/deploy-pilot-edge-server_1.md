---
title: Implantar um Servidor de Borda piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="a0c4f-102">Implantar um Servidor de Borda piloto</span><span class="sxs-lookup"><span data-stu-id="a0c4f-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0c4f-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a0c4f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a0c4f-104">Este tópico destaca as configurações de configuração das quais você deve estar ciente antes de implantar seu servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="a0c4f-105">Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação do pool de bordas piloto.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="a0c4f-106">Para obter etapas detalhadas, consulte Implantando o [acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para o acesso de usuários externos.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="a0c4f-107">Ao navegar pelo assistente **definir novo pool de borda** , examine as configurações de chave de configuração mostradas nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="a0c4f-108">Observe que apenas algumas páginas do assistente para **definir novo pool de borda** são mostradas.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="a0c4f-109">**Definir um pool de bordas**</span><span class="sxs-lookup"><span data-stu-id="a0c4f-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="a0c4f-110">Abra a topologia do pool piloto usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="a0c4f-111">Navegue até o nó do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="a0c4f-112">Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="a0c4f-113">![Definir a caixa de diálogo novo pool de bordas] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir a caixa de diálogo novo pool de bordas")</span><span class="sxs-lookup"><span data-stu-id="a0c4f-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="a0c4f-114">Um pool de bordas pode ser um **pool de vários computadores** ou um **único pool de computadores**.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="a0c4f-115">![Definir a caixa de diálogo FQDN do pool de bordas] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definir a caixa de diálogo FQDN do pool de bordas")</span><span class="sxs-lookup"><span data-stu-id="a0c4f-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="a0c4f-116">Na página **selecionar recursos** , não habilite Federação ou Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="a0c4f-117">Atualmente, a Federação e a Federação do XMPP são roteadas por meio do servidor de borda herdado do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="a0c4f-118">Esses recursos serão configurados em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="a0c4f-119">![Caixa de diálogo Selecionar recursos] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Caixa de diálogo Selecionar recursos")</span><span class="sxs-lookup"><span data-stu-id="a0c4f-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="a0c4f-120">Em seguida, continue a concluir as seguintes páginas do assistente: **selecione opções de IP**, **FQDNs externos**, **defina o endereço IP interno**e **defina o endereço IP externo**.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="a0c4f-121">Na página **definir o próximo salto** , selecione o diretor do próximo nó do pool de bordas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="a0c4f-122">![Caixa de diálogo Definir novo pool de borda, próxima lista de pools de saltos] (images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda, próxima lista de pools de saltos")</span><span class="sxs-lookup"><span data-stu-id="a0c4f-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="a0c4f-123">Na página **associar pools de front-end** , não associe um pool a este pool de bordas no momento.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="a0c4f-124">O tráfego de mídia externo está atualmente roteado por meio do servidor de borda do Office Communications Server 2007 R2 herdado.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="a0c4f-125">Essa configuração será configurada em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="a0c4f-126">![Caixa de diálogo Definir novo pool de bordas] (images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Caixa de diálogo Definir novo pool de bordas")</span><span class="sxs-lookup"><span data-stu-id="a0c4f-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="a0c4f-127">Clique em **concluir** e **publique** a topologia.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="a0c4f-128">Siga as etapas em [instalar servidores de borda para o Lync server 2013](lync-server-2013-install-edge-servers.md) na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="a0c4f-129">É muito importante que você siga as diretrizes nos tópicos implantando o [acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="a0c4f-130">Esta seção simplesmente forneceu algumas diretrizes sobre as definições de configuração durante a instalação dessas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="a0c4f-131">Agora você deve ter uma implantação herdada do servidor de borda do Office Communications Server 2007 R2, indicada pela presença do BackCompatSite, em paralelo com uma implantação do servidor de borda 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="a0c4f-132">A Federação está configurada para usar o diretor do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="a0c4f-133">Verifique se as duas implantações estão funcionando corretamente, se os serviços foram iniciados e você pode administrar cada implantação antes de passar para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="a0c4f-134">![Construtor de topologias mostrando o servidor de borda do OCS] (images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Construtor de topologias mostrando o servidor de borda do OCS")</span><span class="sxs-lookup"><span data-stu-id="a0c4f-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

