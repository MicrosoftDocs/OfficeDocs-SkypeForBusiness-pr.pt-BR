---
title: Criar um pool de VIS no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumo: Crie um pool de Servidor de Interop de Vídeo no Skype for Business Server usando o Construtor de Topologias.'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802048"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="a0aae-103">Criar um pool de VIS no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a0aae-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="a0aae-104">**Resumo:** Crie um pool de Servidor de Interop de Vídeo no Skype for Business Server usando o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="a0aae-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="a0aae-105">Criar um pool de VIS ou VIS usando o Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="a0aae-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="a0aae-106">Abra o Construtor de Topologias no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a0aae-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="a0aae-107">No painel esquerdo do Construtor de Topologias, clique com o botão direito do mouse em Pools de Servidor de **Interop** de Vídeo e escolha Novo Pool de Servidores de **Interop de Vídeo.**</span><span class="sxs-lookup"><span data-stu-id="a0aae-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="a0aae-108">Isso abrirá um assistente Criar um novo Pool de Servidores de **Interop de** Vídeo.</span><span class="sxs-lookup"><span data-stu-id="a0aae-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="a0aae-109">Forneça o FQDN do Pool para o novo Servidor de Interop de Vídeo e selecione Este **pool** tem um servidor ou Este **pool** tem vários servidores com base no seu requisito e pressione **Next**.</span><span class="sxs-lookup"><span data-stu-id="a0aae-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="a0aae-110">Se você quiser implantar um pool de Servidor de Interop de Vídeo para fornecer alta disponibilidade, selecione **Este pool tem vários servidores.**</span><span class="sxs-lookup"><span data-stu-id="a0aae-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="a0aae-111">Tenha em mente com essa opção que:</span><span class="sxs-lookup"><span data-stu-id="a0aae-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="a0aae-112">Você deve implantar o balanceamento de carga DNS para dar suporte a pools de Servidor de Interop de Vídeo.</span><span class="sxs-lookup"><span data-stu-id="a0aae-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="a0aae-113">Na próxima página, para Definir os computadores neste item de **pool,** insira o **FQDN** do Computador de cada servidor no pool no campo de texto e clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="a0aae-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="a0aae-114">Repita essa etapa para adicionar outro Servidor de Interop de Vídeo ao pool.</span><span class="sxs-lookup"><span data-stu-id="a0aae-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="a0aae-115">Quando você tiver definido todos os computadores no pool, pressione **Next**.</span><span class="sxs-lookup"><span data-stu-id="a0aae-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="a0aae-116">Se você quiser implantar apenas um Servidor de Interop de Vídeo no pool porque não precisa de alta disponibilidade, selecione Este **pool** tem um servidor e pressione **Next**.</span><span class="sxs-lookup"><span data-stu-id="a0aae-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="a0aae-117">Selecione o pool/FE do próximo salto na lista drop-down e pressione **Next**.</span><span class="sxs-lookup"><span data-stu-id="a0aae-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="a0aae-118">Selecione um Pool de Borda para associar ao VIS e pressione **Finish**.</span><span class="sxs-lookup"><span data-stu-id="a0aae-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="a0aae-119">Defina uma porta TCP ou TLS.</span><span class="sxs-lookup"><span data-stu-id="a0aae-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="a0aae-120">Selecione o Servidor de Interop de Vídeo recém-adicionado no painel esquerdo do Construtor de Topologias, clique com o botão direito do mouse nele e escolha **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="a0aae-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="a0aae-121">Habilita ou atualize a porta TCP ou TLS de acordo com seu requisito e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0aae-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="a0aae-122">Embora, por padrão, o TLS seja adicionado, apenas o TCP foi totalmente testado com o Cisco Unified Communications Manager (CallManager ou CUCM).</span><span class="sxs-lookup"><span data-stu-id="a0aae-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="a0aae-123">Adicione um gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a0aae-123">Add a video gateway.</span></span> <span data-ttu-id="a0aae-124">Para fazer isso, Expanda Componentes **Compartilhados,** clique com o botão direito do mouse em Gateways de Vídeo e selecione **Novo Gateway de Vídeo.**</span><span class="sxs-lookup"><span data-stu-id="a0aae-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="a0aae-125">Forneça o FQDN ou endereço IP do gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a0aae-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="a0aae-126">O gateway de vídeo pode estar em um subdomínio ou em um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="a0aae-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="a0aae-127">O CUCM usado pelos VTCs do seu sistema funciona como um gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a0aae-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="a0aae-128">Selecione IPv4 ou IPv6 conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="a0aae-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="a0aae-129">Você pode usar todos os endereços IP configurados ou limitar o uso do serviço aos endereços IP selecionados.</span><span class="sxs-lookup"><span data-stu-id="a0aae-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="a0aae-130">Selecione a porta de escuta do gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a0aae-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="a0aae-131">Selecione o protocolo de Transporte (TCP ou TLS) e associe-o a um Servidor de Interop de Vídeo que está definido para um tronco SIP de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a0aae-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="a0aae-132">O Protocolo de Transporte para o gateway de vídeo deve corresponder ao Protocolo de Transporte configurado para o VIS.</span><span class="sxs-lookup"><span data-stu-id="a0aae-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="a0aae-133">Um tronco de vídeo SIP correspondente é adicionado após a conclusão da etapa acima.</span><span class="sxs-lookup"><span data-stu-id="a0aae-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="a0aae-134">Clique com o botão direito do mouse no tronco de vídeo SIP e selecione o tronco que acabou de ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="a0aae-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="a0aae-135">O nome do tronco SIP de vídeo, o Servidor de Interop de Vídeo associado, o protocolo de Transporte SIP e a porta podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="a0aae-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="a0aae-136">Um Servidor de Interop de Vídeo oferece suporte a troncos 1:N.</span><span class="sxs-lookup"><span data-stu-id="a0aae-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="a0aae-137">Portanto, vários troncos podem ser adicionados, que são associados a um único Servidor de Interop de Vídeo, onde cada tronco termina em um Gateway de Vídeo diferente.</span><span class="sxs-lookup"><span data-stu-id="a0aae-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="a0aae-138">A limitação é que um gateway de vídeo específico tem um único tronco que pode ser definido para a implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a0aae-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="a0aae-139">Publique o Documento de Topologia conforme descrito em [Criar e publicar nova topologia no Skype for Business Server 2015.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="a0aae-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a0aae-140">Para melhorar a resiliência, você pode configurar um segundo Servidor de Interop de Vídeo ou pool VIS, ou um pool de front-end de backup.</span><span class="sxs-lookup"><span data-stu-id="a0aae-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="a0aae-141">Consulte [Mecanismos de resiliência para](../../plan-your-deployment/video-interop-server.md#resiliency) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a0aae-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="a0aae-142">Todas as tarefas executadas usando o Construtor de Topologias agora devem ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="a0aae-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="a0aae-143">Prossiga para instalar o software no novo servidor ou servidores VIS.</span><span class="sxs-lookup"><span data-stu-id="a0aae-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="a0aae-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="a0aae-144">See also</span></span>

[<span data-ttu-id="a0aae-145">Implantar a função de servidor VIS no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a0aae-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="a0aae-146">Planejar o Servidor de Interop de Vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a0aae-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="a0aae-147">Criar e publicar nova topologia no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a0aae-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
