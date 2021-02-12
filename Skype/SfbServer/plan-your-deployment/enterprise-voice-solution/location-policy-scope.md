---
title: Atribuir escopo de política de local no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planejamento de políticas de local para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825521"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="7548a-103">Atribuir escopo de política de local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7548a-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="7548a-104">Planejamento de políticas de local para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7548a-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7548a-105">Assim como com outras políticas do Skype for Business Server, as políticas de local podem ser atribuídas em vários níveis de escopo: global, site e usuário.</span><span class="sxs-lookup"><span data-stu-id="7548a-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="7548a-106">No entanto, o escopo das políticas de local no nível do usuário se comporta um pouco diferente de outras políticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7548a-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="7548a-107">Não só as políticas de local por usuário podem ser aplicadas a objetos de ponto de extremidade (como objetos de contato usuários e telefone de área comum), como também podem ser aplicadas aos sites de rede do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7548a-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="7548a-108">Os sites de rede são agrupamentos de sub-redes de clientes associados a uma localidade geográfica (mas podem não ser necessariamente todas as sub-redes em todo o site central ou site de filial).</span><span class="sxs-lookup"><span data-stu-id="7548a-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="7548a-109">Quaisquer clientes conectados às sub-redes em um site de rede automaticamente selecionam a política de local designada para o site de rede.</span><span class="sxs-lookup"><span data-stu-id="7548a-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="7548a-110">Nos casos em que uma política de local no nível do usuário é atribuída a um usuário e a um site de rede, a política de local baseada em site de rede substitui qualquer configuração de política por usuário.</span><span class="sxs-lookup"><span data-stu-id="7548a-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="7548a-111">Cada site de rede possui uma política de local atribuída a ele e cada política terá diferentes valores para Usos do PSTN, URIs de Notificação e URIs da Conferência atribuídos a ela.</span><span class="sxs-lookup"><span data-stu-id="7548a-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7548a-112">O motivo para esse comportamento especial de scoping de política é que, quando um usuário que está em um pool em um site do escritório visita outro site e precisa fazer uma chamada de emergência, as configurações de roteamento de chamada E9-1-1 apropriadas para esse local de rede serão aplicadas independentemente do pool ou site ao qual o usuário está atribuído.</span><span class="sxs-lookup"><span data-stu-id="7548a-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

