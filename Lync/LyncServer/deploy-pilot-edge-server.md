---
title: Implantar um Servidor de Borda piloto
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
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="6c33a-102">Implantar um Servidor de Borda piloto</span><span class="sxs-lookup"><span data-stu-id="6c33a-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c33a-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6c33a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6c33a-104">Este tópico destaca as configurações de configuração das quais você deve estar ciente antes de implantar seu servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c33a-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="6c33a-105">Os processos de implantação e configuração do Lync Server 2013 são muito semelhantes ao Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6c33a-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="6c33a-106">Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto.</span><span class="sxs-lookup"><span data-stu-id="6c33a-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="6c33a-107">Para obter etapas detalhadas, consulte [implantando o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para o acesso de usuários externos.</span><span class="sxs-lookup"><span data-stu-id="6c33a-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="6c33a-108">Ao navegar pelo assistente **definir novo pool de borda** , examine as configurações de chave de configuração mostradas nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c33a-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="6c33a-109">Observe que apenas algumas páginas do assistente para **definir novo pool de borda** são mostradas.</span><span class="sxs-lookup"><span data-stu-id="6c33a-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="6c33a-110">**Definir um pool de bordas**</span><span class="sxs-lookup"><span data-stu-id="6c33a-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="6c33a-111">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6c33a-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="6c33a-112">Navegue até o nó do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c33a-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="6c33a-113">Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.</span><span class="sxs-lookup"><span data-stu-id="6c33a-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="6c33a-114">![Definir a caixa de diálogo novo pool de bordas](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir a caixa de diálogo novo pool de bordas")</span><span class="sxs-lookup"><span data-stu-id="6c33a-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="6c33a-115">Um pool de bordas pode ser um **pool de vários computadores** ou um **único pool de computadores**.</span><span class="sxs-lookup"><span data-stu-id="6c33a-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="6c33a-116">![Definir a caixa de diálogo FQDN do pool de bordas](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definir a caixa de diálogo FQDN do pool de bordas")</span><span class="sxs-lookup"><span data-stu-id="6c33a-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="6c33a-117">Na página **selecionar recursos** , não habilite Federação ou Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="6c33a-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="6c33a-118">A Federação e a Federação do XMPP são roteadas atualmente por meio do servidor de borda do Lync Server 2010 herdado.</span><span class="sxs-lookup"><span data-stu-id="6c33a-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="6c33a-119">Esses recursos serão configurados em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="6c33a-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="6c33a-120">![Caixa de diálogo Selecionar recursos](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Caixa de diálogo Selecionar recursos")</span><span class="sxs-lookup"><span data-stu-id="6c33a-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="6c33a-121">Em seguida, continue a concluir as seguintes páginas do assistente: **FQDNs externos**, **defina o endereço IP interno**e **defina o endereço IP externo**.</span><span class="sxs-lookup"><span data-stu-id="6c33a-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="6c33a-122">Na página **definir o próximo salto** , selecione o diretor do próximo nó do pool de bordas do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6c33a-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="6c33a-123">![Definir a caixa de diálogo salto seguinte](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Definir a caixa de diálogo salto seguinte")</span><span class="sxs-lookup"><span data-stu-id="6c33a-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="6c33a-124">Na página **associar front-end ou pool de mediação** , não associe um pool a este pool de bordas no momento.</span><span class="sxs-lookup"><span data-stu-id="6c33a-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="6c33a-125">No momento, o tráfego de mídia externo é roteado por meio do servidor de borda herdado do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6c33a-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="6c33a-126">Essa configuração será configurada em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="6c33a-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="6c33a-127">![Caixa de diálogo associar grupos de front-end](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Caixa de diálogo associar grupos de front-end")</span><span class="sxs-lookup"><span data-stu-id="6c33a-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="6c33a-128">Clique em **concluir** e **publique** a topologia.</span><span class="sxs-lookup"><span data-stu-id="6c33a-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="6c33a-129">Siga as etapas em [instalar servidores de borda para o Lync server 2013](lync-server-2013-install-edge-servers.md) na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="6c33a-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="6c33a-130">É muito importante que você siga as diretrizes nos tópicos [implantando o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6c33a-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="6c33a-131">Esta seção simplesmente forneceu algumas diretrizes sobre as definições de configuração durante a instalação dessas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="6c33a-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="6c33a-132">Agora você deve ter um servidor de borda herdado do Lync Server 2010 implantado em paralelo com uma implantação do servidor de borda 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c33a-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="6c33a-133">Verifique se as duas implantações estão funcionando corretamente, se os serviços foram iniciados e você pode administrar cada implantação antes de passar para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="6c33a-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

