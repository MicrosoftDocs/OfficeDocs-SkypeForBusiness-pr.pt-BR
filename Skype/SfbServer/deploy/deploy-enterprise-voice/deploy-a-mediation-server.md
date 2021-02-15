---
title: Implantar um Servidor de Mediação no Construtor de Topologias no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumo: saiba como definir e implantar um Servidor de Mediação no Construtor de Topologias no Skype for Business Server.'
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836911"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="edb70-103">Implantar um Servidor de Mediação no Construtor de Topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="edb70-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="edb70-104">**Resumo:** Saiba como definir e implantar um Servidor de Mediação no Construtor de Topologias no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="edb70-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="edb70-105">A carga de trabalho do Enterprise Voice, a conferência discda e os aplicativos avançados do Enterprise Voice (aplicativo grupo de resposta, aplicativo Estacionamento de chamada, controle de admissão de chamadas (CAC) e assim por diante) estão disponíveis em pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="edb70-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="edb70-106">A funcionalidade do Servidor de Mediação é criada no Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="edb70-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="edb70-107">Um Servidor de Mediação autônomo separado não é necessário.</span><span class="sxs-lookup"><span data-stu-id="edb70-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="edb70-108">A única exceção é se você configurar um tronco SIP para se conectar a um Controlador de Borda de Sessão de um Provedor de Serviços de Telefonia e Internet.</span><span class="sxs-lookup"><span data-stu-id="edb70-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="edb70-109">Para conectar sua infraestrutura do Enterprise Voice ao seu provedor de tronco SIP, um Servidor de Mediação separado deve ser implantado.</span><span class="sxs-lookup"><span data-stu-id="edb70-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="edb70-110">A conexão entre o Skype for Business Server (um Servidor de Mediação alocado em um pool de front-end ou servidor de mediação autônomo) e um gateway é definida como uma associação lógica chamada tronco.</span><span class="sxs-lookup"><span data-stu-id="edb70-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="edb70-111">Os tópicos nesta seção descrevem como definir um tronco e como implantar um Servidor de Mediação autônomo, se você se conectar a um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="edb70-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="edb70-112">Definir um Servidor de Mediação no Construtor de Topologia</span><span class="sxs-lookup"><span data-stu-id="edb70-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="edb70-113">Você pode adicionar o Servidor de Mediação como uma função locada em um pool de Front-End ou definir um pool de Servidor de Mediação autônomo separado.</span><span class="sxs-lookup"><span data-stu-id="edb70-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="edb70-114">Para adicionar um Servidor de Mediação a um pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="edb70-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="edb70-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="edb70-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="edb70-116">No Construtor de Topologias, na árvore do console, expanda o nome do site para o qual você deseja definir um pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="edb70-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="edb70-117">Na árvore de console, clique com o botão direito do mouse no tipo de pool de Front-End que você deseja e clique em **Novo pool de Front-End.**</span><span class="sxs-lookup"><span data-stu-id="edb70-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="edb70-118">Navegue pelo assistente **Definir Novo Pool de Front-Ends** até chegar à página **Selecionar funções de servidor colocadas**.</span><span class="sxs-lookup"><span data-stu-id="edb70-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="edb70-119">Em **Selecionar funções de servidor locadas,** marque a opção **Collocate Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="edb70-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="edb70-120">Se o tipo de pool de Front End selecionado for Enterprise Edition, o componente do Servidor de Mediação será instalado em todos os Servidores front-end desse pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="edb70-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="edb70-121">O **pool de próximo salto** usado pelo Servidor de Mediação será o pool de Front-End no qual o Servidor de Mediação está alocado.</span><span class="sxs-lookup"><span data-stu-id="edb70-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="edb70-122">O **pool de Borda** usado pelo Servidor de Mediação será o mesmo pool de Borda associado ao pool de Front-End no qual o Servidor de Mediação está alocado.</span><span class="sxs-lookup"><span data-stu-id="edb70-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="edb70-123">Clique **em Tornar** Padrão para usar esse pool de Front-End para rotear chamadas para a PSTN.</span><span class="sxs-lookup"><span data-stu-id="edb70-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="edb70-124">Clique **em** Concluir quando terminar de associar um ou mais pares ao pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="edb70-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="edb70-125">Antes de prosseguir para a próxima etapa no processo de implantação do Enterprise Voice, certifique-se de que o pool do Servidor de Mediação (ou seja, pool de Front-End com o componente do Servidor de Mediação alocado) está usando os FQDNs especificados.</span><span class="sxs-lookup"><span data-stu-id="edb70-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="edb70-126">Clique com o botão direito do mouse **no nó do Skype for Business Server 2015** e clique em Publicar **Topologia.**</span><span class="sxs-lookup"><span data-stu-id="edb70-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="edb70-127">Para adicionar um Servidor de Mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="edb70-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="edb70-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="edb70-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="edb70-129">No Construtor de Topologias, na árvore do console, expanda o nome do site para o qual você deseja definir um Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="edb70-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="edb70-130">Na árvore de console, clique com o botão direito do mouse no nó **pools** de Mediação e clique em **Pool do Servidor de Mediação.**</span><span class="sxs-lookup"><span data-stu-id="edb70-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="edb70-131">Em **Definir Novo Pool de Mediação,** digite o FQDN (nome de domínio totalmente qualificado) do pool do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="edb70-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="edb70-132">Em seguida, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="edb70-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="edb70-133">Se você quiser implantar vários Servidores de Mediação no pool para fornecer alta disponibilidade, selecione **Pool de vários computadores.**</span><span class="sxs-lookup"><span data-stu-id="edb70-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="edb70-134">Você deve [implantar para](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) dar suporte a pools de Servidor de Mediação com vários Servidores de Mediação.</span><span class="sxs-lookup"><span data-stu-id="edb70-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="edb70-135">Se você deseja implantar apenas um Servidor de Mediação no pool porque não exige alta disponibilidade, selecione Pool **de computador único.**</span><span class="sxs-lookup"><span data-stu-id="edb70-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="edb70-136">Ignore a etapa seguinte.</span><span class="sxs-lookup"><span data-stu-id="edb70-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="edb70-137">Se você selecionou **Pool de Vários Computadores** na etapa anterior, no item **Definir os computadores neste pool**, clique em **FQDN do Computador**, digite o FQDN de cada servidor no pool e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="edb70-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="edb70-138">Repita essa etapa para todos os outros Servidores de Mediação que você deseja adicionar ao pool.</span><span class="sxs-lookup"><span data-stu-id="edb70-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="edb70-139">Quando tiver definido todos os computadores no pool, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="edb70-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="edb70-140">Na página Selecionar **o** próximo salto, clique em Pool de próximo **salto,** clique no FQDN do pool de Front-End que usará esse pool do Servidor de Mediação e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="edb70-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="edb70-141">Na página **Selecionar um Servidor de Borda**, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="edb70-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="edb70-142">Se você deseja fornecer conectividade PSTN para usuários externos habilitados para o Enterprise Voice, em Selecionar **Pool** de Borda usado por este Servidor de Mediação, clique no FQDN do pool do Servidor de Borda que usará esse pool de Servidor de Mediação para fornecer conectividade PSTN a esses usuários externos e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="edb70-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="edb70-143">Se você não planeja habilitar usuários externos para o Enterprise Voice ou se não deseja fornecer conectividade PSTN aos usuários quando eles estão fora da rede interna, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="edb70-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="edb70-144">Clique com o botão direito do mouse **no nó do Skype for Business Server 2015** e clique em Publicar **Topologia.**</span><span class="sxs-lookup"><span data-stu-id="edb70-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="edb70-145">Definir as portas de escuta do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="edb70-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="edb70-146">Siga as etapas deste tópico para usar o Construtor de Topologias para definir as portas de escuta que um Servidor ou pool de Mediação aceitará conexões de entrada de um par de gateway.</span><span class="sxs-lookup"><span data-stu-id="edb70-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="edb70-147">Para modificar as portas de escuta do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="edb70-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="edb70-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="edb70-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="edb70-149">No Construtor de Topologias, na árvore do console, expanda o nó **pools** de Mediação e clique com o botão direito do mouse no Servidor de Mediação criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="edb70-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="edb70-150">Por padrão, as portas de escuta SIP no Servidor de Mediação são 5070 para tráfego TLS do Skype for Business Server e 5067 para tráfego TLS de pares (como gateways, PBXes ou SBCs).</span><span class="sxs-lookup"><span data-stu-id="edb70-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="edb70-151">A porta TCP é desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="edb70-151">TCP port is disabled by default.</span></span> <span data-ttu-id="edb70-152">Você deve habilitar a porta TCP se tiver gateways que não oferecem suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="edb70-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="edb70-153">Especifique o intervalo de portas de escuta TLS ou TCP desejado que o Servidor de Mediação aceitará conexões de entrada de gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="edb70-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="edb70-154">Não é necessário inserir um intervalo de portas TCP se a opção **Habilitar porta TCP** não estiver marcada.</span><span class="sxs-lookup"><span data-stu-id="edb70-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="edb70-155">Essa configuração é opcional.</span><span class="sxs-lookup"><span data-stu-id="edb70-155">This setting is optional.</span></span>
  

