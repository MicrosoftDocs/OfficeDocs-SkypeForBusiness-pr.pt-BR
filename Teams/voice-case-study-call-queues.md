---
title: Estudo de caso do Teams voice Contoso
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
description: Estudo de caso de voz do Teams para corporação multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918727"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="d4808-103">Estudo de caso da Contoso: Atendimentos automáticos e filas de chamada</span><span class="sxs-lookup"><span data-stu-id="d4808-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="d4808-104">A Contoso estava familiarizada com os atendimentos automáticos e filas de chamadas da implantação local do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d4808-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="d4808-105">Para entender como configurar os atendimentos automáticos na nuvem e filas de chamada, eles revisaram o Plano para os [atendimentos automáticos e filas de chamada do Teams.](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="d4808-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="d4808-106">Requisitos dependendo do tipo de site</span><span class="sxs-lookup"><span data-stu-id="d4808-106">Requirements depending on site type</span></span>

<span data-ttu-id="d4808-107">Dependendo do tipo de site, a Contoso tinha as seguintes necessidades:</span><span class="sxs-lookup"><span data-stu-id="d4808-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="d4808-108">Tipo de Site A: sistemas tradicionais de telefonia herdados</span><span class="sxs-lookup"><span data-stu-id="d4808-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="d4808-109">O Tipo de Site A é necessário para manter o mesmo número de telefone associado ao recepcionista do número dos seus atenderes automáticos.</span><span class="sxs-lookup"><span data-stu-id="d4808-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="d4808-110">Os principais departamentos de cada um desses sites teriam suas próprias filas de chamada que seriam encaminhada para os membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="d4808-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="d4808-111">Havia uma combinação de sites que usavam o Sistema de Telefonia com Roteamento Direto e Sistema de Telefonia com Planos de Chamada.</span><span class="sxs-lookup"><span data-stu-id="d4808-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="d4808-112">Tipo de site B: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="d4808-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="d4808-113">O tipo de site B tinha os atendimentos automáticos e filas de chamada existentes que precisavam migrar para o Teams.</span><span class="sxs-lookup"><span data-stu-id="d4808-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="d4808-114">A Contoso precisava manter os números de telefone associados aos atenderes automáticos.</span><span class="sxs-lookup"><span data-stu-id="d4808-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="d4808-115">A Contoso moveu a maioria desses sites para o Sistema de Telefonia com Planos de Chamada.</span><span class="sxs-lookup"><span data-stu-id="d4808-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="d4808-116">No entanto, nos poucos locais em que os Planos de Chamada não estão disponíveis, a Contoso moveu esses sites para uma configuração de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="d4808-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="d4808-117">Tipo de Site C: Skype for Business Enterprise Voice & tradicional sistema de telefonia herdado</span><span class="sxs-lookup"><span data-stu-id="d4808-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="d4808-118">O Tipo de Site C tinha os participantes automáticos existentes que residiam no sistema de telefonia herdado tradicional.</span><span class="sxs-lookup"><span data-stu-id="d4808-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="d4808-119">As decisões e configurações deste site eram as mesmas que o Tipo de Site A.</span><span class="sxs-lookup"><span data-stu-id="d4808-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="d4808-120">Para todos os tipos de site, a Contoso fez as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="d4808-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="d4808-121">P: Vamos usar números novos ou existentes?</span><span class="sxs-lookup"><span data-stu-id="d4808-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="d4808-122">R: A Contoso decidiu usar números de telefone existentes para serem atribuídos à conta de serviço do atender automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d4808-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="d4808-123">P: Quando o atender automático estará disponível para aceitar chamadas recebidas?</span><span class="sxs-lookup"><span data-stu-id="d4808-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="d4808-124">R: A Contoso decidiu definir o horário comercial e ter as chamadas recebidas após o horário comercial redirecionadas para um atender automático "horas extras".</span><span class="sxs-lookup"><span data-stu-id="d4808-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="d4808-125">P: Como as chamadas serão roteada para membros em uma fila de chamadas: roteamento de atendimento, série ou round?</span><span class="sxs-lookup"><span data-stu-id="d4808-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="d4808-126">R: A Contoso decidiu usar o roteamento do Attendant,</span><span class="sxs-lookup"><span data-stu-id="d4808-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="d4808-127">P: Como determinaremos quando um usuário deve ou não receber uma chamada?</span><span class="sxs-lookup"><span data-stu-id="d4808-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="d4808-128">R: A Contoso decidiu usar as opções de tratamento de chamadas para determinar se o agente está disponível: roteamento baseado em presença.</span><span class="sxs-lookup"><span data-stu-id="d4808-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="d4808-129">Configuração</span><span class="sxs-lookup"><span data-stu-id="d4808-129">Configuration</span></span>

<span data-ttu-id="d4808-130">As etapas para configurar um atendimento automático e uma fila de chamada incluem os seguintes descritos em [Gerenciar contas de recursos:](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="d4808-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="d4808-131">Obtenha um número de serviço.</span><span class="sxs-lookup"><span data-stu-id="d4808-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="d4808-132">Obtenha uma licença gratuita do Sistema de Telefonia – Usuário Virtual ou uma licença paga do Sistema telefônico para usar com a conta de recurso ou uma licença do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="d4808-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="d4808-133">Criar a conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="d4808-133">Create the resource account.</span></span> <span data-ttu-id="d4808-134">Um atendimento automático ou fila de chamada é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="d4808-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="d4808-135">Atribua o Sistema telefônico ou um sistema telefônico – licença de usuário virtual à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="d4808-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="d4808-136">Para obter mais informações, consulte [Microsoft 365 Phone System – Licença de Usuário Virtual.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)</span><span class="sxs-lookup"><span data-stu-id="d4808-136">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="d4808-137">Atribua um número de telefone de serviço à conta de recurso à onde você atribuiu licenças.</span><span class="sxs-lookup"><span data-stu-id="d4808-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="d4808-138">Criar uma fila de chamadas do Sistema de Telefonia ou um atender automático</span><span class="sxs-lookup"><span data-stu-id="d4808-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="d4808-139">Vincule a conta de recurso com uma fila de chamada ou um atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="d4808-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="d4808-140">Sites com Sistema telefônico com roteamento direto</span><span class="sxs-lookup"><span data-stu-id="d4808-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="d4808-141">A Contoso teve que configurar o número de telefone fornecido pela operadora local como o número de serviço no Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4808-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="d4808-142">Para configurar um número de telefone disponível por meio do Roteamento Direto, a Contoso seguiu as instruções localizadas em [Gerenciar Contas de Recursos.](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="d4808-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="d4808-143">Como o Office 365 não está ciente dos números de telefone locais, a Contoso usou o PowerShell para concluir a configuração.</span><span class="sxs-lookup"><span data-stu-id="d4808-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="d4808-144">Para configurar o atendimento automático na nuvem, a Contoso seguiu as etapas descritas [em Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="d4808-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="d4808-145">Para configurar uma fila de chamada na nuvem, a Contoso seguiu as etapas descritas em Criar uma fila [de chamada na nuvem.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="d4808-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="d4808-146">Sites com Sistema de Telefonia com plano de Chamada</span><span class="sxs-lookup"><span data-stu-id="d4808-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="d4808-147">A Contoso teve que fazer a portabilidade do número de telefone usado para os atenderes automáticos do Skype for Business Enterprise Voice para o Sistema Telefônico do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4808-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="d4808-148">Isso permitiu que o mesmo número fosse atribuído como um número de serviço para ser usado como um atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="d4808-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="d4808-149">Para fazer a portabilidade do número de telefone, a Contoso seguiu as instruções em Transferir números de telefone para o [Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) e obteve orientações adicionais em Gerenciar números de [telefone para sua organização.](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="d4808-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="d4808-150">Para configurar um atendimento automático na nuvem, a Contoso seguiu as etapas descritas [em Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="d4808-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="d4808-151">Para configurar uma fila de chamada na nuvem, a Contoso seguiu as etapas descritas em Criar uma fila [de chamada na nuvem.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="d4808-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 