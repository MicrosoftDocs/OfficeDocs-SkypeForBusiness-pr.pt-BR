---
title: Planeje o estacionamento de chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planejando o estacionamento de chamadas no Skype for Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas e clientes compatíveis.
ms.openlocfilehash: 3272efe89ac995b304d96ad7ce5660144641073b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277052"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="d26bc-104">Planeje o estacionamento de chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d26bc-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="d26bc-105">Planejando o estacionamento de chamadas no Skype for Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos.</span><span class="sxs-lookup"><span data-stu-id="d26bc-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="d26bc-106">Inclui planejamento de capacidade, chamadas e clientes compatíveis.</span><span class="sxs-lookup"><span data-stu-id="d26bc-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="d26bc-107">O aplicativo de estacionamento de chamadas permite que os usuários do Enterprise Voice façam o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d26bc-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="d26bc-108">Colocar uma chamada em espera e recuperá-la no mesmo telefone ou em outro.</span><span class="sxs-lookup"><span data-stu-id="d26bc-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="d26bc-109">Colocar uma chamada em espera para transferi-la para um departamento ou área geral, por exemplo, um departamento de vendas ou um depósito onde há um telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="d26bc-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="d26bc-110">Colocar uma chamada em espera e manter o telefone original livre para outras chamadas.</span><span class="sxs-lookup"><span data-stu-id="d26bc-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="d26bc-111">Quando um usuário representa uma chamada, o Skype for Business Server transfere a chamada para um número temporário, chamado de órbita, onde a chamada é mantida até ser recuperada ou expirada. O Skype for Business Server envia a órbita ao usuário que estaciona a chamada.</span><span class="sxs-lookup"><span data-stu-id="d26bc-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="d26bc-112">Para recuperar a chamada estacionada, o usuário pode discar o número de órbita ou clicar no link de órbita ou na janela de Conversação.</span><span class="sxs-lookup"><span data-stu-id="d26bc-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="d26bc-p104">O usuário que estacionou uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas ou um sistema de paginação, para comunicar o número de órbita para outra pessoa. O usuário que estacionou a chamada pode deixar a janela de Conversação aberta para receber notificações quando a chamada for recuperada.</span><span class="sxs-lookup"><span data-stu-id="d26bc-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="d26bc-115">Como intervalos de órbita são globalmente exclusivos, é possível recuperar chamadas de qualquer site do Skype for Business ou de um telefone PBX se o roteamento estiver configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="d26bc-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="d26bc-116">Se ninguém recuperar a chamada dentro do tempo configurável, a chamada tocará novamente para a pessoa que a estacionou.</span><span class="sxs-lookup"><span data-stu-id="d26bc-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="d26bc-117">Se essa pessoa não atender, a chamada será transferida para um destino de fallback, como um operador, se assim estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="d26bc-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="d26bc-118">Você pode configurar o número de vezes que a chamada toca antes de ser transferida, entre uma a dez vezes.</span><span class="sxs-lookup"><span data-stu-id="d26bc-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="d26bc-119">Se ninguém atender a chamada transferida, ela será desconectada.</span><span class="sxs-lookup"><span data-stu-id="d26bc-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="d26bc-120">A órbita é liberada quando a chamada é recebida ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="d26bc-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="d26bc-121">Quando você implanta o Estacionamento de Chamada, precisa reservar intervalos de números de extensão para estacionar as chamadas.</span><span class="sxs-lookup"><span data-stu-id="d26bc-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="d26bc-122">Essas extensões precisam ser extensões virtuais: extensões que não têm nenhum usuário ou telefone atribuído.</span><span class="sxs-lookup"><span data-stu-id="d26bc-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="d26bc-123">Você configura a tabela de órbitas do estacionamento de chamada com os intervalos de números de extensões e especifica qual serviço de Aplicativo hospeda o aplicativo de Estacionamento de Chamada que lida com cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="d26bc-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="d26bc-124">Cada pool de front-ends tem uma tabela parque de chamadas no servidor back-end correspondente usado para gerenciar chamadas estacionadas no pool.</span><span class="sxs-lookup"><span data-stu-id="d26bc-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="d26bc-125">A lista de intervalos de órbita é armazenada no repositório de gerenciamento central e é usada para rotear órbitas para o pool de destino.</span><span class="sxs-lookup"><span data-stu-id="d26bc-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="d26bc-126">Cada pool do Skype for Business Server onde o aplicativo de estacionamento de chamada é implantado e configurado pode ter um ou mais intervalos de órbita.</span><span class="sxs-lookup"><span data-stu-id="d26bc-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="d26bc-127">As faixas órbitas devem ser globalmente exclusivas em toda a implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d26bc-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="d26bc-p107">Você também define outras configurações de Estacionamento de Chamada, como para onde as chamadas são redirecionadas quando atingem o tempo limite e se a pessoa ao telefone ouve música enquanto aguarda. Você também pode especificar o arquivo de música a ser reproduzido enquanto a chamada está em espera.</span><span class="sxs-lookup"><span data-stu-id="d26bc-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d26bc-130">Os arquivos personalizados de música em espera para o parque de chamadas não fazem backup como parte do processo de recuperação de desastres do Skype for Business Server e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="d26bc-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="d26bc-131">Mantenha sempre uma cópia de backup separada dos arquivos de música de espera personalizados que você enviar ao Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="d26bc-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="d26bc-132">O aplicativo Estacionamento de Chamada é um componente do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d26bc-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="d26bc-133">Ao implantar o Enterprise Voice, o aplicativo de estacionamento de chamada é instalado e ativado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d26bc-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="d26bc-134">No entanto, antes de poder usar o parque de chamadas, o administrador do Enterprise Voice deve configurá-lo e habilitá-lo para os usuários por meio da política de voz.</span><span class="sxs-lookup"><span data-stu-id="d26bc-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="d26bc-135">Implantação e requisitos</span><span class="sxs-lookup"><span data-stu-id="d26bc-135">Deployment and requirements</span></span>

