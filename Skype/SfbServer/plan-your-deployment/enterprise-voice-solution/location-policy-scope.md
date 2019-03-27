---
title: Atribuir o escopo da política de local no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planejando as políticas de local para uma implantação do E9-1-1 em Skype Business Server Enterprise Voice.
ms.openlocfilehash: 0c39d0f464b7cde9521dbb69043411b964f74858
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892214"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="58948-103">Atribuir o escopo da política de local no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="58948-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="58948-104">Planejando as políticas de local para uma implantação do E9-1-1 em Skype Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="58948-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="58948-105">Como com outra Skype para políticas de Business Server, as políticas de local podem ser atribuídas nos vários níveis de escopo: global, site e usuário.</span><span class="sxs-lookup"><span data-stu-id="58948-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="58948-106">No entanto, o escopo de políticas de nível de usuário local se comporta um bit de forma diferente com outro Skype para políticas de Business Server.</span><span class="sxs-lookup"><span data-stu-id="58948-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="58948-107">Não apenas políticas de local por usuário podem ser aplicadas a objetos de ponto de extremidade (por exemplo, usuários e objetos de contato de telefone de área comum), eles também podem ser aplicados a Skype para sites de rede do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="58948-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="58948-108">Os sites de rede são agrupamentos de subredes de cliente associadas com um local geográfico (mas não necessariamente deve ser todas as subredes em um site central ou site de filial).</span><span class="sxs-lookup"><span data-stu-id="58948-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="58948-109">Qualquer cliente conectado às subredes de um site de rede obtém automaticamente a política de local atribuída a este site de rede.</span><span class="sxs-lookup"><span data-stu-id="58948-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="58948-110">Em casos onde uma política de local a nível de usuário é atribuída ao usuário e a um site de rede, a política de local baseada em site de rede substitui qualquer configuração de política por usuário.</span><span class="sxs-lookup"><span data-stu-id="58948-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="58948-111">Cada local de rede possui uma política de rede atribuída e cada política possuirá diferentes valores de Usos de PSTN, URIs de notificação e URIs de conferência atribuídos.</span><span class="sxs-lookup"><span data-stu-id="58948-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58948-112">O motivo para esta política especial se comportar desta forma é porque quando um usuário hospedado em um pool em um local de escritório visita outro local e precisa fazer uma chamada de emergência, as configurações de roteamento de chamada E9-1-1 adequadas para este local de rede serão aplicadas não importando a qual pool ou local o usuário está atribuído.</span><span class="sxs-lookup"><span data-stu-id="58948-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

