---
title: Definir seus requisitos de chamadas de emergência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Resume as etapas necessárias para habilitar o E9-1-1 no Skype for Business Server Enterprise Voice, dependendo se você tiver um provedor de serviços de tronco SIP E9-1 ou um gateway ELIN.
ms.openlocfilehash: ffda7796390fea6c44d943770c9b4af6d299549a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803081"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="d3f93-103">Definir seus requisitos de chamadas de emergência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="d3f93-104">Resume as etapas necessárias para habilitar o E9-1-1 no Skype for Business Server Enterprise Voice, dependendo se você tiver um provedor de serviços de tronco SIP E9-1 ou um gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="d3f93-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="d3f93-105">Antes de começar uma implantação do Skype for Business Server E9-1-1, você deve primeiro poder responder às perguntas detalhadas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="d3f93-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="d3f93-106">O planejamento necessário dependerá do tipo de solução E9-1-1 que você optar por implantar: um provedor de serviços E9-1-1 de tronco SIP ou um gateway ELIN (número de identificação de local de emergência).</span><span class="sxs-lookup"><span data-stu-id="d3f93-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="d3f93-107">A tabela a seguir identifica as seções nesta pasta de trabalho de planejamento que você precisará examinar para cada uma dessas soluções.</span><span class="sxs-lookup"><span data-stu-id="d3f93-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="d3f93-108">**Planejando as etapas por tipo de solução E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="d3f93-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="d3f93-109">**Provedor de serviços de tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="d3f93-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="d3f93-110">**Gateway ELIN**</span><span class="sxs-lookup"><span data-stu-id="d3f93-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d3f93-111">Definir o escopo da implantação do E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="d3f93-112">Definir o escopo da implantação do E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="d3f93-113">Definir os elementos de rede usados para determinar o local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="d3f93-114">Definir os elementos de rede usados para determinar o local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="d3f93-115">Habilitar usuários para o E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="d3f93-116">Habilitar usuários para o E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="d3f93-117">Gerenciar locais para provedores de serviço de tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="d3f93-118">Gerenciar locais para gateways do ELIN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="d3f93-119">Definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="d3f93-120">Definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="d3f93-121">Crie o tronco SIP para E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="d3f93-122">Inclua a central de segurança no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="d3f93-123">Inclua a central de segurança no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="d3f93-124">Planejar políticas de localização para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="d3f93-125">Escolher um fornecedor de serviço E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="d3f93-126">Atribuir o escopo da política de localização no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="d3f93-127">Planejar políticas de localização para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="d3f93-128">Atribuir o escopo da política de localização no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3f93-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