<span data-ttu-id="d26bc-136">O aplicativo de estacionamento de chamadas é instalado automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d26bc-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="d26bc-137">Para habilitar o estacionamento de chamadas, configure a política de voz.</span><span class="sxs-lookup"><span data-stu-id="d26bc-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="d26bc-138">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="d26bc-138">Software requirements</span></span>

<span data-ttu-id="d26bc-139">Todos os servidores de front-end e servidores Standard Edition nos quais o estacionamento de chamadas é implantado devem ter o tempo de execução do Windows Media Format instalado para servidores executando o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="d26bc-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="d26bc-140">Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="d26bc-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="d26bc-141">O tempo de execução do Windows Media Format ou do Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que chamam o estacionamento reproduz para música em espera.</span><span class="sxs-lookup"><span data-stu-id="d26bc-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="d26bc-142">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="d26bc-142">Port requirements</span></span>

<span data-ttu-id="d26bc-143">O aplicativo parque de chamadas usa a **porta 5075** para solicitações de escuta SIP.</span><span class="sxs-lookup"><span data-stu-id="d26bc-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d26bc-144">Esta porta é uma configuração padrão, que pode ser alterada usando o cmdlet **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="d26bc-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="d26bc-145">Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d26bc-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="d26bc-146">Requisitos do arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="d26bc-146">Audio File requirements</span></span>

<span data-ttu-id="d26bc-147">O aplicativo de estacionamento de chamadas só dá suporte a arquivos de áudio do Windows Media (. WMA) para música em espera.</span><span class="sxs-lookup"><span data-stu-id="d26bc-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="d26bc-148">É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera.</span><span class="sxs-lookup"><span data-stu-id="d26bc-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="d26bc-149">Para baixar o Expression Encoder 4, consulte ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="d26bc-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="d26bc-150">Use a ferramenta para converter o arquivo para o formato .wma.</span><span class="sxs-lookup"><span data-stu-id="d26bc-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="d26bc-151">O formato recomendado para os arquivos de áudio da chamada com vídeo em espera é áudio de mídia 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="d26bc-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d26bc-152">O arquivo convertido é reproduzido no telefone apenas em 16 kHz, mesmo que tenha sido gravado em 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="d26bc-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="d26bc-153">Chamadas e clientes suportados</span><span class="sxs-lookup"><span data-stu-id="d26bc-153">Supported clients and calls</span></span>

<span data-ttu-id="d26bc-154">Os seguintes clientes e tipos de chamadas são compatíveis com o parque de chamadas</span><span class="sxs-lookup"><span data-stu-id="d26bc-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="d26bc-155">Clientes com suporte para Estacionamento de Chamadas</span><span class="sxs-lookup"><span data-stu-id="d26bc-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="d26bc-156">Chamadas de qualquer telefone IP, PBX, PSTN ou celular podem ser estacionadas.</span><span class="sxs-lookup"><span data-stu-id="d26bc-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d26bc-p114">Apenas chamadas de áudio podem ser estacionadas. Conferências e mensagens instantâneas não podem ser estacionadas.</span><span class="sxs-lookup"><span data-stu-id="d26bc-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="d26bc-159">Os seguintes clientes podem usar o estacionamento de chamadas para estacionar chamadas:</span><span class="sxs-lookup"><span data-stu-id="d26bc-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="d26bc-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d26bc-160">Skype for Business</span></span>
    
