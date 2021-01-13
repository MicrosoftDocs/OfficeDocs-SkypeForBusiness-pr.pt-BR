---
title: Planejar o Estacionamento de Chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planejamento para estacionamento de chamada no Skype for Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas com suporte e clientes suportados.
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825921"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="cdf45-104">Planejar o Estacionamento de Chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cdf45-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="cdf45-105">Planejamento para estacionamento de chamada no Skype for Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos.</span><span class="sxs-lookup"><span data-stu-id="cdf45-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="cdf45-106">Inclui planejamento de capacidade, chamadas com suporte e clientes suportados.</span><span class="sxs-lookup"><span data-stu-id="cdf45-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="cdf45-107">O aplicativo Estacionamento de Chamada permite que os usuários do Enterprise Voice faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cdf45-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="cdf45-108">Coloque uma chamada em espera e recupere a chamada do mesmo telefone ou de outro telefone.</span><span class="sxs-lookup"><span data-stu-id="cdf45-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="cdf45-109">Colocar uma chamada em espera para transferi-la para um departamento ou área geral (por exemplo, para um departamento de vendas ou um depósito onde há um telefone de área comum).</span><span class="sxs-lookup"><span data-stu-id="cdf45-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="cdf45-110">Coloque uma chamada em espera e mantenha o telefone de atendimento original livre para outras chamadas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="cdf45-111">Quando um usuário estaciona uma chamada, o Skype for Business Server transfere a chamada para um número temporário, chamado órbita, onde a chamada é mantida até que seja recuperada ou o tempo se esvae. O Skype for Business Server envia a órbita para o usuário que estacionou a chamada.</span><span class="sxs-lookup"><span data-stu-id="cdf45-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="cdf45-112">Para recuperar a chamada estacionada, o usuário pode discar o número da órbita ou clicar no link de órbita ou no botão na janela conversa.</span><span class="sxs-lookup"><span data-stu-id="cdf45-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="cdf45-113">O usuário que estacionou uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas (IM) ou um sistema de paging, para comunicar o número da órbita a outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="cdf45-113">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="cdf45-114">O usuário que estacionou a chamada pode deixar a janela conversa aberta para receber notificação quando a chamada é recuperada.</span><span class="sxs-lookup"><span data-stu-id="cdf45-114">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="cdf45-115">Como os intervalos de órbitas são globalmente exclusivos, é possível recuperar chamadas de qualquer site do Skype for Business Server ou telefone PBX se o roteamento estiver configurado adequadamente.</span><span class="sxs-lookup"><span data-stu-id="cdf45-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="cdf45-116">Se ninguém recuperar a chamada dentro de um período de tempo configurável, a chamada tocará de volta para a pessoa que a estacionou.</span><span class="sxs-lookup"><span data-stu-id="cdf45-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="cdf45-117">Se essa pessoa não responder ao retorno de toque, a chamada será transferida para um destino de fallback, como para um operador, se estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="cdf45-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="cdf45-118">Você pode configurar o número de vezes que a chamada toca antes de ser transferida de uma a dez vezes.</span><span class="sxs-lookup"><span data-stu-id="cdf45-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="cdf45-119">Se ninguém atender a uma chamada transferida, ela será desconectada.</span><span class="sxs-lookup"><span data-stu-id="cdf45-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="cdf45-120">A órbita é liberada quando a chamada é recuperada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="cdf45-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="cdf45-121">Ao implantar o Estacionamento de Chamada, você precisa reservar intervalos de ramais para estacionar chamadas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="cdf45-122">Essas extensões precisam ser extensões virtuais: extensões que não têm nenhum usuário ou telefone atribuído a elas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="cdf45-123">Em seguida, configure a tabela de órbita de estacionamento de chamada com os intervalos de números de ramal e especifique qual serviço de aplicativo hospeda o aplicativo Estacionamento de Chamada que lida com cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="cdf45-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="cdf45-124">Cada pool de Front-End tem uma tabela estacionamento de chamadas no servidor back-end correspondente que é usado para gerenciar chamadas estacionadas no pool.</span><span class="sxs-lookup"><span data-stu-id="cdf45-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="cdf45-125">A lista de intervalos de órbitas é armazenada no armazenamento de Gerenciamento Central e é usada para rotear órbitas para o pool de destino.</span><span class="sxs-lookup"><span data-stu-id="cdf45-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="cdf45-126">Cada pool do Skype for Business Server onde o aplicativo Estacionamento de Chamada é implantado e configurado pode ter um ou mais intervalos de órbitas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="cdf45-127">Os intervalos de órbita devem ser globalmente exclusivos na implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cdf45-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="cdf45-128">Você também define outras configurações de Estacionamento de Chamadas, como para onde as chamadas são redirecionadas se o tempo passar e se a pessoa no telefone ouve música enquanto está estacionada.</span><span class="sxs-lookup"><span data-stu-id="cdf45-128">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="cdf45-129">Você também pode especificar o arquivo de música a ser tocar enquanto a chamada estiver em espera.</span><span class="sxs-lookup"><span data-stu-id="cdf45-129">You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdf45-130">Arquivos de música de espera personalizados para Estacionamento de Chamada não são armazenados como parte do processo de recuperação de desastres do Skype for Business Server e serão perdidos se os arquivos carregados no pool estão danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="cdf45-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="cdf45-131">Sempre mantenha uma cópia de backup separada dos arquivos de música de espera personalizados que você carregou para o Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="cdf45-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="cdf45-132">O aplicativo Estacionamento de Chamada é um componente do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cdf45-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="cdf45-133">Quando você implanta o Enterprise Voice, o aplicativo Estacionamento de Chamada é instalado e ativado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cdf45-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="cdf45-134">Antes de poder usar o Estacionamento de Chamada, no entanto, o administrador do Enterprise Voice deve configurá-lo e habilita-lo para os usuários por meio da política de voz.</span><span class="sxs-lookup"><span data-stu-id="cdf45-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="cdf45-135">Implantação e requisitos</span><span class="sxs-lookup"><span data-stu-id="cdf45-135">Deployment and requirements</span></span>

