---
title: Implantação do Cloud Voice
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/13/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Orientações práticas para a implantação dos recursos de Cloud Voice no Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45528d71dc04b96d77b454d5db402648779c1ac9
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2018
---
#<a name="cloud-voice-deployment"></a><span data-ttu-id="d400c-103">Implantação do Cloud Voice</span><span class="sxs-lookup"><span data-stu-id="d400c-103">Cloud voice deployment</span></span>

<span data-ttu-id="d400c-104">O Microsoft Teams, o centro de trabalho em equipe e comunicação do Office 365, agora oferece funcionalidades de Audioconferência e Sistema de Telefonia com Planos de Chamadas para atender a requisitos comerciais adicionais, ampliando a experiência de reuniões e chamadas do Microsoft Teams para incluir participantes externos conectados pela da Rede Telefônica Pública Comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="d400c-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the Public Switched Telephone Network (PSTN).</span></span>
 
<span data-ttu-id="d400c-105">Esta página será atualizada conforme outros recursos do Cloud Voice do Microsoft Teams forem lançados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="d400c-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>


##<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="d400c-106">Orientações práticas de Audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d400c-106">Practical guidance for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="d400c-107">A Audioconferência do Office 365  permite que os participantes ingressem em reuniões do Microsoft Teams usando qualquer telefone.</span><span class="sxs-lookup"><span data-stu-id="d400c-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="d400c-108">Eis o que você obtém com a [Audioconferência](https://go.microsoft.com/fwlink/?linkid=858992) no Office 365.</span><span class="sxs-lookup"><span data-stu-id="d400c-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

<span data-ttu-id="d400c-109">Estas orientações práticas o direcionam pela estrutura da jornada do cliente do Office 365 FastTrack e suas três fases, Concepção, Integração e Geração de valor, para ajudar no planejamento, na entrega e na operação de uma implementação da Audioconferência para obter ótimos resultados comerciais.</span><span class="sxs-lookup"><span data-stu-id="d400c-109">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases, Envision, Onboard, and Drive Value, to help you plan, deliver, and operate an Audio Conferencing implementation towards succesful business outcomes.</span></span>

> [!TIP]
> <span data-ttu-id="d400c-110">Nessas orientações práticas, fornecemos exemplos de resultados de cada atividade e discussão importante.</span><span class="sxs-lookup"><span data-stu-id="d400c-110">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="d400c-111">Os exemplos contidos neste documento estão incluídos nos balões de DICAS e servem como um modelo que você pode reutilizar.</span><span class="sxs-lookup"><span data-stu-id="d400c-111">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="d400c-112">Você verá “TBA” (a ser adicionado) para informações que você precisa inserir como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="d400c-112">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

##<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="d400c-113">Orientações práticas para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d400c-113">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="d400c-114">O Sistema de Telefonia é um recurso do Office 365 que permite gerenciar o encaminhamento de chamadas, políticas e o provisionamento de usuários.</span><span class="sxs-lookup"><span data-stu-id="d400c-114">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="d400c-115">Isso inclui o sistema de gerenciamento de chamadas telefônicas, o encaminhamento e o controle de chamadas.</span><span class="sxs-lookup"><span data-stu-id="d400c-115">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="d400c-116">Os Planos de Chamadas do Office 365 são um serviço complementar ao recurso Sistema de Telefonia, fornecido pelo Microsoft Teams e pelo Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="d400c-116">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="d400c-117">Os Planos de Chamadas fornecem às pessoas de sua empresa um número de telefone principal e permite que façam e recebam chamadas telefônicas fora da organização, pela PSTN (Rede Telefônica Pública Comutada).</span><span class="sxs-lookup"><span data-stu-id="d400c-117">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="d400c-118">Para saber mais, leia [Isto é o que você obtém com o Sistema de Telefonia no Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) e [O que são os Planos de Chamadas no Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span><span class="sxs-lookup"><span data-stu-id="d400c-118">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>

<span data-ttu-id="d400c-119">Estas orientações práticas o direcionam pela estrutura da jornada do cliente do Office 365 FastTrack e suas três fases, Concepção, Integração e Geração de valor, para ajudar no planejamento, na entrega e na operação de uma implementação bem-sucedida do Sistema de Telefonia com Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="d400c-119">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases - Envision, Onboard, and Drive Value - to help you plan, deliver, and operate a successful Phone System with Calling Plans implementation.</span></span>

> [!TIP]
> <span data-ttu-id="d400c-120">Nessas orientações práticas, fornecemos exemplos de resultados de cada atividade e discussão importante.</span><span class="sxs-lookup"><span data-stu-id="d400c-120">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="d400c-121">Os exemplos contidos neste documento estão incluídos nos balões de DICAS e servem como um modelo que você pode reutilizar.</span><span class="sxs-lookup"><span data-stu-id="d400c-121">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="d400c-122">Você verá “TBA” (a ser adicionado) para informações que você precisa inserir como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="d400c-122">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>