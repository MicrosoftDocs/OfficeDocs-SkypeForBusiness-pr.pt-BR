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
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785943"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="ed020-103">Estudo de caso da Contoso: atendedores automáticos e filas de chamadas</span><span class="sxs-lookup"><span data-stu-id="ed020-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="ed020-104">A contoso já está familiarizada com atendedores automáticos e filas de chamadas na implantação do Skype for Business local.</span><span class="sxs-lookup"><span data-stu-id="ed020-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="ed020-105">Para entender como configurar atendedores automáticos na nuvem, eles revisaram [o que são atendedores automáticos da nuvem? e o](what-are-phone-system-auto-attendants.md) [exemplo de pequena empresa – configurar o tutorial do atendedor automático](tutorial-org-aa.yml).</span><span class="sxs-lookup"><span data-stu-id="ed020-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="ed020-106">Para saber mais sobre as opções disponíveis para configurar filas de chamadas, a contoso analisou [a criação de uma fila de chamadas em nuvem](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="ed020-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="ed020-107">Requisitos dependendo do tipo de site</span><span class="sxs-lookup"><span data-stu-id="ed020-107">Requirements depending on site type</span></span>

<span data-ttu-id="ed020-108">Dependendo do tipo de site, a Contoso tinha as seguintes necessidades:</span><span class="sxs-lookup"><span data-stu-id="ed020-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="ed020-109">Tipo de site A: sistemas tradicionais de telefonia herdada</span><span class="sxs-lookup"><span data-stu-id="ed020-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="ed020-110">Tipo de site A necessário para manter o mesmo número de telefone associado ao recepcionista como o número dos atendedores automáticos.</span><span class="sxs-lookup"><span data-stu-id="ed020-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="ed020-111">Os principais departamentos para cada um desses sites teriam suas próprias filas de chamadas que roteiariam para os membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="ed020-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="ed020-112">Houve uma mistura de sites que usaram o sistema telefônico com roteamento direto e sistema telefônico com planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="ed020-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="ed020-113">Tipo de site B: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ed020-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="ed020-114">O tipo de site B tinha atendedores automáticos e filas de chamadas existentes que precisavam migrar para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ed020-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="ed020-115">A contoso precisou manter os números de telefone associados aos atendedores automáticos.</span><span class="sxs-lookup"><span data-stu-id="ed020-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="ed020-116">A contoso moveu a maioria desses sites para o sistema telefônico com planos de chamadas.</span><span class="sxs-lookup"><span data-stu-id="ed020-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="ed020-117">No entanto, nos poucos locais em que os planos de chamada não estavam disponíveis, a contoso moveu esses sites para uma configuração de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="ed020-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="ed020-118">Tipo de site C: Skype for Business Enterprise Voice & sistema de telefonia tradicional herdado</span><span class="sxs-lookup"><span data-stu-id="ed020-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="ed020-119">Tipo de site C tinha atendedores automáticos existentes que residiam no sistema de telefonia tradicional herdada.</span><span class="sxs-lookup"><span data-stu-id="ed020-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="ed020-120">As decisões e configurações para este site foram iguais às do tipo de site A.</span><span class="sxs-lookup"><span data-stu-id="ed020-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="ed020-121">Para todos os tipos de sites, a contoso fez as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="ed020-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="ed020-122">P: vamos usar números novos ou existentes?</span><span class="sxs-lookup"><span data-stu-id="ed020-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="ed020-123">R: a Contoso decidiu usar números de telefone existentes para ser atribuído à conta de serviço para o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ed020-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="ed020-124">P: quando o atendedor automático estará disponível para aceitar as chamadas recebidas?</span><span class="sxs-lookup"><span data-stu-id="ed020-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="ed020-125">R: a Contoso decidiu definir o horário comercial e ter chamadas recebidas após o horário comercial ser redirecionado para o atendedor automático de "depois de horas".</span><span class="sxs-lookup"><span data-stu-id="ed020-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="ed020-126">P: como as chamadas serão encaminhadas para os membros de uma fila de chamadas: roteamento de atendedor, serial ou Round Robin?</span><span class="sxs-lookup"><span data-stu-id="ed020-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="ed020-127">R: contoso decidiu usar o roteamento de atendedor,</span><span class="sxs-lookup"><span data-stu-id="ed020-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="ed020-128">P: como determinamos quando um usuário deve ou não ter uma chamada?</span><span class="sxs-lookup"><span data-stu-id="ed020-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="ed020-129">R: a Contoso decidiu usar as opções de gerenciamento de chamadas para determinar se o agente está disponível: roteamento baseado em presença.</span><span class="sxs-lookup"><span data-stu-id="ed020-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="ed020-130">Configuração</span><span class="sxs-lookup"><span data-stu-id="ed020-130">Configuration</span></span>

<span data-ttu-id="ed020-131">As etapas para configurar um atendedor automático e uma fila de chamada incluem o seguinte descrito em [gerenciar contas de recursos](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="ed020-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="ed020-132">Obter um número de serviço.</span><span class="sxs-lookup"><span data-stu-id="ed020-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="ed020-133">Obter um sistema telefônico gratuito-licença de usuário virtual ou uma licença do sistema de telefonia paga para uso com a conta do recurso ou uma licença do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="ed020-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="ed020-134">Criar a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="ed020-134">Create the resource account.</span></span> <span data-ttu-id="ed020-135">Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="ed020-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="ed020-136">Atribua o sistema telefônico ou um sistema telefônico-licença de usuário virtual para a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="ed020-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="ed020-137">Para obter mais informações, consulte [sistema telefônico Microsoft 365 – licença de usuário virtual](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span><span class="sxs-lookup"><span data-stu-id="ed020-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="ed020-138">Atribua um número de telefone de serviço à conta de recurso à qual você atribuiu licenças.</span><span class="sxs-lookup"><span data-stu-id="ed020-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="ed020-139">Criar uma fila de chamadas do sistema telefônico ou um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="ed020-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="ed020-140">Vincule a conta do recurso a uma fila de chamadas ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ed020-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="ed020-141">Sites com sistema telefônico com roteamento direto</span><span class="sxs-lookup"><span data-stu-id="ed020-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="ed020-142">A contoso precisou configurar o número de telefone fornecido pela operadora local como o número de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed020-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="ed020-143">Para configurar um número de telefone disponível por meio do direcionamento direto, a contoso seguiu as instruções localizadas em [gerenciar contas de recursos](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="ed020-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="ed020-144">Como o Office 365 não reconhece os números de telefone locais, a contoso usava o PowerShell para concluir a configuração.</span><span class="sxs-lookup"><span data-stu-id="ed020-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="ed020-145">Para configurar o atendedor automático na nuvem, a contoso seguiu as etapas descritas em [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="ed020-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="ed020-146">Para configurar uma fila de chamada em nuvem, a contoso seguiu as etapas descritas em [criar uma fila de chamadas em nuvem](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="ed020-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="ed020-147">Sites com o sistema telefônico com plano de chamadas</span><span class="sxs-lookup"><span data-stu-id="ed020-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="ed020-148">A Contoso tinha que portar o número de telefone usado para atendedores automáticos do Skype for Business Enterprise Voice ao sistema telefônico do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed020-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="ed020-149">Isso permitia que o mesmo número fosse atribuído como um número de serviço para uso como atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ed020-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="ed020-150">Para portar o número de telefone, a contoso seguiu as instruções em [transferir números de telefone para o Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) e obter orientação adicional em [gerenciar números de telefone para sua organização](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="ed020-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="ed020-151">Para configurar um atendedor automático na nuvem, a contoso seguiu as etapas descritas em [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="ed020-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="ed020-152">Para configurar uma fila de chamada em nuvem, a contoso seguiu as etapas descritas em [criar uma fila de chamadas em nuvem](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="ed020-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 