- <span data-ttu-id="d26bc-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d26bc-161">Lync 2013</span></span>
    
- <span data-ttu-id="d26bc-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d26bc-162">Lync 2010</span></span>
    
- <span data-ttu-id="d26bc-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d26bc-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="d26bc-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d26bc-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="d26bc-165">Telefones celulares não podem usar o estacionamento de chamadas para fazer chamadas para estacionar.</span><span class="sxs-lookup"><span data-stu-id="d26bc-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="d26bc-166">Clientes com suporte para Recuperação de Chamadas</span><span class="sxs-lookup"><span data-stu-id="d26bc-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="d26bc-p115">Os intervalos de órbita são configurados como blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído). Quando você configura órbitas como extensões virtuais, os celulares e telefones PSTN não podem recuperar as chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="d26bc-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="d26bc-169">Os usuários federados não podem recuperar chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="d26bc-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="d26bc-170">Os seguintes clientes podem recuperar chamadas estacionadas no parque da chamada:</span><span class="sxs-lookup"><span data-stu-id="d26bc-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="d26bc-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d26bc-171">Skype for Business</span></span>
    
- <span data-ttu-id="d26bc-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d26bc-172">Lync 2013</span></span>
    
- <span data-ttu-id="d26bc-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d26bc-173">Lync 2010</span></span>
    
- <span data-ttu-id="d26bc-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d26bc-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="d26bc-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d26bc-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="d26bc-176">Telefones de área comuns IP</span><span class="sxs-lookup"><span data-stu-id="d26bc-176">IP common area phones</span></span>
    
- <span data-ttu-id="d26bc-177">Telefones não IP que estão conectados à infraestrutura do Skype for Business Server, incluindo telefones de área comum e telefones PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="d26bc-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="d26bc-178">Planejamento de capacidade do Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="d26bc-178">Call Park capacity planning</span></span>

<span data-ttu-id="d26bc-179">A tabela a seguir descreve o modelo de usuário do parque de chamadas que você pode usar como base para requisitos de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="d26bc-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d26bc-180">Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de manipular as cargas de trabalho para serviços de estacionamento de chamadas em ambos os pools.</span><span class="sxs-lookup"><span data-stu-id="d26bc-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="d26bc-181">**Modelo de usuário do estacionamento de chamada**</span><span class="sxs-lookup"><span data-stu-id="d26bc-181">**Call Park User Model**</span></span>

|<span data-ttu-id="d26bc-182">**Indicador**</span><span class="sxs-lookup"><span data-stu-id="d26bc-182">**Metric**</span></span>|<span data-ttu-id="d26bc-183">**Por pool <br/> de front-end (com 8 servidores front end)**</span><span class="sxs-lookup"><span data-stu-id="d26bc-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="d26bc-184">**Por servidor padrão da edição**</span><span class="sxs-lookup"><span data-stu-id="d26bc-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d26bc-185">Taxa de estacionamento</span><span class="sxs-lookup"><span data-stu-id="d26bc-185">Park rate</span></span>  <br/> |<span data-ttu-id="d26bc-186">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="d26bc-186">8 per minute</span></span>  <br/> |<span data-ttu-id="d26bc-187">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="d26bc-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="d26bc-188">Recuperar a taxa de chamada estacionada</span><span class="sxs-lookup"><span data-stu-id="d26bc-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="d26bc-189">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="d26bc-189">8 per minute</span></span>  <br/> |<span data-ttu-id="d26bc-190">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="d26bc-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="d26bc-191">Duração média do estacionamento</span><span class="sxs-lookup"><span data-stu-id="d26bc-191">Average park duration</span></span>  <br/> |<span data-ttu-id="d26bc-192">60 segundos</span><span class="sxs-lookup"><span data-stu-id="d26bc-192">60 seconds</span></span>  <br/> |<span data-ttu-id="d26bc-193">60 segundos</span><span class="sxs-lookup"><span data-stu-id="d26bc-193">60 seconds</span></span>  <br/> |
   

