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
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785942"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="83639-103">Estudo de caso da Contoso: plano de atualização do Teams</span><span class="sxs-lookup"><span data-stu-id="83639-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="83639-104">Na decisão de migrar do Skype for Business para o Teams, a Contoso queria fornecer uma experiência de transição fácil para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="83639-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="83639-105">Em vez de mudar todos para o Teams ao mesmo tempo, eles decidiram configurar a conectividade híbrida e usar o método de sobreposição de recursos para mover os usuários para o Teams.</span><span class="sxs-lookup"><span data-stu-id="83639-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="83639-106">Isso permitia que os usuários do Teams e do Skype for Business locais compartilhavam presença e se comunicam.</span><span class="sxs-lookup"><span data-stu-id="83639-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="83639-107">Conforme os usuários entraram no piloto do Sistema telefônico, eles foram movidos para o modo Somente equipes.</span><span class="sxs-lookup"><span data-stu-id="83639-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="83639-108">Para entender conceitos fundamentais sobre atualização, métodos e modos, a Contoso leu os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="83639-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="83639-109">Introdução à atualização para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83639-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="83639-110">Atualização do Skype for Business para o Teams</span><span class="sxs-lookup"><span data-stu-id="83639-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="83639-111">Diretrizes de migração e interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="83639-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="83639-112">A Contoso também participou da sessão Ignite 2019, projetando seu caminho do [Skype for Business para o Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="83639-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="83639-113">A Contoso aprendeu sobre:</span><span class="sxs-lookup"><span data-stu-id="83639-113">Contoso learned about:</span></span>

- <span data-ttu-id="83639-114">Conceitos fundamentais, como interoperabilidade, federação e comportamento de atualização</span><span class="sxs-lookup"><span data-stu-id="83639-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="83639-115">Modos de coexistência e gerenciamento com base no TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="83639-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="83639-116">Experiência do usuário final para:</span><span class="sxs-lookup"><span data-stu-id="83639-116">End user experience for:</span></span> 

  - <span data-ttu-id="83639-117">Chat e Chamada</span><span class="sxs-lookup"><span data-stu-id="83639-117">Chat and Calling</span></span> 

  - <span data-ttu-id="83639-118">Agendamento de reunião</span><span class="sxs-lookup"><span data-stu-id="83639-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="83639-119">Disponibilidade da funcionalidade de colaboração em clientes do Teams</span><span class="sxs-lookup"><span data-stu-id="83639-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="83639-120">Para planejar e configurar a conectividade híbrida, o primeiro passo para [](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) mover seu ambiente [](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) local para a nuvem, a Contoso leu Plano de conectividade híbrida e Configurar a conectividade híbrida para entender como:</span><span class="sxs-lookup"><span data-stu-id="83639-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="83639-121">Configure o serviço de ambiente local para se federar com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="83639-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="83639-122">Configurar o ambiente local para confiar no Office 365 e habilitar o espaço de endereço SIP compartilhado com o Office 365</span><span class="sxs-lookup"><span data-stu-id="83639-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="83639-123">Habilitar o espaço de endereço SIP compartilhado no locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="83639-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="83639-124">Use o modo Ilhas durante o piloto técnico.</span><span class="sxs-lookup"><span data-stu-id="83639-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="83639-125">Alternar usuários para o modo TeamsOnly assim que o usuário está habilitado para o Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="83639-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="83639-126">O modo TeamsOnly é necessário para o Plano de Chamada e o Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="83639-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
