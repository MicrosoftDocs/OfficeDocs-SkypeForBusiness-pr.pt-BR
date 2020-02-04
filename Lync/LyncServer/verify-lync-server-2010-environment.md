---
title: Verificar ambiente do Lync Server 2010
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
ms.openlocfilehash: 2a871955f53515491ed09ece5e5da21ef7a9fef8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="79166-102">Verificar ambiente do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="79166-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79166-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="79166-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="79166-104">Antes de implantar o Lync Server 2013 em um estado de coexistência com o Lync Server 2010, você precisa verificar se os serviços do Lync Server 2010 foram configurados e iniciados.</span><span class="sxs-lookup"><span data-stu-id="79166-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="79166-105">É importante identificar os principais serviços e recursos que existem em seu ambiente herdado antes de implantar um pool piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79166-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="79166-106">Antes de implantar o Microsoft Lync Server 2013 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identifica qual parceiro federado a configuração de XMPP herdada tem suporte.</span><span class="sxs-lookup"><span data-stu-id="79166-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="79166-107">A verificação da implantação do Lync Server 2010 herdada envolve o seguinte:</span><span class="sxs-lookup"><span data-stu-id="79166-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="79166-108">Verificando se os serviços do Lync Server 2010 foram iniciados</span><span class="sxs-lookup"><span data-stu-id="79166-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="79166-109">Revisão da topologia e dos usuários no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="79166-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="79166-110">Verificar as configurações do servidor de Federação e de borda.</span><span class="sxs-lookup"><span data-stu-id="79166-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="79166-111">Verificar os serviços do XMPP e os parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="79166-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="79166-112">**Verificar se os serviços do Lync Server 2010 foram iniciados**</span><span class="sxs-lookup"><span data-stu-id="79166-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="79166-113">No servidor de front-end do Lync Server 2010, navegue até o\\applet Serviços de ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="79166-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="79166-114">Verifique se os seguintes serviços estão em execução no servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="79166-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="79166-115">![Lista de serviços em execução no front-end Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Lista de serviços em execução no front-end Server")</span><span class="sxs-lookup"><span data-stu-id="79166-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="79166-116">**Examine a topologia do Lync Server 2010 no painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="79166-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="79166-117">Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="79166-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="79166-118">Abra o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79166-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="79166-119">Selecione **topologia**.</span><span class="sxs-lookup"><span data-stu-id="79166-119">Select **Topology**.</span></span> <span data-ttu-id="79166-120">Verifique se os vários servidores na sua implantação do Lync Server 2010 estão listados.</span><span class="sxs-lookup"><span data-stu-id="79166-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="79166-121">![Página de topologia do painel de controle do Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Página de topologia do painel de controle do Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="79166-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="79166-122">**Para revisar os usuários do Lync Server 2010 no painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="79166-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="79166-123">Abra o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79166-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="79166-124">Selecione **usuários** e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="79166-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="79166-125">Verifique se a coluna **pool de registradores** aponta para o pool do Lync Server 2010 para cada usuário listado.</span><span class="sxs-lookup"><span data-stu-id="79166-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="79166-126">![Painel de controle do Lync Server 2010 listando usuários](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Painel de controle do Lync Server 2010 listando usuários")</span><span class="sxs-lookup"><span data-stu-id="79166-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="79166-127">**Para verificar as configurações de borda e Federação do Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="79166-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="79166-128">Iniciar o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="79166-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="79166-129">Selecione **baixar a topologia na implantação existente**.</span><span class="sxs-lookup"><span data-stu-id="79166-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="79166-130">Escolha um nome de arquivo e salve a topologia com o tipo de arquivo default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="79166-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="79166-131">Expanda o nó do Lync Server 2010 para revelar as várias funções de servidor na implantação.</span><span class="sxs-lookup"><span data-stu-id="79166-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="79166-132">Selecione o nó do site e verifique se um valor de **atribuição de roteiro de Federação do site** está definido.</span><span class="sxs-lookup"><span data-stu-id="79166-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="79166-133">![Construtor de topologias, roteiro de Federação do site](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Construtor de topologias, roteiro de Federação do site")</span><span class="sxs-lookup"><span data-stu-id="79166-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="79166-134">Em seguida, selecione o servidor Standard Edition ou o pool Front-end da edição Enterprise.</span><span class="sxs-lookup"><span data-stu-id="79166-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="79166-135">Determine se um pool de bordas foi configurado para mídia abaixo de **associações**.</span><span class="sxs-lookup"><span data-stu-id="79166-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="79166-136">![Construtor de topologias mostrando servidores e pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Construtor de topologias mostrando servidores e pools")</span><span class="sxs-lookup"><span data-stu-id="79166-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="79166-137">Por fim, selecione o pool de bordas e identifique se um próximo pool de saltos está configurado abaixo da **próxima seleção de salto**.</span><span class="sxs-lookup"><span data-stu-id="79166-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="79166-138">![Construtor de topologias, seleção do próximo salto](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Construtor de topologias, seleção do próximo salto")</span><span class="sxs-lookup"><span data-stu-id="79166-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="79166-139">**Verificar a configuração de parceiro federado do XMPP herdado**</span><span class="sxs-lookup"><span data-stu-id="79166-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="79166-140">No servidor herdado XMPP, navegue até o applet Serviços\\de ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="79166-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="79166-141">Verifique se o serviço do Gateway XMPP do Office Communications Server foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="79166-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="79166-142">![Serviço de Gateway XMPP do Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Serviço de Gateway XMPP do Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="79166-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

