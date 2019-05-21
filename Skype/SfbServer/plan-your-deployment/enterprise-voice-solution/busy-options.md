---
title: Planejar Opções de Disponibilidade no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Leia sobre o recurso opções ocupadas no Skype for Business Server.
ms.openlocfilehash: 8e88b4bf3b92c7fea9bcf79822e2711ff3bee7de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277101"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="ba55b-103">Planejar Opções de Disponibilidade no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ba55b-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="ba55b-104">Leia sobre o recurso opções ocupadas no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ba55b-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="ba55b-105">O recurso Opções de Disponibilidade é uma nova política de voz introduzida na Atualização Cumulativa de julho de 2016 que permite configurar como as chamadas de entrada serão tratadas quando o usuário já estiver em uma chamada ou em conferência ou tiver colocado uma chamada em espera.</span><span class="sxs-lookup"><span data-stu-id="ba55b-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="ba55b-106">As chamadas novas ou de entrada poderão ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="ba55b-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="ba55b-107">Essa política tem suporte para failover e recuperação de desastre em Pools de Front-Ends e em SBSs (Servidores de Ramificação Persistente) emparelhados.</span><span class="sxs-lookup"><span data-stu-id="ba55b-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="ba55b-108">Este tópico descreve as configurações de Opções de Disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ba55b-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="ba55b-109">Para obter informações sobre como instalar e configurar o recurso Opções de Disponibilidade, veja [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="ba55b-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="ba55b-110">Opções de configuração</span><span class="sxs-lookup"><span data-stu-id="ba55b-110">Configuration options</span></span>

<span data-ttu-id="ba55b-111">Se o recurso Opções de Disponibilidade estiver habilitado para a organização, todos os usuários da empresa, tanto os usuários Enterprise Voice quanto os não Enterprise Voice, poderão usar os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="ba55b-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="ba55b-112">Sinal de Ocupado quando Ocupado - Se o usuário estiver ocupado, as novas chamadas de entrada serão rejeitadas com um sinal de ocupado.</span><span class="sxs-lookup"><span data-stu-id="ba55b-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="ba55b-113">Caixa Postal quando Ocupado - Se o usuário estiver ocupado, as novas chamadas de entrada serão encaminhadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="ba55b-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="ba55b-114">O recurso Opções de Disponibilidade fornece a capacidade de failover.</span><span class="sxs-lookup"><span data-stu-id="ba55b-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="ba55b-115">Se ocorrer um problema e os usuários executarem failover em outro servidor front-end ou em outro pool no Skype for Business Server, as configurações de opções de ocupação serão preservadas.</span><span class="sxs-lookup"><span data-stu-id="ba55b-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="ba55b-116">Qualquer que seja a maneira de configurar as opções de disponibilidade, os usuários em uma chamada ou em conferência (ou aqueles com uma chamada em espera) não serão impedidos de iniciar novas chamadas ou conferências.  </span><span class="sxs-lookup"><span data-stu-id="ba55b-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="ba55b-117">Após a configuração, a configuração de opções de ocupado estará em vigor para todos os dispositivos e clientes de chamadas do Skype for Business do usuário.</span><span class="sxs-lookup"><span data-stu-id="ba55b-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="ba55b-118">Com base nas configurações de Opções de Disponibilidade do usuário, a chamada que é rejeitada ou enviada para a caixa postal não tocará em nenhum dos dispositivos de chamada do usuário (incluindo Macintosh, Área de Trabalho do Windows, clientes móveis ou telefones IP) nos quais ele esteja conectado.</span><span class="sxs-lookup"><span data-stu-id="ba55b-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="ba55b-119">Os usuários verão notificações de chamada perdida em seus clientes e dispositivos do Skype for Business, e eles serão notificados por e-mail também.</span><span class="sxs-lookup"><span data-stu-id="ba55b-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="ba55b-120">Os chamadores cuja chamada foi rejeitada devido ao ocupado em ocupado verão uma notificação no cliente do Skype for Business, informando que o usuário que ele tentou alcançar está ocupado em outra chamada.</span><span class="sxs-lookup"><span data-stu-id="ba55b-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="ba55b-121">Você pode configurar o recurso de opções de ocupado usando cmdlets do PowerShell do Skype for Business para:</span><span class="sxs-lookup"><span data-stu-id="ba55b-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="ba55b-122">Habilitar ou desabilitar a política de voz do recurso Opções de Disponibilidade para a empresa.</span><span class="sxs-lookup"><span data-stu-id="ba55b-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="ba55b-123">Administrar a opção Sinal de Ocupado quando Ocupado ou Caixa Postal quando Ocupado para todos os usuários da empresa.</span><span class="sxs-lookup"><span data-stu-id="ba55b-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="ba55b-124">Administrar a opção Sinal de Ocupado quando Ocupado ou Caixa Postal quando Ocupado para todos os usuários residentes em um Pool de Front-Ends específico.</span><span class="sxs-lookup"><span data-stu-id="ba55b-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="ba55b-125">Administrar a opção Sinal de Ocupado quando Ocupado ou Caixa Postal quando Ocupado para uma lista de usuários.</span><span class="sxs-lookup"><span data-stu-id="ba55b-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="ba55b-126">Administrar a opção Sinal de Ocupado quando Ocupado ou Caixa Postal quando Ocupado para um único usuário.</span><span class="sxs-lookup"><span data-stu-id="ba55b-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="ba55b-127">Interoperabilidade com aplicativos de voz</span><span class="sxs-lookup"><span data-stu-id="ba55b-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="ba55b-128">Opções ocupadas fornecem interoperabilidade com os seguintes aplicativos de voz no Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="ba55b-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="ba55b-129">Grupos de Resposta (RGS)</span><span class="sxs-lookup"><span data-stu-id="ba55b-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="ba55b-130">As configurações de Opções de Disponibilidade definidas nos números de Grupo de Resposta serão ignoradas pelo sistema; várias chamadas simultâneas serão permitidas. </span><span class="sxs-lookup"><span data-stu-id="ba55b-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="ba55b-131">A experiência de encaminhamento do Atendedor atual em Grupos de Resposta permanecerá inalterada para os Agentes com configurações de Opções de Disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ba55b-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="ba55b-132">As chamadas de Grupos de Resposta para usuários que são Agentes de Grupos de Resposta não serão controladas pelas configurações de Opções de Disponibilidade. Além disso, a experiência de RGS atual será mantida.</span><span class="sxs-lookup"><span data-stu-id="ba55b-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="ba55b-133">As chamadas para os Agentes, que não estiverem relacionadas a RGS, serão tratadas de acordo com as configurações de Opções de Disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ba55b-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="ba55b-134">Chamada de Equipe</span><span class="sxs-lookup"><span data-stu-id="ba55b-134">Team Call</span></span>
    
  - <span data-ttu-id="ba55b-135">As chamadas recebidas para os usuários configurados para uma chamada de equipe serão priorizadas para ignorar o ocupado em configurações de correio de voz ocupada e em ocupado.</span><span class="sxs-lookup"><span data-stu-id="ba55b-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="ba55b-136">A experiência de Chamada de Equipe atual permanecerá inalterada com as configurações de Opções de Disponibilidade definidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="ba55b-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="ba55b-137">As chamadas que não estiverem relacionadas à Chamada de Equipe serão tratadas conforme as configurações de Opções de Disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ba55b-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="ba55b-138">Delegação de chefe/administrador </span><span class="sxs-lookup"><span data-stu-id="ba55b-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="ba55b-139">As chamadas recebidas para os usuários configurados para um chefe/delegação de administrador, seja como chefe ou administrador, serão priorizadas para ignorar as configurações de correio de voz ocupada e de correio de voz em ocupado.</span><span class="sxs-lookup"><span data-stu-id="ba55b-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="ba55b-140">A experiência de Delegação de Chefe/Administrador atual permanecerá inalterada com as configurações de Opções de Disponibilidade definidas para administradores ou chefe.</span><span class="sxs-lookup"><span data-stu-id="ba55b-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="ba55b-141">As chamadas para administradores, que não estiverem relacionadas à Delegação de Chefe/Administrador, serão tratadas conforme as configurações de Opções de Disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ba55b-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="ba55b-142">Aparência de linha compartilhada   </span><span class="sxs-lookup"><span data-stu-id="ba55b-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="ba55b-143">As configurações de Opções de Disponibilidade nas contas de usuário configuradas para Aparência de Linha Compartilhada serão ignoradas. </span><span class="sxs-lookup"><span data-stu-id="ba55b-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="ba55b-144">A aparência nativa da aparência da linha compartilhada em opções ocupadas e correio de voz em ocupado será aceita em vez disso.</span><span class="sxs-lookup"><span data-stu-id="ba55b-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="ba55b-145">Serviço de estacionamento de chamada </span><span class="sxs-lookup"><span data-stu-id="ba55b-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="ba55b-146">As chamadas estacionadas que não foram atendidas e que retornam a tocar após determinado período poderão serão atendidas pelo usuário que as estacionou utilizando as configurações de Opções de Disponibilidade. </span><span class="sxs-lookup"><span data-stu-id="ba55b-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="ba55b-147">Chamada em conferência</span><span class="sxs-lookup"><span data-stu-id="ba55b-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="ba55b-148">Os usuários que estiverem em chamadas em conferência terão o status Ocupado, e as novas chamadas de entrada serão rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal conforme as configurações de Opções de Disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ba55b-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="ba55b-149">Os usuários em conferência não são impedidos de iniciar novas chamadas ou conferências conforme as configurações de Opções de Disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ba55b-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="ba55b-150">Os usuários em conferência ainda podem receber novos convites de conferência, mas novas chamadas ponto a ponto serão rejeitadas conforme as configurações de Opções de Disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ba55b-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="ba55b-151">Toque Simultâneo e Encaminhamento de Chamadas</span><span class="sxs-lookup"><span data-stu-id="ba55b-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="ba55b-152">O recurso Busy on Busy não é projetado para funcionar com Toque Simultâneo e Encaminhamento de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="ba55b-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