<span data-ttu-id="cdf45-136">O aplicativo Estacionamento de Chamada é instalado automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cdf45-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="cdf45-137">Você habilita o Estacionamento de Chamada configurando a política de voz.</span><span class="sxs-lookup"><span data-stu-id="cdf45-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="cdf45-138">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="cdf45-138">Software requirements</span></span>

<span data-ttu-id="cdf45-139">Todos os servidores Front End e Standard Edition onde o Estacionamento de Chamada é implantado devem ter o Windows Media Format Runtime instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="cdf45-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="cdf45-140">Para o Windows Server 2008 R2, o Windows Media Format Runtime é instalado como parte da Experiência Desktop do Windows.</span><span class="sxs-lookup"><span data-stu-id="cdf45-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="cdf45-141">O Tempo de Execução do Windows Media Format ou o Microsoft Media Foundation são necessários para arquivos .wma (Windows Media Audio) que o Estacionamento de Chamada reproduz para música em espera.</span><span class="sxs-lookup"><span data-stu-id="cdf45-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="cdf45-142">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="cdf45-142">Port requirements</span></span>

<span data-ttu-id="cdf45-143">O aplicativo Estacionamento de Chamada usa **a Porta 5075 para**  solicitações de escuta SIP.</span><span class="sxs-lookup"><span data-stu-id="cdf45-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cdf45-144">Esta porta é uma configuração padrão, que pode ser alterado usando o cmdlet **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="cdf45-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="cdf45-145">Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdf45-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="cdf45-146">Requisitos de arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="cdf45-146">Audio File requirements</span></span>

<span data-ttu-id="cdf45-147">O aplicativo Estacionamento de Chamada dá suporte apenas a arquivos .wma (Windows Media Audio) para música em espera.</span><span class="sxs-lookup"><span data-stu-id="cdf45-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="cdf45-148">É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera.</span><span class="sxs-lookup"><span data-stu-id="cdf45-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="cdf45-149">Para baixar o Expression Encoder 4, consulte   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="cdf45-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="cdf45-150">Use a ferramenta para converter o arquivo no formato .wma.</span><span class="sxs-lookup"><span data-stu-id="cdf45-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="cdf45-151">O formato recomendado para arquivos de música de espera do Estacionamento de Chamada é Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="cdf45-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdf45-152">O arquivo convertido é reproduzido no telefone somente a 16 kHz, mesmo que tenha sido gravado a 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="cdf45-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="cdf45-153">Clientes e chamadas com suporte</span><span class="sxs-lookup"><span data-stu-id="cdf45-153">Supported clients and calls</span></span>

