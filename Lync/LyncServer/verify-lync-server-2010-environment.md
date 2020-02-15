---
title: Verificar o ambiente do Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce56a23120df813d3c3d8107de67d202afb5d663
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="3308f-102">Verificar o ambiente do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3308f-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3308f-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3308f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3308f-104">Antes de implantar o Lync Server 2013 em um estado de coexistência com o Lync Server 2010, você precisa verificar se os serviços do Lync Server 2010 foram configurados e iniciados.</span><span class="sxs-lookup"><span data-stu-id="3308f-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="3308f-105">É importante identificar os principais serviços e recursos existentes no seu ambiente herdado antes de implantar um pool piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3308f-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="3308f-106">Antes de implantar o Microsoft Lync Server 2013 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identificar o parceiro federado onde a configuração XMPP herdada oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="3308f-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="3308f-107">Verificar sua implantação herdada do Lync Server 2010 envolve o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3308f-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="3308f-108">Verificando se os serviços do Lync Server 2010 foram iniciados</span><span class="sxs-lookup"><span data-stu-id="3308f-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="3308f-109">Revisão da topologia e dos usuários no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3308f-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="3308f-110">Verificando a federação e as configurações do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="3308f-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="3308f-111">Verificando serviços XMPP e parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="3308f-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="3308f-112">**Verifique se os serviços do Lync Server 2010 foram iniciados**</span><span class="sxs-lookup"><span data-stu-id="3308f-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="3308f-113">No servidor front-end do Lync Server 2010, navegue até o mini-aplicativo\\serviços de ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="3308f-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="3308f-114">Verifique se os serviços a seguir estão sendo executados no servidor Front End:</span><span class="sxs-lookup"><span data-stu-id="3308f-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="3308f-115">![Lista de serviços em execução no servidor front-end](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Lista de serviços em execução no servidor front-end")</span><span class="sxs-lookup"><span data-stu-id="3308f-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="3308f-116">**Examinar a topologia do Lync Server 2010 no painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="3308f-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="3308f-117">Entre no Servidor front-end com uma conta membro do grupo RTCUniversalServerAdmins ou um membro da função administrativa CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3308f-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="3308f-118">Abra o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3308f-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="3308f-119">Selecione **Topologia**.</span><span class="sxs-lookup"><span data-stu-id="3308f-119">Select **Topology**.</span></span> <span data-ttu-id="3308f-120">Verifique se os vários servidores na sua implantação do Lync Server 2010 estão listados.</span><span class="sxs-lookup"><span data-stu-id="3308f-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="3308f-121">![Página de topologia do painel de controle do Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Página de topologia do painel de controle do Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="3308f-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="3308f-122">**Para examinar os usuários do Lync Server 2010 no painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="3308f-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="3308f-123">Abra o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3308f-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="3308f-124">Selecione **Usuários** e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="3308f-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="3308f-125">Verifique se a coluna **pool do registrador** aponta para o pool do Lync Server 2010 para cada usuário listado.</span><span class="sxs-lookup"><span data-stu-id="3308f-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="3308f-126">![Lync Server 2010 listando usuários do painel de controle](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 listando usuários do painel de controle")</span><span class="sxs-lookup"><span data-stu-id="3308f-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="3308f-127">**Para verificar as configurações de borda e de Federação do Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="3308f-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="3308f-128">Inicie o Construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="3308f-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="3308f-129">Selecione **Download da topologia de uma implantação existente**.</span><span class="sxs-lookup"><span data-stu-id="3308f-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="3308f-130">Escolha um nome de arquivo e salve a topologia com um tipo de arquivo padrão .tbxml.</span><span class="sxs-lookup"><span data-stu-id="3308f-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="3308f-131">Expanda o nó do Lync Server 2010 para revelar as várias funções de servidor na implantação.</span><span class="sxs-lookup"><span data-stu-id="3308f-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="3308f-132">Selecione o nó do site e verifique se um valor de **Atribuição de tora de federação do site** está definido.</span><span class="sxs-lookup"><span data-stu-id="3308f-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="3308f-133">![Construtor de topologias, rota de Federação do site](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Construtor de topologias, rota de Federação do site")</span><span class="sxs-lookup"><span data-stu-id="3308f-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="3308f-p103">Em seguida, selecione o pool front-end do servidor Standard Edition ou Enterprise Edition. Determine se um pool de borda foi configurado para Mídia abaixo de **Associações**.</span><span class="sxs-lookup"><span data-stu-id="3308f-p103">Next, select the Standard Edition Server or Enterprise Edition front end pool. Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="3308f-136">![Construtor de topologia mostrando servidores e pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Construtor de topologia mostrando servidores e pools")</span><span class="sxs-lookup"><span data-stu-id="3308f-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="3308f-137">Por fim, selecione o pool de borda e identifique se um pool de Próximo salto está configurado abaixo de **Seleção do próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="3308f-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="3308f-138">![Construtor de topologias, seleção de próximo salto](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Construtor de topologias, seleção de próximo salto")</span><span class="sxs-lookup"><span data-stu-id="3308f-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="3308f-139">**Verificar a configuração de parceiro federado XMPP herdado**</span><span class="sxs-lookup"><span data-stu-id="3308f-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="3308f-140">No servidor XMPP herdado, navegue até o mini-aplicativo Serviços\\de ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="3308f-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="3308f-141">Verifique se o serviço do Gateway XMPP do Office Communications Server foi inicializado.</span><span class="sxs-lookup"><span data-stu-id="3308f-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="3308f-142">![Serviço de Gateway XMPP do Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Serviço de Gateway XMPP do Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="3308f-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

