---
title: Estudo de caso da Contoso Voice Teams
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
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785942"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="f1a35-103">Estudo de caso da Contoso: plano de atualização do teams</span><span class="sxs-lookup"><span data-stu-id="f1a35-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="f1a35-104">Na decisão de migrar do Skype for Business para o Teams, a contoso queria oferecer uma experiência de transição fácil para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="f1a35-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="f1a35-105">Em vez de alternar entre todas as equipes ao mesmo tempo, elas decidiram configurar a conectividade híbrida e usar o método de recursos sobrepostos para mover usuários para o Teams.</span><span class="sxs-lookup"><span data-stu-id="f1a35-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="f1a35-106">Isso permitia aos usuários do Teams e do Skype for Business no local para compartilhar a presença e se comunicar.</span><span class="sxs-lookup"><span data-stu-id="f1a35-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="f1a35-107">Conforme os usuários digitam o piloto do sistema telefônico, eles foram movidos para o modo somente para equipes.</span><span class="sxs-lookup"><span data-stu-id="f1a35-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="f1a35-108">Para entender os conceitos fundamentais sobre a atualização, os métodos e os modos, a contoso leu os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="f1a35-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="f1a35-109">Introdução à atualização para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1a35-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="f1a35-110">Atualização do Skype for Business para o Teams</span><span class="sxs-lookup"><span data-stu-id="f1a35-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="f1a35-111">Orientação de migração e interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="f1a35-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="f1a35-112">A contoso também participou da sessão do Ignite 2019 [que está criando seu caminho do Skype for Business para o Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="f1a35-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="f1a35-113">A contoso aprendeu sobre:</span><span class="sxs-lookup"><span data-stu-id="f1a35-113">Contoso learned about:</span></span>

- <span data-ttu-id="f1a35-114">Conceitos fundamentais, como interoperabilidade, agrupamento e comportamento de atualização</span><span class="sxs-lookup"><span data-stu-id="f1a35-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="f1a35-115">Modos de coexistência e gerenciamento baseados no TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f1a35-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="f1a35-116">Experiência do usuário final para:</span><span class="sxs-lookup"><span data-stu-id="f1a35-116">End user experience for:</span></span> 

  - <span data-ttu-id="f1a35-117">Chat e chamadas</span><span class="sxs-lookup"><span data-stu-id="f1a35-117">Chat and Calling</span></span> 

  - <span data-ttu-id="f1a35-118">Agendamento de reunião</span><span class="sxs-lookup"><span data-stu-id="f1a35-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="f1a35-119">Disponibilidade da funcionalidade de colaboração em clientes do teams</span><span class="sxs-lookup"><span data-stu-id="f1a35-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="f1a35-120">Para planejar e configurar a conectividade híbrida, o primeiro passo para mover o ambiente local para a nuvem, a contoso leu o plano de leitura [híbrido](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) e [Configurar a conectividade híbrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) para compreender como:</span><span class="sxs-lookup"><span data-stu-id="f1a35-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="f1a35-121">Configurar o serviço de ambiente local para federação com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="f1a35-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="f1a35-122">Configurar o ambiente local para confiar no Office 365 e habilitar o espaço de endereço SIP compartilhado com o Office 365</span><span class="sxs-lookup"><span data-stu-id="f1a35-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="f1a35-123">Habilite o espaço de endereço SIP compartilhado em seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f1a35-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="f1a35-124">Use o modo de ilhas durante o piloto técnico.</span><span class="sxs-lookup"><span data-stu-id="f1a35-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="f1a35-125">Alternar usuários para o modo TeamsOnly quando o usuário estiver habilitado para o sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="f1a35-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="f1a35-126">O modo TeamsOnly é necessário para o plano de chamadas e o roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="f1a35-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
