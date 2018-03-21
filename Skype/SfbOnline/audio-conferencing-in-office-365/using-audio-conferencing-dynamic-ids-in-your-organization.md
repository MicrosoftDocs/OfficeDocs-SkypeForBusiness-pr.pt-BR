---
title: "Usar as IDs de dinâmica de conferência de áudio em sua organização"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "O serviço de conferência de áudio está sendo atualizado para fornecer cada Skype para reunião Teams da Microsoft e de negócios com IDs de conferência diferentes. IDs de conferência dinâmicos são um avanço significativo sobre conferência estática IDs, porque eles fornecem:"
ms.openlocfilehash: c4158537f7c36299a82df92d3c6ced6cb6189315
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a><span data-ttu-id="ee555-104">Usar as IDs de dinâmica de conferência de áudio em sua organização</span><span class="sxs-lookup"><span data-stu-id="ee555-104">Using Audio Conferencing dynamic IDs in your organization</span></span>

<span data-ttu-id="ee555-105">O serviço de conferência de áudio está sendo atualizado para fornecer cada Skype para reunião Teams da Microsoft e de negócios com IDs de conferência diferentes.</span><span class="sxs-lookup"><span data-stu-id="ee555-105">The Audio Conferencing service is being updated to provide each Skype for Business and Microsoft Teams meeting with different conference IDs.</span></span> <span data-ttu-id="ee555-106">IDs de conferência dinâmicos são um avanço significativo sobre conferência estática IDs, porque eles fornecem:</span><span class="sxs-lookup"><span data-stu-id="ee555-106">Dynamic conference IDs are a significant improvement over static conference IDs, because they provide:</span></span>
  
- <span data-ttu-id="ee555-107">**Segurança avançada** A conferência IDs são exclusivos para cada Skype para reunião de negócios ou Teams da Microsoft e são gerados quando a reunião está sendo agendada.</span><span class="sxs-lookup"><span data-stu-id="ee555-107">**Enhanced security** The conference IDs are unique for each Skype for Business or Microsoft Teams meeting and are generated when the meeting is being scheduled.</span></span>
    
- <span data-ttu-id="ee555-108">**Uma melhor experiência nas reuniões de ponta a ponta** Nas reuniões de um único organizador são fornecidas informações específicas sobre a conferência discada que impede que os participantes por telefone de uma reunião sejam misturados a outros participantes da outra que está sendo agendada em horários próximos.</span><span class="sxs-lookup"><span data-stu-id="ee555-108">**A better experience for back-to-back and side-to-side meetings** Meetings for a single organizer are given specific dial-in information that prevents phone participants of one meeting from being mixed with participants of another one when they're scheduled next to each other.</span></span>
    
- <span data-ttu-id="ee555-109">**Uma transição perfeita** Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões já agendadas na organização com IDs de conferência estáticas continuarão funcionando.</span><span class="sxs-lookup"><span data-stu-id="ee555-109">**A seamless transition** When your organization is enabled for dynamic conference IDs, all the meetings that have been already scheduled in your organization with static conference IDs will continue to work.</span></span>
    
> [!TIP]
> <span data-ttu-id="ee555-110">IDs dinâmicas só estão disponíveis para usuários habilitados para * * conferência áudio * * e tem o Microsoft definido como seu provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="ee555-110">Dynamic IDs are only available to users who are enabled for ** Audio Conferencing** and have Microsoft set as their audio conferencing provider.</span></span> <span data-ttu-id="ee555-111">Você pode [Atribuir a Microsoft como um provedor de serviços de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md) para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="ee555-111">You can [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md) for your users.</span></span>
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a><span data-ttu-id="ee555-112">As alterações que os usuários na minha organização verá?</span><span class="sxs-lookup"><span data-stu-id="ee555-112">What changes will the users in my organization see?</span></span>

<span data-ttu-id="ee555-113">Depois de IDs de conferência dinâmico tiverem sido habilitados para sua organização, qualquer nova Skype para negócios ou Teams Microsoft da reunião que esteja agendado pelos usuários em sua organização que estão habilitados para conferência de áudio terá que serão diferentes dos IDs de conferência a ID de conferência estáticos que tinham antes.</span><span class="sxs-lookup"><span data-stu-id="ee555-113">After dynamic conference IDs have been enabled for your organization, any new Skype for Business or Microsoft Teams meeting that is scheduled by users in your organization who are enabled for Audio Conferencing will have conference IDs that will be different from the static conference ID they had before.</span></span> <span data-ttu-id="ee555-114">Organizadores que tivessem estática IDs de conferência antes precisam lembrar os usuários que participarem de suas reuniões que eles precisam usar uma nova ID de conferência no convite da reunião antes que eles poderão ingressá-lo agora.</span><span class="sxs-lookup"><span data-stu-id="ee555-114">Organizers who had static conference IDs before need to remind the users joining their meetings that they now need to use a new conference ID in the meeting's invite before they can join it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ee555-115">Reuniões que foram agendadas por um usuário com estáticas IDs de conferência antes que a organização foi habilitada para conferência dinâmica que IDs continuará a ter as IDs de conferência estático, para que eles vai continuar a agendar reuniões sem nenhum impacto.</span><span class="sxs-lookup"><span data-stu-id="ee555-115">Meetings that were scheduled by a user with static conference IDs before the organization was enabled for dynamic conference IDs will continue to have the static conference IDs, so they'll continue to schedule meetings without any impact.</span></span> 
  
<span data-ttu-id="ee555-116">Estes exemplos mostram a nova experiência para dois Skype para reuniões de negócios que foram organizadas pelo mesmo usuário, mas ambos agora terá duas IDs de conferência diferentes:</span><span class="sxs-lookup"><span data-stu-id="ee555-116">These examples show you the new experience for two Skype for Business meetings that have been organized by the same user but will both now have two different conference IDs:</span></span> 
  
 <span data-ttu-id="ee555-117">**Reunião nº 1** foi agendada das 9:00 às 10:00 AM sob a ID de conferência 93907123:</span><span class="sxs-lookup"><span data-stu-id="ee555-117">**Meeting #1** has been scheduled from 9:00 AM to 10:00 AM and it has 93907123 as its conference ID:</span></span>
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 <span data-ttu-id="ee555-119">**Reunião nº 2** foi agendada pelo mesmo usuários das 10:00 às 11:00 AM sob a ID de conferência 16353789:</span><span class="sxs-lookup"><span data-stu-id="ee555-119">**Meeting #2** has been scheduled by the same user from 10:00 AM to 11:00 AM and it has 16353789 as its conference ID:</span></span>
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a><span data-ttu-id="ee555-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ee555-121">Related topics</span></span>

- [<span data-ttu-id="ee555-122">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee555-122">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [<span data-ttu-id="ee555-123">Configurar conferência de áudio para o Skype for Business e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee555-123">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
    
- [<span data-ttu-id="ee555-124">Licenciamento de complementos do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee555-124">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
