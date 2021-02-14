---
title: Definir seus requisitos para chamadas de emergência no Skype for Business Server
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Resume as etapas necessárias para habilizar o E9-1-1 no Skype for Business Server Enterprise Voice, dependendo se você tem um provedor de serviços E9-1-1 de tronco SIP ou um gateway ELIN.
ms.openlocfilehash: 8efd38657a80bee1ecd979e8730feacfb980053e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825811"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="4d3c1-103">Definir seus requisitos para chamadas de emergência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="4d3c1-104">Resume as etapas necessárias para habilizar o E9-1-1 no Skype for Business Server Enterprise Voice, dependendo se você tem um provedor de serviços E9-1-1 de tronco SIP ou um gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="4d3c1-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="4d3c1-105">Antes de começar uma implantação do Skype for Business Server E9-1-1, primeiro você deve ser capaz de responder às perguntas detalhadas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="4d3c1-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="4d3c1-106">O planejamento necessário dependerá do tipo de solução E9-1-1 que você optar por implantar: um provedor de serviços E9-1-1 de tronco SIP ou um gateway ELIN (número de identificação de local de emergência).</span><span class="sxs-lookup"><span data-stu-id="4d3c1-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="4d3c1-107">A tabela a seguir identifica as seções nesta plano de trabalho de planejamento que você precisará revisar para cada uma dessas soluções.</span><span class="sxs-lookup"><span data-stu-id="4d3c1-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="4d3c1-108">**Planejando as etapas por tipo de solução E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="4d3c1-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="4d3c1-109">**Provedor de serviços de tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="4d3c1-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="4d3c1-110">**Gateway ELIN**</span><span class="sxs-lookup"><span data-stu-id="4d3c1-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4d3c1-111">Definir o escopo da implantação do E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="4d3c1-112">Definir o escopo da implantação do E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="4d3c1-113">Definir os elementos de rede usados para determinar a localização no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="4d3c1-114">Definir os elementos de rede usados para determinar a localização no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="4d3c1-115">Habilitar usuários para E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="4d3c1-116">Habilitar usuários para E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="4d3c1-117">Gerenciar locais para provedores de serviços de tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="4d3c1-118">Gerenciar locais para gateways ELIN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="4d3c1-119">Definir a experiência do usuário para aquisição manual de um local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="4d3c1-120">Definir a experiência do usuário para aquisição manual de um local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="4d3c1-121">Projetar o tronco SIP para E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="4d3c1-122">Incluir a central de segurança no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="4d3c1-123">Incluir a central de segurança no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="4d3c1-124">Planejar políticas de local para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="4d3c1-125">Escolher um provedor de serviços E9-1-1 para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="4d3c1-126">Atribuir escopo de política de local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="4d3c1-127">Planejar políticas de local para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="4d3c1-128">Atribuir escopo de política de local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d3c1-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

