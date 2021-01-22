---
title: Estudo de caso da Contoso Voice Teams
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
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918727"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="4d4fd-103">Estudo de caso da Contoso: atendedores automáticos e filas de chamadas</span><span class="sxs-lookup"><span data-stu-id="4d4fd-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="4d4fd-104">A contoso já está familiarizada com atendedores automáticos e filas de chamadas na implantação do Skype for Business local.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="4d4fd-105">Para compreender como configurar atendedores automáticos na nuvem e filas de chamadas, eles revisaram o [plano para atendedores automáticos e filas de chamadas do teams](plan-auto-attendant-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="4d4fd-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="4d4fd-106">Requisitos dependendo do tipo de site</span><span class="sxs-lookup"><span data-stu-id="4d4fd-106">Requirements depending on site type</span></span>

<span data-ttu-id="4d4fd-107">Dependendo do tipo de site, a Contoso tinha as seguintes necessidades:</span><span class="sxs-lookup"><span data-stu-id="4d4fd-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="4d4fd-108">Tipo de site A: sistemas tradicionais de telefonia herdada</span><span class="sxs-lookup"><span data-stu-id="4d4fd-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="4d4fd-109">Tipo de site A necessário para manter o mesmo número de telefone associado ao recepcionista como o número dos atendedores automáticos.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="4d4fd-110">Os principais departamentos para cada um desses sites teriam suas próprias filas de chamadas que roteiariam para os membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="4d4fd-111">Houve uma mistura de sites que usaram o sistema telefônico com roteamento direto e sistema telefônico com planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="4d4fd-112">Tipo de site B: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="4d4fd-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="4d4fd-113">O tipo de site B tinha atendedores automáticos e filas de chamadas existentes que precisavam migrar para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="4d4fd-114">A contoso precisou manter os números de telefone associados aos atendedores automáticos.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="4d4fd-115">A contoso moveu a maioria desses sites para o sistema telefônico com planos de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="4d4fd-116">No entanto, nos poucos locais em que os planos de chamada não estavam disponíveis, a contoso moveu esses sites para uma configuração de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="4d4fd-117">Tipo de site C: Skype for Business Enterprise Voice & sistema de telefonia tradicional herdado</span><span class="sxs-lookup"><span data-stu-id="4d4fd-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="4d4fd-118">Tipo de site C tinha atendedores automáticos existentes que residiam no sistema de telefonia tradicional herdada.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="4d4fd-119">As decisões e configurações para este site foram iguais às do tipo de site A.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="4d4fd-120">Para todos os tipos de sites, a contoso fez as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="4d4fd-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="4d4fd-121">P: vamos usar números novos ou existentes?</span><span class="sxs-lookup"><span data-stu-id="4d4fd-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="4d4fd-122">R: a Contoso decidiu usar números de telefone existentes para ser atribuído à conta de serviço para o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="4d4fd-123">P: quando o atendedor automático estará disponível para aceitar as chamadas recebidas?</span><span class="sxs-lookup"><span data-stu-id="4d4fd-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="4d4fd-124">R: a Contoso decidiu definir o horário comercial e ter chamadas recebidas após o horário comercial ser redirecionado para o atendedor automático de "depois de horas".</span><span class="sxs-lookup"><span data-stu-id="4d4fd-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="4d4fd-125">P: como as chamadas serão encaminhadas para os membros de uma fila de chamadas: roteamento de atendedor, serial ou Round Robin?</span><span class="sxs-lookup"><span data-stu-id="4d4fd-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="4d4fd-126">R: contoso decidiu usar o roteamento de atendedor,</span><span class="sxs-lookup"><span data-stu-id="4d4fd-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="4d4fd-127">P: como determinamos quando um usuário deve ou não ter uma chamada?</span><span class="sxs-lookup"><span data-stu-id="4d4fd-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="4d4fd-128">R: a Contoso decidiu usar as opções de gerenciamento de chamadas para determinar se o agente está disponível: roteamento baseado em presença.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="4d4fd-129">Configuração</span><span class="sxs-lookup"><span data-stu-id="4d4fd-129">Configuration</span></span>

<span data-ttu-id="4d4fd-130">As etapas para configurar um atendedor automático e uma fila de chamada incluem o seguinte descrito em [gerenciar contas de recursos](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="4d4fd-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="4d4fd-131">Obter um número de serviço.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="4d4fd-132">Obter um sistema telefônico gratuito-licença de usuário virtual ou uma licença do sistema de telefonia paga para uso com a conta do recurso ou uma licença do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="4d4fd-133">Criar a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-133">Create the resource account.</span></span> <span data-ttu-id="4d4fd-134">Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="4d4fd-135">Atribua o sistema telefônico ou um sistema telefônico-licença de usuário virtual para a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="4d4fd-136">Para obter mais informações, consulte [sistema telefônico Microsoft 365 – licença de usuário virtual](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span><span class="sxs-lookup"><span data-stu-id="4d4fd-136">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="4d4fd-137">Atribua um número de telefone de serviço à conta de recurso à qual você atribuiu licenças.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="4d4fd-138">Criar uma fila de chamadas do sistema telefônico ou um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="4d4fd-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="4d4fd-139">Vincule a conta do recurso a uma fila de chamadas ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="4d4fd-140">Sites com sistema telefônico com roteamento direto</span><span class="sxs-lookup"><span data-stu-id="4d4fd-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="4d4fd-141">A contoso precisou configurar o número de telefone fornecido pela operadora local como o número de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="4d4fd-142">Para configurar um número de telefone disponível por meio do direcionamento direto, a contoso seguiu as instruções localizadas em [gerenciar contas de recursos](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="4d4fd-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="4d4fd-143">Como o Office 365 não reconhece os números de telefone locais, a contoso usava o PowerShell para concluir a configuração.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="4d4fd-144">Para configurar o atendedor automático na nuvem, a contoso seguiu as etapas descritas em [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="4d4fd-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="4d4fd-145">Para configurar uma fila de chamada em nuvem, a contoso seguiu as etapas descritas em [criar uma fila de chamadas em nuvem](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="4d4fd-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="4d4fd-146">Sites com o sistema telefônico com plano de chamadas</span><span class="sxs-lookup"><span data-stu-id="4d4fd-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="4d4fd-147">A Contoso tinha que portar o número de telefone usado para atendedores automáticos do Skype for Business Enterprise Voice ao sistema telefônico do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="4d4fd-148">Isso permitia que o mesmo número fosse atribuído como um número de serviço para uso como atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="4d4fd-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="4d4fd-149">Para portar o número de telefone, a contoso seguiu as instruções em [transferir números de telefone para o Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) e obter orientação adicional em [gerenciar números de telefone para sua organização](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="4d4fd-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="4d4fd-150">Para configurar um atendedor automático na nuvem, a contoso seguiu as etapas descritas em [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="4d4fd-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="4d4fd-151">Para configurar uma fila de chamada em nuvem, a contoso seguiu as etapas descritas em [criar uma fila de chamadas em nuvem](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="4d4fd-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 