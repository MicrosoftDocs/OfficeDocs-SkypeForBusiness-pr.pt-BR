---
title: Implantar um servidor de mediação no construtor de topologia no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumo: Saiba como definir e implantar um servidor de mediação no construtor de topologia no Skype para Business Server.'
ms.openlocfilehash: a80f5bfbd57c1a533153effe21ca6748eb26aa6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892780"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="03ffa-103">Implantar um servidor de mediação no construtor de topologia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="03ffa-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="03ffa-104">**Resumo:** Saiba como definir e implantar um servidor de mediação no construtor de topologia no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="03ffa-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="03ffa-105">A carga de trabalho do Enterprise Voice, conferência discada e aplicativos avançados do Enterprise Voice (aplicativo grupo de resposta, o aplicativo de estacionamento de chamada, o controle de admissão de chamadas (CAC) e assim por diante), estão disponíveis nos pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="03ffa-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="03ffa-106">A funcionalidade do servidor de mediação é inserida no servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="03ffa-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="03ffa-107">Um servidor de mediação autônomo separado não é necessário.</span><span class="sxs-lookup"><span data-stu-id="03ffa-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="03ffa-108">A única exceção é se você configurar um tronco SIP para se conectar a um Controlador de Borda de Sessão de um Provedor de Serviços de Telefonia e Internet.</span><span class="sxs-lookup"><span data-stu-id="03ffa-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="03ffa-109">Para conectar sua infraestrutura do Enterprise Voice com seu provedor de tronco SIP, um servidor de mediação separado deve ser implantado.</span><span class="sxs-lookup"><span data-stu-id="03ffa-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="03ffa-110">A conexão entre Skype para Business Server (qualquer um servidor de mediação colocado em um pool de Front-End ou servidor de mediação autônomo) e um gateway é definido como uma associação lógica chamada um tronco.</span><span class="sxs-lookup"><span data-stu-id="03ffa-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="03ffa-111">Os tópicos desta seção descrevem como definir um tronco e como implantar um servidor de mediação autônomo, se você conectar a um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="03ffa-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="03ffa-112">Definir um Servidor de Mediação no Construtor de Topologia</span><span class="sxs-lookup"><span data-stu-id="03ffa-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="03ffa-113">Você pode adicionar o servidor de mediação como uma função colocada em um pool de Front-End ou definir um pool do servidor de mediação de autônomo separado.</span><span class="sxs-lookup"><span data-stu-id="03ffa-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="03ffa-114">Para adicionar um servidor de mediação para um pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="03ffa-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="03ffa-115">Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="03ffa-116">No construtor de topologia, na árvore de console, expanda o nome do site para o qual você deseja definir um pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="03ffa-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="03ffa-117">Na árvore de console, clique com botão direito do tipo de pool de Front-End que você deseja e clique em **pool de Front-End novo …**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="03ffa-118">Navegue pelo assistente **Definir Novo Pool de Front-Ends** até chegar à página **Selecionar funções de servidor colocadas**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="03ffa-119">Nas **funções de servidor colocadas Select**, marque a opção **Colocar o servidor de mediação**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03ffa-120">Se o tipo de pool de Front-End que você selecionou for o Enterprise Edition, em seguida, o componente de servidor de mediação será instalado em todos os servidores Front-End desse pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="03ffa-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="03ffa-121">O **pool de próximo salto** usado pelo servidor de mediação será o pool de Front-End, qual o servidor de mediação é colocado.</span><span class="sxs-lookup"><span data-stu-id="03ffa-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="03ffa-122">O **pool de borda** usado pelo servidor de mediação será o mesmo pool de borda associado ao pool de Front-End no qual o servidor de mediação é colocado.</span><span class="sxs-lookup"><span data-stu-id="03ffa-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="03ffa-123">Clique em **Tornar padrão** para usar este pool de Front-End para rotear chamadas para a PSTN.</span><span class="sxs-lookup"><span data-stu-id="03ffa-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="03ffa-124">Clique em **Concluir** quando tiver terminado de associar um ou mais pares ao pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="03ffa-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03ffa-125">Antes de prosseguir para a próxima etapa do processo de implantação do Enterprise Voice, certifique-se de que o pool de servidor de mediação (isto é, Front End pool com o componente de servidor de mediação colocado) está usando os FQDNs que você especificou.</span><span class="sxs-lookup"><span data-stu-id="03ffa-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="03ffa-126">Com o botão direito no nó do **Skype para Business Server 2015** e, em seguida, clique em **Publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="03ffa-127">Para adicionar um Servidor de Mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="03ffa-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="03ffa-128">Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="03ffa-129">No construtor de topologia, na árvore de console, expanda o nome do site para o qual você deseja definir um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="03ffa-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="03ffa-130">Na árvore de console, clique com botão direito no nó **pools de mediação** e clique em **pool de servidor de mediação**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="03ffa-131">Em **Definir Novo Pool de mediação**, digite o nome de domínio totalmente qualificado do pool do servidor de mediação (FQDN).</span><span class="sxs-lookup"><span data-stu-id="03ffa-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="03ffa-132">Em seguida, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="03ffa-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="03ffa-133">Se desejar implantar vários servidores de mediação no pool para fornecer alta disponibilidade, selecione **pool de vários computadores**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="03ffa-134">Você deve [implantar](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) para oferecer suporte a pools de servidor de mediação que possuem vários servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="03ffa-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="03ffa-135">Se você deseja implantar apenas um servidor de mediação no pool, porque você não requerem alta disponibilidade, selecione **pool de computador único**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="03ffa-136">Ignore a etapa seguinte.</span><span class="sxs-lookup"><span data-stu-id="03ffa-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="03ffa-137">Se você selecionou **Pool de Vários Computadores** na etapa anterior, no item **Definir os computadores neste pool**, clique em **FQDN do Computador**, digite o FQDN de cada servidor no pool e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="03ffa-138">Repita essa etapa para todos os outros servidores de mediação que você deseja adicionar ao pool.</span><span class="sxs-lookup"><span data-stu-id="03ffa-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="03ffa-139">Quando tiver definido todos os computadores no pool, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="03ffa-140">Na página **Selecionar o próximo salto** , clique em **pool de próximo salto**, o FQDN do pool Front-Ends que usará esse pool de servidores de mediação e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="03ffa-141">Na página **Selecionar um Servidor de Borda**, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="03ffa-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="03ffa-142">Se você deseja oferecer conectividade PSTN para usuários externos habilitados para o Enterprise Voice, em **Selecione Pool de borda usado pelo servidor de mediação**, clique em FQDN do pool de servidores de borda que usará esse pool de servidores de mediação para fornecer conectividade PSTN para os usuários externos e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="03ffa-143">Se você não planeja permitir que usuários externos para o Enterprise Voice, ou se você não deseja fornecer conectividade PSTN para usuários quando eles estão fora da rede interna, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="03ffa-144">Com o botão direito no nó do **Skype para Business Server 2015** e, em seguida, clique em **Publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="03ffa-145">Definir as portas de escuta do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="03ffa-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="03ffa-146">Siga as etapas neste tópico para usar o construtor de topologias para definir as portas de escuta um servidor de mediação ou pool aceitará conexões de entrada de um par de gateway.</span><span class="sxs-lookup"><span data-stu-id="03ffa-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="03ffa-147">Para modificar as portas de escuta do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="03ffa-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="03ffa-148">Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="03ffa-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="03ffa-149">No construtor de topologia, na árvore de console, expanda o nó **pools de mediação** e clique com o botão o servidor de mediação criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="03ffa-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="03ffa-150">Por padrão, as portas de escuta SIP no servidor de mediação são 5070 tráfego TLS nos Skype para Business Server e 5067 tráfego TLS nos peers (por exemplo, gateways, PBXs ou SBCs).</span><span class="sxs-lookup"><span data-stu-id="03ffa-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="03ffa-151">A porta TCP é desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="03ffa-151">TCP port is disabled by default.</span></span> <span data-ttu-id="03ffa-152">Você deve habilitar a porta TCP se tiver gateways que não oferecem suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="03ffa-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="03ffa-153">Especifique o desejada TLS ou TCP escutando intervalo de porta do servidor de mediação aceitará conexões de entrada de gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="03ffa-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03ffa-p107">Não é necessário inserir um intervalo de portas TCP se a opção **Habilitar porta TCP** não estiver marcada. Essa configuração é opcional.</span><span class="sxs-lookup"><span data-stu-id="03ffa-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

