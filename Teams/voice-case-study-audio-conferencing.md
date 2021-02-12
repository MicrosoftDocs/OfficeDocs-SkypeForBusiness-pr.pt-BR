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
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785948"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="2ebe3-103">Estudo de caso da Contoso: Audioconferência</span><span class="sxs-lookup"><span data-stu-id="2ebe3-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="2ebe3-104">Para obter uma compreensão do que é a audioconferência, o custo, a disponibilidade e a forma como ela funciona, a Contoso reviu a Audioconferência no &mdash; &mdash; Office [365.](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="2ebe3-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="2ebe3-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="2ebe3-105">Overview</span></span> 

<span data-ttu-id="2ebe3-106">Para audioconferência, a Contoso usava números de telefone conhecidos dentro da organização e externamente.</span><span class="sxs-lookup"><span data-stu-id="2ebe3-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="2ebe3-107">Como a Contoso queria manter esses números sempre que possível, eles revisaram as informações sobre a atribuição de números de telefone dedicados e compartilhados à ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="2ebe3-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="2ebe3-108">Com base na pesquisa, a Contoso toma as seguintes decisões:</span><span class="sxs-lookup"><span data-stu-id="2ebe3-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="2ebe3-109">Somente um segmento da população que hospeda regularmente chamadas de audioconferência receberia licenças de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="2ebe3-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="2ebe3-110">A Contoso usaria números de telefone dedicados e portaria seus números existentes para uso com a Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="2ebe3-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="2ebe3-111">Como os usuários da Contoso estavam usando o Skype for Business e as caixas de correio de todos os usuários residem online, muitos usuários têm reuniões existentes agendadas.</span><span class="sxs-lookup"><span data-stu-id="2ebe3-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="2ebe3-112">A Contoso leu Usando o [MMS (Meeting Migration Service)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) para saber que as reuniões existentes são atualizadas automaticamente para a Contoso quando eles alteram o usuário final para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2ebe3-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="2ebe3-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="2ebe3-113">Configuration</span></span>

<span data-ttu-id="2ebe3-114">Os números de telefone associados à audioconferência são chamados de números de serviço no Sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="2ebe3-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="2ebe3-115">Para locais que usam Planos de Chamada, para portabilidade de seus números de telefone existentes de sua operadora de telefonia para o Office 365, a Contoso seguiu as etapas em Obter números de telefone [de serviço.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="2ebe3-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="2ebe3-116">Para atribuir a licença de Audioconferência ao usuário final no piloto técnico, o administrador da Contoso seguiu as etapas em Gerenciar as configurações de [Audioconferência da sua organização.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="2ebe3-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="2ebe3-117">Para o piloto comercial e a migração, a Contoso usou licenciamento baseado em grupo seguindo as etapas em Atribuir licenças aos usuários por associação ao grupo no [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="2ebe3-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 