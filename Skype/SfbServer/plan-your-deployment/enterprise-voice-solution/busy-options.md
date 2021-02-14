---
title: Planejar opções de ocupado para o Skype for Business Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Leia sobre o recurso Opções de Ocupado no Skype for Business Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813691"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="234aa-103">Planejar opções de ocupado para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="234aa-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="234aa-104">Leia sobre o recurso Opções de Ocupado no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="234aa-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="234aa-105">Opções de Ocupado é uma nova política de voz introduzida na Atualização Cumulativa de julho de 2016 que permite configurar como as chamadas de entrada são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera.</span><span class="sxs-lookup"><span data-stu-id="234aa-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="234aa-106">Chamadas novas ou de entrada podem ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="234aa-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="234aa-107">A política de Opções de Ocupado é suportada para failover e recuperação de desastre em Pools de Front-End emparelhados e Servidores de Filial Survivable (SBS).</span><span class="sxs-lookup"><span data-stu-id="234aa-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="234aa-108">Este tópico descreve os recursos das Opções de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="234aa-109">Para obter informações sobre como instalar e configurar Opções de Ocupado, consulte Instalar e configurar Opções de Ocupado [para o Skype for Business Server.](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="234aa-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="234aa-110">Opções de configuração</span><span class="sxs-lookup"><span data-stu-id="234aa-110">Configuration options</span></span>

<span data-ttu-id="234aa-111">Se as Opções de Ocupado estiver habilitada para a organização, todos os usuários da sua organização, tanto os usuários do Enterprise Voice quanto os que não são do Enterprise Voice, poderão usar os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="234aa-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="234aa-112">Ocupado quando ocupado - Em que novas chamadas de entrada serão rejeitadas com um sinal de ocupado se o usuário estiver ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="234aa-113">Caixa Postal quando Ocupado - Em que novas chamadas de entrada serão encaminhadas para a caixa postal se o usuário estiver ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="234aa-114">O recurso Opções de Ocupado fornece o recurso de failover.</span><span class="sxs-lookup"><span data-stu-id="234aa-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="234aa-115">Se ocorrer um problema e os usuários efetuarem fail over para outro Servidor front-end ou para outro pool no Skype for Business Server, suas configurações de Opções de Ocupado serão preservadas.</span><span class="sxs-lookup"><span data-stu-id="234aa-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="234aa-116">Independentemente de como suas opções de ocupado estão configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências.</span><span class="sxs-lookup"><span data-stu-id="234aa-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="234aa-117">Após a configuração, a configuração Opções de Ocupado está em vigor para todos os clientes e dispositivos de chamada do Skype for Business do usuário.</span><span class="sxs-lookup"><span data-stu-id="234aa-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="234aa-118">Com base nas configurações de Opções de Ocupado do usuário, a chamada que é rejeitada ou enviada para a caixa postal não tocaria em nenhum dos dispositivos de chamada do usuário, incluindo Macintosh, Área de Trabalho do Windows, clientes móveis ou telefones IP, nos quais o usuário está conectado.</span><span class="sxs-lookup"><span data-stu-id="234aa-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="234aa-119">Os usuários verão notificações de chamada perdida em seus clientes e dispositivos do Skype for Business e também serão notificados por email.</span><span class="sxs-lookup"><span data-stu-id="234aa-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="234aa-120">Os chamadores cuja chamada foi rejeitada devido a Ocupado quando Ocupado verão uma notificação em seu cliente do Skype for Business informando que o usuário que tentou acessar está ocupado em outra chamada.</span><span class="sxs-lookup"><span data-stu-id="234aa-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="234aa-121">Você pode configurar o recurso Opções de Ocupado usando os cmdlets do PowerShell do Skype for Business para:</span><span class="sxs-lookup"><span data-stu-id="234aa-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="234aa-122">Habilitar ou desabilitar a política de Voz de Opções de Ocupado para a empresa.</span><span class="sxs-lookup"><span data-stu-id="234aa-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="234aa-123">Administrar a caixa postal quando ocupado ou quando ocupado para todos os usuários na empresa.</span><span class="sxs-lookup"><span data-stu-id="234aa-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="234aa-124">Administrar a caixa postal quando ocupado ou quando ocupado para todos os usuários que estão em um pool de Front-End específico.</span><span class="sxs-lookup"><span data-stu-id="234aa-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="234aa-125">Administrar a caixa postal quando ocupado ou ocupado para uma lista de usuários.</span><span class="sxs-lookup"><span data-stu-id="234aa-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="234aa-126">Administrar a caixa postal quando ocupado ou quando ocupado para um único usuário.</span><span class="sxs-lookup"><span data-stu-id="234aa-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="234aa-127">Interoperabilidade com aplicativos de voz</span><span class="sxs-lookup"><span data-stu-id="234aa-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="234aa-128">Opções de ocupado fornece interoperabilidade com os seguintes aplicativos de voz no Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="234aa-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="234aa-129">Grupos de Resposta (RGS)</span><span class="sxs-lookup"><span data-stu-id="234aa-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="234aa-130">Opções de Ocupado definidas nos números do Grupo de Resposta serão ignoradas pelo sistema; várias chamadas simultâneas serão permitidas.</span><span class="sxs-lookup"><span data-stu-id="234aa-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="234aa-131">A experiência de roteamento atual do Attendant nos Grupos de Resposta permanecerá inalterada para os Agentes com as configurações de Opções de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="234aa-132">As chamadas provenientes dos Grupos de Resposta para os usuários que são Agentes de Grupos de Resposta não serão aceleradas pelas configurações de Opções de Ocupado e a experiência atual do RGS será mantida.</span><span class="sxs-lookup"><span data-stu-id="234aa-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="234aa-133">As chamadas não relacionadas a RGS para os Agentes serão aprinciadas pelas configurações de Opções de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="234aa-134">Chamada de Equipe</span><span class="sxs-lookup"><span data-stu-id="234aa-134">Team Call</span></span>
    
  - <span data-ttu-id="234aa-135">As chamadas de entrada para usuários que estão configuradas para uma Chamada de Equipe serão priorizadas para ignorar as configurações de Ocupado quando Ocupado e Caixa Postal quando Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="234aa-136">A experiência atual da Chamada de Equipe permanecerá inalterada com as Opções de Ocupado definidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="234aa-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="234aa-137">As chamadas não relacionadas à Chamada de Equipe para esses usuários serão aprididas pelas configurações de Opções de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="234aa-138">Delegação de chefe/administrador</span><span class="sxs-lookup"><span data-stu-id="234aa-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="234aa-139">As chamadas de entrada para usuários que estão configuradas para delegação de chefe/administrador como chefe ou administrador serão priorizadas para ignorar as configurações de Ocupado quando Ocupado e Caixa Postal quando Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="234aa-140">A experiência atual de Delegação de Chefe/Administrador permanecerá inalterada com as Opções de Ocupado definidas para Administradores ou Chefe.</span><span class="sxs-lookup"><span data-stu-id="234aa-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="234aa-141">As chamadas não relacionadas à Delegação de Chefe/Administrador para Administradores serão acovadas pelas configurações de Opções de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="234aa-142">Aparência de linha compartilhada</span><span class="sxs-lookup"><span data-stu-id="234aa-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="234aa-143">As configurações de Opções de Ocupado em contas de usuário configuradas para Aparência de Linha Compartilhada serão ignoradas.</span><span class="sxs-lookup"><span data-stu-id="234aa-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="234aa-144">Em vez disso, as opções de Ocupado ocupado quando ocupado e caixa postal quando ocupado da Aparência de linha compartilhada serão a vontade.</span><span class="sxs-lookup"><span data-stu-id="234aa-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="234aa-145">Serviço de Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="234aa-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="234aa-146">As chamadas estacionadas que não foram recuperadas e estão tocando de volta devido ao tempo final poderão tocar para o usuário que estacionou a chamada pelas Opções de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="234aa-147">Conferência de Chamada</span><span class="sxs-lookup"><span data-stu-id="234aa-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="234aa-148">Os usuários em chamadas em conferência são considerados Ocupados e novas chamadas de entrada serão rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal de acordo com as configurações de Opções de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="234aa-149">Os usuários em conferências não são impedidos de iniciar novas chamadas ou conferências por opções de ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="234aa-150">Os usuários em conferências ainda podem receber novos convites de conferência, mas novas chamadas ponto a ponto serão rejeitadas de acordo com as configurações de Opções de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="234aa-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="234aa-151">Toque simultâneo e encaminhamento de chamada</span><span class="sxs-lookup"><span data-stu-id="234aa-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="234aa-152">O recurso Ocupado quando Ocupado não foi projetado para funcionar com Toque Simultâneo e Encaminhamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="234aa-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

