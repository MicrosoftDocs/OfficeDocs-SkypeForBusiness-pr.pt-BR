---
title: Estudo de caso de voz do Teams Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudo de caso de voz do Teams para corporação multi-nacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121289"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="c9710-103">Estudo de caso da Contoso: Atendimentos automáticos e filas de chamada</span><span class="sxs-lookup"><span data-stu-id="c9710-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="c9710-104">A Contoso estava familiarizada com os atendimentos automáticos e filas de chamadas de sua implantação local do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c9710-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="c9710-105">Para entender como configurar os atendimentos automáticos de nuvem e filas de chamada, eles revisaram [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="c9710-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="c9710-106">Requisitos dependendo do tipo de site</span><span class="sxs-lookup"><span data-stu-id="c9710-106">Requirements depending on site type</span></span>

<span data-ttu-id="c9710-107">Dependendo do tipo de site, a Contoso tinha as seguintes necessidades:</span><span class="sxs-lookup"><span data-stu-id="c9710-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="c9710-108">Tipo de site A: sistemas de telefonia herdados tradicionais</span><span class="sxs-lookup"><span data-stu-id="c9710-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="c9710-109">Tipo de site A necessário para manter o mesmo número de telefone associado à recepcionista como o número de seus atendimentos automáticos.</span><span class="sxs-lookup"><span data-stu-id="c9710-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="c9710-110">Os principais departamentos de cada um desses sites teriam suas próprias filas de chamada que seriam roteada para os membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="c9710-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="c9710-111">Houve uma mistura de sites que usavam o Sistema de Telefonia com Roteamento Direto e Sistema de Telefonia com Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="c9710-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="c9710-112">Tipo de site B: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="c9710-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="c9710-113">O Tipo de Site B tinha atendentes automáticos e filas de chamada existentes que precisavam migrar para o Teams.</span><span class="sxs-lookup"><span data-stu-id="c9710-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="c9710-114">A Contoso precisava manter os números de telefone associados aos atendimentos automáticos.</span><span class="sxs-lookup"><span data-stu-id="c9710-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="c9710-115">A Contoso moveu a maioria desses sites para o Sistema de Telefonia com Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="c9710-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="c9710-116">No entanto, nos poucos locais em que Planos de Chamadas não estava disponível, a Contoso moveu esses sites para uma configuração de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="c9710-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="c9710-117">Tipo de site C: Skype for Business Enterprise Voice & sistema de telefonia herdado tradicional</span><span class="sxs-lookup"><span data-stu-id="c9710-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="c9710-118">O Tipo de Site C tinha os atendimentos automáticos existentes que residiam no sistema de telefonia herdado tradicional.</span><span class="sxs-lookup"><span data-stu-id="c9710-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="c9710-119">As decisões e configurações para este site eram as mesmas que o Tipo de Site A.</span><span class="sxs-lookup"><span data-stu-id="c9710-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="c9710-120">Para todos os tipos de site, a Contoso fez as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="c9710-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="c9710-121">P: Vamos usar números novos ou existentes?</span><span class="sxs-lookup"><span data-stu-id="c9710-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="c9710-122">R: A Contoso decidiu usar números de telefone existentes para serem atribuídos à conta de serviço do atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="c9710-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="c9710-123">P: Quando o atendimento automático estará disponível para aceitar chamadas de entrada?</span><span class="sxs-lookup"><span data-stu-id="c9710-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="c9710-124">R: a Contoso decidiu definir o horário comercial e ter chamadas recebidas após o horário comercial redirecionadas para um atendimento automático "pós-horário".</span><span class="sxs-lookup"><span data-stu-id="c9710-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="c9710-125">P: Como as chamadas serão roteados para membros em uma fila de chamadas: roteamento de robin de atendimento, série ou round?</span><span class="sxs-lookup"><span data-stu-id="c9710-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="c9710-126">R: a Contoso decidiu usar o roteamento de atendimento,</span><span class="sxs-lookup"><span data-stu-id="c9710-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="c9710-127">P: Como determinaremos quando um usuário deve ou não receber uma chamada?</span><span class="sxs-lookup"><span data-stu-id="c9710-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="c9710-128">R: A Contoso decidiu usar opções de tratamento de chamadas para determinar se o agente está disponível: roteamento baseado em presença.</span><span class="sxs-lookup"><span data-stu-id="c9710-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="c9710-129">Configuração</span><span class="sxs-lookup"><span data-stu-id="c9710-129">Configuration</span></span>

<span data-ttu-id="c9710-130">As etapas para configurar um atendimento automático e uma fila de chamada incluem o seguinte descrito em [Gerenciar contas de recursos](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="c9710-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="c9710-131">Obtenha um número de serviço.</span><span class="sxs-lookup"><span data-stu-id="c9710-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="c9710-132">Obtenha um Sistema de Telefonia gratuito - Licença do Usuário Virtual ou uma licença do Sistema de Telefonia paga a ser usada com a conta de recurso ou uma licença do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="c9710-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="c9710-133">Crie a conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="c9710-133">Create the resource account.</span></span> <span data-ttu-id="c9710-134">Um atendimento automático ou fila de chamada é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="c9710-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="c9710-135">Atribua o Sistema de Telefonia ou um Sistema de Telefonia - Licença de usuário virtual à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="c9710-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="c9710-136">Para obter mais informações, consulte [Microsoft 365 Phone System – Licença de usuário virtual.](./teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="c9710-136">For more information, see [Microsoft 365 Phone System – Virtual User license](./teams-add-on-licensing/virtual-user.md).</span></span>

5. <span data-ttu-id="c9710-137">Atribua um número de telefone de serviço à conta de recurso à que você atribuiu licenças.</span><span class="sxs-lookup"><span data-stu-id="c9710-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="c9710-138">Criar uma fila de chamadas do Sistema de Telefonia ou um atendimento automático</span><span class="sxs-lookup"><span data-stu-id="c9710-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="c9710-139">Vincule a conta de recurso com uma fila de chamada ou um atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="c9710-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="c9710-140">Sites com Sistema de Telefonia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="c9710-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="c9710-141">A Contoso precisou configurar o número de telefone fornecido pela operadora local como o número de serviço no Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9710-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="c9710-142">Para configurar um número de telefone disponível por meio do Roteamento Direto, a Contoso seguiu as instruções localizadas em [Gerenciar Contas de Recursos.](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="c9710-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="c9710-143">Como o Office 365 não está ciente dos números de telefone locais, a Contoso usou o PowerShell para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="c9710-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="c9710-144">Para configurar o atendimento automático na nuvem, a Contoso seguiu as etapas descritas [em Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="c9710-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="c9710-145">Para configurar uma fila de chamada na nuvem, a Contoso seguiu as etapas descritas em [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="c9710-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="c9710-146">Sites com Sistema de Telefonia com Plano de Chamadas</span><span class="sxs-lookup"><span data-stu-id="c9710-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="c9710-147">A Contoso precisou por o número de telefone usado para o Skype for Business Enterprise Voice atendimento automático para o Sistema de Telefonia do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9710-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="c9710-148">Isso permitiu que o mesmo número fosse atribuído como um número de serviço para uso como um atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="c9710-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="c9710-149">Para por o número de telefone, a Contoso seguiu as instruções em Transferir números de telefone para o [Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) e obteve orientações adicionais em Gerenciar números de telefone [para sua organização.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="c9710-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) and obtained additional guidance at [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="c9710-150">Para configurar um atendimento automático na nuvem, a Contoso seguiu as etapas descritas em [Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="c9710-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="c9710-151">Para configurar uma fila de chamada na nuvem, a Contoso seguiu as etapas descritas em [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="c9710-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

