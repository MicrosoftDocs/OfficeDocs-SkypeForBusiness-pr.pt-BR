---
title: Implantação do Cloud Voice
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/10/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Orientações práticas para a implantação dos recursos de Cloud Voice no Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4828cb7c27c53387e0efae800167cef1b53dd4b6
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="ea467-103">Implantação do Cloud Voice</span><span class="sxs-lookup"><span data-stu-id="ea467-103">Cloud voice deployment</span></span>

<span data-ttu-id="ea467-104">Teams da Microsoft, o hub para o trabalho em equipe e comunicações no Office 365, agora oferece conferência de áudio e o sistema telefônico com os recursos de chamada planos para atender a requisitos de negócios adicionais estendendo a reunião de equipes e chamando experiência para incluir parceiros externos conectado por meio da rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="ea467-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>
 
<span data-ttu-id="ea467-105">Esta página será atualizada conforme outros recursos do Cloud Voice do Microsoft Teams forem lançados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="ea467-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="ea467-106">Audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea467-106">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="ea467-107">A Audioconferência do Office 365  permite que os participantes ingressem em reuniões do Microsoft Teams usando qualquer telefone.</span><span class="sxs-lookup"><span data-stu-id="ea467-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="ea467-108">Eis o que você obtém com a [Audioconferência](https://go.microsoft.com/fwlink/?linkid=858992) no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea467-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="ea467-109">Sistema telefônico com planos de chamada em equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ea467-109">Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="ea467-110">O Sistema de Telefonia é um recurso do Office 365 que permite gerenciar o encaminhamento de chamadas, políticas e o provisionamento de usuários.</span><span class="sxs-lookup"><span data-stu-id="ea467-110">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="ea467-111">Isso inclui o sistema de gerenciamento de chamadas telefônicas, o encaminhamento e o controle de chamadas.</span><span class="sxs-lookup"><span data-stu-id="ea467-111">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="ea467-112">Os Planos de Chamadas do Office 365 são um serviço complementar ao recurso Sistema de Telefonia, fornecido pelo Microsoft Teams e pelo Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ea467-112">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="ea467-113">Planos de chamadas fornecem as pessoas na sua empresa com um telefone principal do número e permite que eles façam e recebam chamadas telefônicas fora da sua organização no PSTN.</span><span class="sxs-lookup"><span data-stu-id="ea467-113">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="ea467-114">Para saber mais, leia [Isto é o que você obtém com o Sistema de Telefonia no Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) e [O que são os Planos de Chamadas no Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span><span class="sxs-lookup"><span data-stu-id="ea467-114">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>


## <a name="practical-guidance-for-audio-conferencing-and-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="ea467-115">Orientação prática para conferência de áudio e o sistema telefônico com planos de chamada no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea467-115">Practical guidance for Audio Conferencing and Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="ea467-116">Esta orientação prática é organizada usando o framework do Office 365 FastTrack cliente jornada e seus três fases&mdash;Envision, integrado e o valor de unidade.</span><span class="sxs-lookup"><span data-stu-id="ea467-116">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="ea467-117">Ele foi projetado para ajudá-lo a planejar, entregar e operar uma conferência de áudio ou o sistema telefônico bem-sucedida com implementação chamando planos.</span><span class="sxs-lookup"><span data-stu-id="ea467-117">It's intended to help you plan, deliver, and operate a successful Audio Conferencing or Phone System with Calling Plans implementation.</span></span>

|<span data-ttu-id="ea467-118">Concepção</span><span class="sxs-lookup"><span data-stu-id="ea467-118">Envision</span></span>  |<span data-ttu-id="ea467-119">Integração</span><span class="sxs-lookup"><span data-stu-id="ea467-119">Onboard</span></span>  |<span data-ttu-id="ea467-120">Gerar valor</span><span class="sxs-lookup"><span data-stu-id="ea467-120">Drive Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ea467-121">Definir meu sucesso</span><span class="sxs-lookup"><span data-stu-id="ea467-121">Define my success</span></span> <br> <span data-ttu-id="ea467-122">Tomar decisões meu serviço</span><span class="sxs-lookup"><span data-stu-id="ea467-122">Make my service decisions</span></span> <br> <span data-ttu-id="ea467-123">Avaliar o meu ambiente</span><span class="sxs-lookup"><span data-stu-id="ea467-123">Evaluate my environment</span></span> <br> <span data-ttu-id="ea467-124">Planejar o meu gerenciamento de serviço</span><span class="sxs-lookup"><span data-stu-id="ea467-124">Plan my service management</span></span> <br> <span data-ttu-id="ea467-125">Planejar a experiência dos meus usuários</span><span class="sxs-lookup"><span data-stu-id="ea467-125">Plan my users' experience</span></span> <br> <span data-ttu-id="ea467-126">Documente o meu planejamento de sucesso</span><span class="sxs-lookup"><span data-stu-id="ea467-126">Document my success plan</span></span>    | <span data-ttu-id="ea467-127">Preparar o meu serviço</span><span class="sxs-lookup"><span data-stu-id="ea467-127">Prepare my service</span></span> <br> <span data-ttu-id="ea467-128">Preparar os meus usuários</span><span class="sxs-lookup"><span data-stu-id="ea467-128">Prepare my users</span></span> <br> <span data-ttu-id="ea467-129">Implantar o meu serviço</span><span class="sxs-lookup"><span data-stu-id="ea467-129">Deploy my service</span></span>  <br> <br> <br> <br>     | <span data-ttu-id="ea467-130">Operar o meu serviço</span><span class="sxs-lookup"><span data-stu-id="ea467-130">Operate my service</span></span> <br> <span data-ttu-id="ea467-131">Aprimorar meu serviço</span><span class="sxs-lookup"><span data-stu-id="ea467-131">Enhance my service</span></span> <br> <br> <br> <br> <br>      |

<span data-ttu-id="ea467-132">O conteúdo é apresentado na maneira ordenada e foi projetado para orientá-lo por meio de uma jornada de implantação de ponta a ponta do início ao fim.</span><span class="sxs-lookup"><span data-stu-id="ea467-132">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="ea467-133">Se você estiver implantando já ativamente, ainda recomendamos que você para referenciar as áreas de conteúdo aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="ea467-133">If you're already actively deploying, we still encourage you to reference the applicable content areas.</span></span>



> [!TIP]
> <span data-ttu-id="ea467-134">Neste guia prático, estamos fornecendo saídas de exemplo para cada atividade e discussão principal.</span><span class="sxs-lookup"><span data-stu-id="ea467-134">In this practical guidance, we're providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="ea467-135">Os exemplos neste documento são colocados dentro de textos explicativos de dica, e eles servem como um modelo que pode ser reutilizado.</span><span class="sxs-lookup"><span data-stu-id="ea467-135">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="ea467-136">Você verá “TBA” (a ser adicionado) para informações que você precisa inserir como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ea467-136">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>