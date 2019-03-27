---
title: Criar um pool VIS no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumo: Crie um pool de servidores de interoperabilidade de vídeo no Skype para Business Server usando o construtor de topologias.'
ms.openlocfilehash: 484cb1c504680dde393d24ce65606e415d070edb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874106"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="0783a-103">Criar um pool VIS no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0783a-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="0783a-104">**Resumo:** Crie um pool de servidores de interoperabilidade de vídeo no Skype para Business Server usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="0783a-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="0783a-105">Crie um pool VIS ou VIS usando o Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="0783a-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="0783a-106">Abra o Construtor de Topologias no servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="0783a-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="0783a-107">No painel à esquerda do construtor de topologia, clique com o botão direito em **Pools de servidor de interoperabilidade de vídeo** e escolha **Novo Pool de servidor de interoperabilidade de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="0783a-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="0783a-108">Isso abrirá um assistente **Criar um novo pool de servidor interop de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="0783a-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="0783a-109">Fornecer o FQDN do Pool para o novo servidor de interoperabilidade de vídeo e selecione **pool com um servidor** ou **pool com vários servidores** com base em suas necessidades, em seguida, pressione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0783a-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="0783a-110">Se você deseja implantar um pool de servidores de interoperabilidade de vídeo para fornecer alta disponibilidade, selecione o **pool com vários servidores**.</span><span class="sxs-lookup"><span data-stu-id="0783a-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="0783a-111">Tenha em mente que com esta opção:</span><span class="sxs-lookup"><span data-stu-id="0783a-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="0783a-112">Você deve implantar o balanceamento de carga DNS para dar suporte a pools de servidor de interoperabilidade de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0783a-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="0783a-113">Na próxima página, no item **Definir os computadores neste pool**, insira o **FQDN do computador** de cada servidor no pool no campo de texto e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0783a-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="0783a-114">Repita essa etapa para adicionar outro servidor de interoperabilidade de vídeo para o pool.</span><span class="sxs-lookup"><span data-stu-id="0783a-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="0783a-115">Quando você tiver definido todos os computadores no pool, aperte **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0783a-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="0783a-116">Se desejar implantar apenas um servidor de interoperabilidade de vídeo no pool, pois você não requerem alta disponibilidade, em seguida, selecione o **pool com um servidor** e pressione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0783a-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="0783a-117">Selecione o próximo pool/FE na lista suspensa e aperte **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0783a-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="0783a-118">Selecione um Pool de Borda para ser associado ao VIS e aperte **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="0783a-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="0783a-119">Defina uma porta TCP ou TLS.</span><span class="sxs-lookup"><span data-stu-id="0783a-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="0783a-120">Selecione o servidor recém-adicionado de interoperabilidade de vídeo do painel esquerdo do construtor de topologia, clique com botão direito-lo e escolha **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0783a-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="0783a-121">Habilite ou atualize a porta TCP ou TLS de acordo com o seu requisito e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="0783a-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="0783a-122">Embora por padrão o TLS é adicionado, apenas TCP foi totalmente testado com Cisco Unified Communications Manager (CallManager ou CUCM).</span><span class="sxs-lookup"><span data-stu-id="0783a-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="0783a-p106">Adicione um gateway de vídeo. Para fazer isso, expanda os Componentes compartilhados, clique com o botão direito do mouse sobre **Gateways de vídeo** e selecione **Novo gateway de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="0783a-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="0783a-p107">Forneça o endereço IP ou FQDN do gateway de vídeo. O gateway de vídeo pode estar em um subdomínio ou em um domínio diferente. O CUCM usado pelos VTCs do seu sistema servem de gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0783a-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="0783a-p108">Selecione IPv4 ou IPv6, conforme apropriado. Você pode usar todos os endereços IP configurados ou limitar o uso do serviço para endereços IP selecionados.</span><span class="sxs-lookup"><span data-stu-id="0783a-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="0783a-130">Selecione a porta de escuta do gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0783a-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="0783a-131">Selecione o protocolo de transporte (TCP ou TLS) e associá-lo a um servidor de interoperabilidade de vídeo, que é configurada para um tronco SIP de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0783a-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="0783a-132">O Protocolo de Transporte para o gateway de vídeo deve ser correspondente ao Protocolo de Transporte configurado para o VIS.</span><span class="sxs-lookup"><span data-stu-id="0783a-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="0783a-133">Um tronco de vídeo SIP correspondente é adicionado após a conclusão da etapa acima.</span><span class="sxs-lookup"><span data-stu-id="0783a-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="0783a-134">Clique com o botão direito do mouse sobre o tronco de vídeo SIP e selecione o tronco que acabou de ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="0783a-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="0783a-135">O nome do tronco SIP vídeo, associados servidor interoperabilidade de vídeo, o protocolo de transporte SIP e porta pode todos ser alterada.</span><span class="sxs-lookup"><span data-stu-id="0783a-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="0783a-136">Um servidor de interoperabilidade de vídeo oferece suporte a troncos 1: n.</span><span class="sxs-lookup"><span data-stu-id="0783a-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="0783a-137">Daí troncos múltiplos podem ser adicionados, que estão associados um único servidor de interoperabilidade de vídeo, onde cada tronco finaliza em um Gateway de vídeo diferentes.</span><span class="sxs-lookup"><span data-stu-id="0783a-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="0783a-138">A limitação é que um Gateway de vídeo específico tem somente um tronco que pode ser definidas para o Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0783a-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="0783a-139">Publicar o documento de topologia, conforme descrito em [criar e publicar a nova topologia no Skype para Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="0783a-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0783a-140">Para melhorar a resiliência, convém configurar um pool de servidor de interoperabilidade de vídeo ou VIS segundo ou um pool de Front-End de backup.</span><span class="sxs-lookup"><span data-stu-id="0783a-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="0783a-141">Consulte [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para mais informações.</span><span class="sxs-lookup"><span data-stu-id="0783a-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="0783a-142">Todas as tarefas executadas usando o Construtor de Topologias devem estar concluídas.</span><span class="sxs-lookup"><span data-stu-id="0783a-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="0783a-143">Prossiga com a instalação do software no novo servidor ou servidores VIS.</span><span class="sxs-lookup"><span data-stu-id="0783a-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="0783a-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0783a-144">See also</span></span>

[<span data-ttu-id="0783a-145">Implantar a função de servidor VIS no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0783a-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="0783a-146">Planejar o servidor de interoperabilidade de vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0783a-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="0783a-147">Criar e publicar uma nova topologia no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0783a-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
