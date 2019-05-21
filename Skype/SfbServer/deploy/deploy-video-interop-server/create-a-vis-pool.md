---
title: Criar um pool de VIS no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumo: criar um pool de servidores Interop de vídeo no Skype for Business Server usando o construtor de topologias.'
ms.openlocfilehash: 3e01659c4cef268a8748bd14c658eb5168b3ac97
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302725"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="4ac47-103">Criar um pool de VIS no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4ac47-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="4ac47-104">**Resumo:** Crie um pool de servidores de interoperabilidade de vídeo no Skype for Business Server usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4ac47-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="4ac47-105">Crie um pool VIS ou VIS usando o Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="4ac47-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="4ac47-106">Abra o Construtor de Topologias no servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="4ac47-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="4ac47-107">No painel esquerdo do construtor de topologias, clique com o botão direito do mouse em pools de **servidores Interop** e escolha **novo pool de servidores Interop de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="4ac47-108">Isso abrirá um assistente **Criar um novo pool de servidor interop de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="4ac47-109">Forneça o FQDN do pool para o novo servidor de interoperabilidade de vídeo e selecione **este pool tem um servidor** ou **esse pool tem vários servidores** com base em seu requisito e, em seguida, pressione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="4ac47-110">Se você quiser implantar um pool de servidores de interoperabilidade de vídeo para fornecer alta disponibilidade, selecione **este pool tem vários servidores**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="4ac47-111">Tenha em mente que com esta opção:</span><span class="sxs-lookup"><span data-stu-id="4ac47-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="4ac47-112">Você deve implantar o balanceamento de carga de DNS para dar suporte a pools de servidores de interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="4ac47-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="4ac47-113">Na próxima página, no item **Definir os computadores neste pool**, insira o **FQDN do computador** de cada servidor no pool no campo de texto e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="4ac47-114">Repita esta etapa para adicionar outro servidor de interoperabilidade de vídeo ao pool.</span><span class="sxs-lookup"><span data-stu-id="4ac47-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="4ac47-115">Quando você tiver definido todos os computadores no pool, aperte **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="4ac47-116">Se você quiser implantar apenas um servidor de interoperabilidade de vídeo no pool porque não requer alta disponibilidade, selecione **este pool tem um servidor** e pressione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="4ac47-117">Selecione o próximo pool/FE na lista suspensa e aperte **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="4ac47-118">Selecione um Pool de Borda para ser associado ao VIS e aperte **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="4ac47-119">Defina uma porta TCP ou TLS.</span><span class="sxs-lookup"><span data-stu-id="4ac47-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="4ac47-120">Selecione o servidor de interoperabilidade de vídeo recém-adicionado no painel esquerdo do construtor de topologias, clique nele com o botão direito do mouse e escolha **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="4ac47-121">Habilite ou atualize a porta TCP ou TLS de acordo com o seu requisito e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="4ac47-122">Embora o TLS padrão seja adicionado, somente o TCP foi totalmente testado com o Gerenciador de comunicações unificadas da Cisco (CallManager ou CUCM).</span><span class="sxs-lookup"><span data-stu-id="4ac47-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="4ac47-p106">Adicione um gateway de vídeo. Para fazer isso, expanda os Componentes compartilhados, clique com o botão direito do mouse sobre **Gateways de vídeo** e selecione **Novo gateway de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="4ac47-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="4ac47-p107">Forneça o endereço IP ou FQDN do gateway de vídeo. O gateway de vídeo pode estar em um subdomínio ou em um domínio diferente. O CUCM usado pelos VTCs do seu sistema servem de gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="4ac47-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="4ac47-p108">Selecione IPv4 ou IPv6, conforme apropriado. Você pode usar todos os endereços IP configurados ou limitar o uso do serviço para endereços IP selecionados.</span><span class="sxs-lookup"><span data-stu-id="4ac47-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="4ac47-130">Selecione a porta de escuta do gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="4ac47-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="4ac47-131">Selecione o protocolo de transporte (TCP ou TLS) e associe-o a um servidor de interoperabilidade de vídeo que esteja configurado para um tronco de vídeo SIP.</span><span class="sxs-lookup"><span data-stu-id="4ac47-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="4ac47-132">O Protocolo de Transporte para o gateway de vídeo deve ser correspondente ao Protocolo de Transporte configurado para o VIS.</span><span class="sxs-lookup"><span data-stu-id="4ac47-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="4ac47-133">Um tronco de vídeo SIP correspondente é adicionado após a conclusão da etapa acima.</span><span class="sxs-lookup"><span data-stu-id="4ac47-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="4ac47-134">Clique com o botão direito do mouse sobre o tronco de vídeo SIP e selecione o tronco que acabou de ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="4ac47-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="4ac47-135">O nome do tronco SIP do vídeo, o servidor de interoperabilidade de vídeo associado, o protocolo de transporte SIP e a portabilidade podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="4ac47-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="4ac47-136">Um servidor de interoperabilidade de vídeo dá suporte A troncos 1: N.</span><span class="sxs-lookup"><span data-stu-id="4ac47-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="4ac47-137">Portanto, vários troncos podem ser adicionados, que estão associados a um único servidor de interoperabilidade de vídeo, em que cada tronco termina em um gateway de vídeo diferente.</span><span class="sxs-lookup"><span data-stu-id="4ac47-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="4ac47-138">A limitação é que um gateway de vídeo específico tem um e apenas um tronco que pode ser definido para a implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4ac47-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="4ac47-139">Publique o documento de topologia conforme descrito em [criar e publicar nova topologia no Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4ac47-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ac47-140">Para melhorar a resiliência, talvez você queira configurar um segundo servidor de interoperabilidade de vídeo ou um pool de VIS ou um pool de front-end de backup.</span><span class="sxs-lookup"><span data-stu-id="4ac47-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="4ac47-141">Consulte [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para mais informações.</span><span class="sxs-lookup"><span data-stu-id="4ac47-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="4ac47-142">Todas as tarefas executadas usando o Construtor de Topologias devem estar concluídas.</span><span class="sxs-lookup"><span data-stu-id="4ac47-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="4ac47-143">Prossiga com a instalação do software no novo servidor ou servidores VIS.</span><span class="sxs-lookup"><span data-stu-id="4ac47-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="4ac47-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="4ac47-144">See also</span></span>

[<span data-ttu-id="4ac47-145">Implantar a função de servidor VIS no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4ac47-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="4ac47-146">Planejar o servidor de interoperabilidade de vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4ac47-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="4ac47-147">Criar e publicar uma nova topologia no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4ac47-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
