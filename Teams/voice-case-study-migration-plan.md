---
title: Estudo de caso de voz do Teams Contoso
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
description: Estudo de caso de voz do Teams para corporação multi-nacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93f6d0877537a740dc867b44c3c4deb9bebb8441
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421286"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="4d1c6-103">Estudo de caso contoso: Plano de atualização do Teams</span><span class="sxs-lookup"><span data-stu-id="4d1c6-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="4d1c6-104">Na decisão de migrar do Skype for Business para o Teams, a Contoso quis oferecer uma experiência de transição fácil para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="4d1c6-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="4d1c6-105">Em vez de alternar todos para o Teams ao mesmo tempo, eles decidiram configurar a conectividade híbrida e usar o método de recursos sobrepostos para mover os usuários para o Teams.</span><span class="sxs-lookup"><span data-stu-id="4d1c6-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="4d1c6-106">Isso permitia que os usuários do Teams e do Skype for Business locais compartilhavam presença e se comunicavam.</span><span class="sxs-lookup"><span data-stu-id="4d1c6-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="4d1c6-107">À medida que os usuários entraram no piloto do Sistema de Telefonia, eles foram movidos para o modo Somente do Teams.</span><span class="sxs-lookup"><span data-stu-id="4d1c6-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="4d1c6-108">Para entender os conceitos fundamentais sobre atualização, métodos e modos, a Contoso leu os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="4d1c6-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="4d1c6-109">Introdução à atualização para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d1c6-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="4d1c6-110">Estratégias de atualização para administradores de IT</span><span class="sxs-lookup"><span data-stu-id="4d1c6-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- [<span data-ttu-id="4d1c6-111">Diretrizes de migração e interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="4d1c6-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="4d1c6-112">A Contoso também participou da sessão Ignite 2019 Projetando seu caminho do [Skype for Business para o Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="4d1c6-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="4d1c6-113">Contoso aprendeu sobre:</span><span class="sxs-lookup"><span data-stu-id="4d1c6-113">Contoso learned about:</span></span>

- <span data-ttu-id="4d1c6-114">Conceitos fundamentais, como interoperabilidade, federação e comportamento de atualização</span><span class="sxs-lookup"><span data-stu-id="4d1c6-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="4d1c6-115">Modos de coexistência e gerenciamento com base no TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="4d1c6-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="4d1c6-116">Experiência do usuário final para:</span><span class="sxs-lookup"><span data-stu-id="4d1c6-116">End user experience for:</span></span> 

  - <span data-ttu-id="4d1c6-117">Chat e Chamada</span><span class="sxs-lookup"><span data-stu-id="4d1c6-117">Chat and Calling</span></span> 

  - <span data-ttu-id="4d1c6-118">Agendamento de reuniões</span><span class="sxs-lookup"><span data-stu-id="4d1c6-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="4d1c6-119">Disponibilidade da funcionalidade de colaboração em clientes do Teams</span><span class="sxs-lookup"><span data-stu-id="4d1c6-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="4d1c6-120">Para planejar e configurar a conectividade híbrida, a primeira etapa para [](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) mover seu ambiente local para a nuvem, a Contoso leu Planejar conectividade híbrida e [Configurar](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) conectividade híbrida para entender como:</span><span class="sxs-lookup"><span data-stu-id="4d1c6-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="4d1c6-121">Configure seu serviço de ambiente local para federar com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d1c6-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="4d1c6-122">Configurar seu ambiente local para confiar no Office 365 e habilitar o espaço de endereço SIP compartilhado com o Office 365</span><span class="sxs-lookup"><span data-stu-id="4d1c6-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="4d1c6-123">Habilita o espaço de endereço SIP compartilhado em seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d1c6-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="4d1c6-124">Use o modo Ilhas durante o piloto técnico.</span><span class="sxs-lookup"><span data-stu-id="4d1c6-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="4d1c6-125">Alternar usuários para o modo TeamsOnly quando o usuário for habilitado para o Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="4d1c6-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="4d1c6-126">O modo TeamsOnly é necessário para Plano de Chamadas e Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="4d1c6-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
