---
title: Fazer alterações nas configurações de Transmissão de Reunião do Skype para sua organização
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
description: Você pode habilitar a Transmissão de Reunião do Skype e fazer alterações nas configurações e políticas dessas reuniões.
ms.openlocfilehash: 75b1894f486d6448662c459b0d77d4f5d3057a2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106547"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="dcfd9-103">Fazer alterações nas configurações de Transmissão de Reunião do Skype para sua organização</span><span class="sxs-lookup"><span data-stu-id="dcfd9-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcfd9-104">O centro de administração do Microsoft Teams substituiu o Centro de administração do Skype for Business (portal herdado).</span><span class="sxs-lookup"><span data-stu-id="dcfd9-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="dcfd9-105">Todas as configurações para gerenciar o Skype for Business agora estão no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="dcfd9-106">Você deve ter a função de administrador do [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global ou administrador do Skype for Business para gerenciar recursos do Skype for Business no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="dcfd9-107">Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="dcfd9-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="dcfd9-108">Você pode habilitar a Transmissão de Reunião do Skype e fazer alterações nas configurações e políticas dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="dcfd9-109">**Habilitar Transmissão de Reunião do Skype** Habilita a Transmissão de Reunião do Skype.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="dcfd9-110">Depois de habilitar a Transmissão de Reunião do Skype, você precisará [configurar sua rede para Transmissão de Reunião do Skype.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="dcfd9-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="dcfd9-111">Faça esta etapa se quiser manter webinars e outras transmissões para pessoas fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="dcfd9-112">**Habilitar recursos de Visualização** de Transmissão de Reunião do Skype para minha organização Os programas de clientes do Skype for Business fornecem acesso antecipado a novos produtos e recursos.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="dcfd9-113">Isso oferece à sua organização uma prévia do que está por vir e a oportunidade de testar os novos recursos em seu próprio ambiente e fazer comentários antes de lançarmos as com builds do produto para o público em geral.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="dcfd9-114">Visualização do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="dcfd9-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="dcfd9-115">**Permitir que os organizadores agendem reuniões anônimas** Isso permite que os organizadores criem eventos de transmissão que permitem que qualquer pessoa de fora de sua organização participe sem um requisito para entrar.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="dcfd9-116">**Permitir que as reuniões de transmissão sejam gravadas** Isso permite que qualquer reunião que você tenha que ser gravada pelo apresentador ou organizador.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="dcfd9-117">**URL de suporte do Helpdesk para participantes** Insira um link para que os participantes da transmissão de reunião usem se eles precisam de ajuda para se conectar ou participar de uma reunião de transmissão.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="dcfd9-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="dcfd9-118">Related topics</span></span>

[<span data-ttu-id="dcfd9-119">Configurar a rede para a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="dcfd9-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