<span data-ttu-id="cdf45-154">Os seguintes clientes e tipos de chamadas são suportados para Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="cdf45-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="cdf45-155">Clientes com suporte para estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="cdf45-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="cdf45-156">Chamadas de qualquer IP, PBX (central privada de comução), PSTN (rede telefônica pública comutado) ou telefone celular podem ser estacionadas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdf45-157">Somente chamadas de áudio podem ser estacionadas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-157">Only audio calls can be parked.</span></span> <span data-ttu-id="cdf45-158">As mensagens instantâneas e conferências não podem ser estacionadas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-158">Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="cdf45-159">Os clientes a seguir podem usar o Estacionamento de Chamada para estacionar chamadas:</span><span class="sxs-lookup"><span data-stu-id="cdf45-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="cdf45-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cdf45-160">Skype for Business</span></span>
    
- <span data-ttu-id="cdf45-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf45-161">Lync 2013</span></span>
    
- <span data-ttu-id="cdf45-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="cdf45-162">Lync 2010</span></span>
    
- <span data-ttu-id="cdf45-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="cdf45-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="cdf45-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="cdf45-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="cdf45-165">Os telefones celulares não podem usar o Estacionamento de Chamadas para estacionar chamadas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="cdf45-166">Clientes com suporte para recuperação de chamadas</span><span class="sxs-lookup"><span data-stu-id="cdf45-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="cdf45-167">Os intervalos de órbita são configurados como blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído).</span><span class="sxs-lookup"><span data-stu-id="cdf45-167">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="cdf45-168">Quando você configura órbitas como extensões virtuais, telefones celulares e telefones PSTN não podem recuperar chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-168">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="cdf45-169">Os usuários federados não podem recuperar chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="cdf45-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="cdf45-170">Os clientes a seguir podem recuperar chamadas estacionadas no Estacionamento de Chamadas:</span><span class="sxs-lookup"><span data-stu-id="cdf45-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="cdf45-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cdf45-171">Skype for Business</span></span>
    
- <span data-ttu-id="cdf45-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf45-172">Lync 2013</span></span>
    
- <span data-ttu-id="cdf45-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="cdf45-173">Lync 2010</span></span>
    
- <span data-ttu-id="cdf45-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="cdf45-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="cdf45-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="cdf45-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="cdf45-176">Telefones de área comum IP</span><span class="sxs-lookup"><span data-stu-id="cdf45-176">IP common area phones</span></span>
    
- <span data-ttu-id="cdf45-177">Telefones não IP que estão conectados à infraestrutura do Skype for Business Server, incluindo telefones de área comum e telefones PBX (central privada de comutamento)</span><span class="sxs-lookup"><span data-stu-id="cdf45-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="cdf45-178">Planejamento de capacidade do Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="cdf45-178">Call Park capacity planning</span></span>

<span data-ttu-id="cdf45-179">A tabela a seguir descreve o modelo de usuário estacionamento de chamada que você pode usar como base para requisitos de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="cdf45-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cdf45-180">Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de lidar com as cargas de trabalho dos serviços de Estacionamento de Chamada em ambos os pools.</span><span class="sxs-lookup"><span data-stu-id="cdf45-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="cdf45-181">**Modelo de usuário do estacionamento de chamada Park**</span><span class="sxs-lookup"><span data-stu-id="cdf45-181">**Call Park User Model**</span></span>

|<span data-ttu-id="cdf45-182">**Indicador**</span><span class="sxs-lookup"><span data-stu-id="cdf45-182">**Metric**</span></span>|<span data-ttu-id="cdf45-183">**Por pool de front-end  <br/>  (com 8 servidores front-end)**</span><span class="sxs-lookup"><span data-stu-id="cdf45-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="cdf45-184">**Por servidor Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="cdf45-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cdf45-185">Taxa de estacionamento</span><span class="sxs-lookup"><span data-stu-id="cdf45-185">Park rate</span></span>  <br/> |<span data-ttu-id="cdf45-186">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="cdf45-186">8 per minute</span></span>  <br/> |<span data-ttu-id="cdf45-187">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="cdf45-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="cdf45-188">Recuperar a taxa de chamada estacionada</span><span class="sxs-lookup"><span data-stu-id="cdf45-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="cdf45-189">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="cdf45-189">8 per minute</span></span>  <br/> |<span data-ttu-id="cdf45-190">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="cdf45-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="cdf45-191">Duração média do estacionamento</span><span class="sxs-lookup"><span data-stu-id="cdf45-191">Average park duration</span></span>  <br/> |<span data-ttu-id="cdf45-192">60 segundos</span><span class="sxs-lookup"><span data-stu-id="cdf45-192">60 seconds</span></span>  <br/> |<span data-ttu-id="cdf45-193">60 segundos</span><span class="sxs-lookup"><span data-stu-id="cdf45-193">60 seconds</span></span>  <br/> |
   

