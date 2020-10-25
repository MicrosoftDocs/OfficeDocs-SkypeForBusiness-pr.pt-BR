---
title: Fazer alterações nas configurações de transmissão de reunião do Skype para sua organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- SMB
- ms.lync.lac.BroadcastMeetings
description: Você pode habilitar a transmissão de reunião do Skype e fazer alterações nas configurações e políticas dessas reuniões.
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753406"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="e8a08-103">Fazer alterações nas configurações de transmissão de reunião do Skype para sua organização</span><span class="sxs-lookup"><span data-stu-id="e8a08-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8a08-104">O centro de administração do Microsoft Teams substituiu o centro de administração do Skype for Business (Portal herdado).</span><span class="sxs-lookup"><span data-stu-id="e8a08-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="e8a08-105">Todas as configurações para gerenciar o Skype for Business agora estão no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="e8a08-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="e8a08-106">Você deve receber a função de administrador global do [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ou administrador do Skype for Business para gerenciar os recursos do Skype for Business no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="e8a08-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="e8a08-107">Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="e8a08-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="e8a08-108">Você pode habilitar a transmissão de reunião do Skype e fazer alterações nas configurações e políticas dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="e8a08-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="e8a08-109">**Habilitar a transmissão de reunião do Skype** Habilita a transmissão de reunião do Skype.</span><span class="sxs-lookup"><span data-stu-id="e8a08-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="e8a08-110">Depois de habilitar a transmissão de reunião do Skype, você precisa [configurar sua rede para a transmissão de reunião do Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="e8a08-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="e8a08-111">Siga este procedimento se quiser manter o webinars e outras difusões para pessoas de fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="e8a08-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="e8a08-112">**Habilitar os recursos de visualização da transmissão de reunião do Skype para minha organização** Os programas de cliente do Skype for Business fornecem acesso antecipado a novos produtos e recursos.</span><span class="sxs-lookup"><span data-stu-id="e8a08-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="e8a08-113">Isso dá à sua organização uma retomada do que está chegando e da oportunidade de testar os novos recursos em seu próprio ambiente e enviar comentários antes de lançarmos as compilações de produtos para o público em geral.</span><span class="sxs-lookup"><span data-stu-id="e8a08-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="e8a08-114">Visualização do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e8a08-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="e8a08-115">**Permitir que os organizadores agendem reuniões anônimas** Isso permite que os organizadores criem eventos de transmissão que permitem que qualquer pessoa fora de sua organização ingresse sem necessidade de entrar.</span><span class="sxs-lookup"><span data-stu-id="e8a08-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="e8a08-116">**Permitir que as reuniões de transmissão sejam gravadas** Isso permite que todas as reuniões que você precisa ser gravadas pelo apresentador ou organizador.</span><span class="sxs-lookup"><span data-stu-id="e8a08-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="e8a08-117">**URL de suporte da assistência técnica para participantes** Insira um link para os participantes de transmissão de reunião usarem se precisarem de ajuda para se conectar ou participar de uma reunião de transmissão.</span><span class="sxs-lookup"><span data-stu-id="e8a08-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e8a08-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e8a08-118">Related topics</span></span>

[<span data-ttu-id="e8a08-119">Configurar a rede para a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="e8a08-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
