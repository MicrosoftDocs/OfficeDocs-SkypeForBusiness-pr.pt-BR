---
title: Definir seus requisitos para chamadas de emergência Skype para Business Server
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Resume as etapas necessárias para habilitar o E9-1-1 em Skype para Business Server Enterprise Voice, dependendo se você tem um provedor de serviços de E9-1-1 de tronco SIP ou um gateway ELIN.
ms.openlocfilehash: 3ddcb25b86689f29831872f24a1893d5ff2f1f4c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885358"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="8d721-103">Definir seus requisitos para chamadas de emergência Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="8d721-104">Resume as etapas necessárias para habilitar o E9-1-1 em Skype para Business Server Enterprise Voice, dependendo se você tem um provedor de serviços de E9-1-1 de tronco SIP ou um gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="8d721-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="8d721-105">Antes de começar uma Skype para implantação de servidor de negócios E9-1-1, você deve primeiro ser capazes de responder as perguntas detalhadas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="8d721-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="8d721-106">O planejamento necessário dependerá do tipo de solução E9-1-1 que você optar por implantar: um provedor de serviços E9-1-1 de tronco SIP ou um gateway ELIN (número de identificação de local de emergência).</span><span class="sxs-lookup"><span data-stu-id="8d721-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="8d721-107">A tabela a seguir identifica as seções nesta pasta de trabalho de planejamento que você precisará analisar para cada uma dessas soluções.</span><span class="sxs-lookup"><span data-stu-id="8d721-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="8d721-108">**Planejando as etapas por tipo de solução E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="8d721-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="8d721-109">**Provedor de serviços de tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="8d721-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="8d721-110">**Gateway ELIN**</span><span class="sxs-lookup"><span data-stu-id="8d721-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8d721-111">Definir o escopo da implantação do E9-1-1 Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="8d721-112">Definir o escopo da implantação do E9-1-1 Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="8d721-113">Definir os elementos de rede usados para determinar o local em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="8d721-114">Definir os elementos de rede usados para determinar o local em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="8d721-115">Habilitar usuários para E9-1-1 em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="8d721-116">Habilitar usuários para E9-1-1 em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="8d721-117">Gerenciar locais para provedores de serviços de tronco SIP no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="8d721-118">Gerenciar locais para gateways ELIN no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="8d721-119">Definir a experiência do usuário para adquirir manualmente um local no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="8d721-120">Definir a experiência do usuário para adquirir manualmente um local no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="8d721-121">Projetar o tronco SIP para E9-1-1 em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="8d721-122">Incluir o suporte de segurança em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="8d721-123">Incluir o suporte de segurança em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="8d721-124">Planejar políticas de local Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="8d721-125">Escolher um fornecedor de serviço E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="8d721-126">Atribuir o escopo da política de local no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="8d721-127">Planejar políticas de local Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="8d721-128">Atribuir o escopo da política de local no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8d721-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

