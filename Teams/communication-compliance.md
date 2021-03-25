---
title: Conformidade de comunicação com o Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprender sobre conformidade de comunicação, parte do conjunto de soluções de risco insider, na perspectiva do Microsoft Teams (isso faz parte da funcionalidade de conformidade de comunicação do M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf032669edc7255571e2501774ac0d0ee0df47d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121529"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="af1d5-103">Conformidade de comunicação com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af1d5-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="af1d5-104">A conformidade de comunicação é uma solução de risco interna no Microsoft 365 que ajuda a minimizar os riscos de comunicação, ajudando você a detectar, capturar e agir em mensagens inadequadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="af1d5-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="af1d5-105">Para o Microsoft Teams, a conformidade de comunicação ajuda a identificar os seguintes tipos [de](/microsoft-365/compliance/communication-compliance-feature-reference) conteúdo inadequado nos canais do Teams ou em chats de grupo e 1:1:</span><span class="sxs-lookup"><span data-stu-id="af1d5-105">For Microsoft Teams, communication compliance helps identify the [following types](/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="af1d5-106">Idioma ofensivo, profano e assediante</span><span class="sxs-lookup"><span data-stu-id="af1d5-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="af1d5-107">Imagens de adulto, racy e gory</span><span class="sxs-lookup"><span data-stu-id="af1d5-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="af1d5-108">Compartilhamento de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="af1d5-108">Sharing of sensitive information</span></span>

<span data-ttu-id="af1d5-109">Para obter mais informações sobre a conformidade de comunicação e como configurar políticas para sua organização, consulte [Conformidade de comunicação no Microsoft 365](/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="af1d5-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="af1d5-110">Como usar a conformidade de comunicação no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af1d5-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="af1d5-111">A conformidade de comunicação e o Microsoft Teams são fortemente integrados e podem ajudar a minimizar os riscos de comunicação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="af1d5-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="af1d5-112">Depois de configurar suas primeiras políticas de conformidade de comunicação, você poderá gerenciar ativamente mensagens e conteúdo inadequados do Microsoft Teams que são sinalizados automaticamente em alertas.</span><span class="sxs-lookup"><span data-stu-id="af1d5-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="af1d5-113">Introdução</span><span class="sxs-lookup"><span data-stu-id="af1d5-113">Getting started</span></span>

<span data-ttu-id="af1d5-114">Começar com a conformidade de comunicação [](/microsoft-365/compliance/communication-compliance-plan) no Microsoft Teams começa com o planejamento e a criação de políticas pré-definidas ou personalizadas para identificar atividades de usuário inadequadas em canais do Teams ou em 1:1 e grupos.</span><span class="sxs-lookup"><span data-stu-id="af1d5-114">Getting started with communication compliance in Microsoft Teams begins with [planning](/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="af1d5-115">Lembre-se de que você precisará [configurar](/microsoft-365/compliance/communication-compliance-configure) algumas permissões e pré-requisitos básicos como parte do processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="af1d5-115">Keep in mind that you'll need to [configure](/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="af1d5-116">Os administradores do Teams podem configurar políticas de conformidade de comunicação nos seguintes níveis:</span><span class="sxs-lookup"><span data-stu-id="af1d5-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="af1d5-117">**Nível do** usuário: as políticas nesse nível se aplicam a um usuário individual do Teams ou podem ser aplicadas a todos os usuários do Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="af1d5-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="af1d5-118">Essas políticas abrangem mensagens que esses usuários podem enviar em chats de grupo ou 1:1.</span><span class="sxs-lookup"><span data-stu-id="af1d5-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="af1d5-119">As comunicações de chat para os usuários são monitoradas automaticamente em todos os Microsoft Teams onde os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="af1d5-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="af1d5-120">**Nível do Teams**: As políticas nesse nível se aplicam a um canal da Equipe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="af1d5-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="af1d5-121">Essas políticas abrangem mensagens enviadas apenas no canal do Teams.</span><span class="sxs-lookup"><span data-stu-id="af1d5-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="af1d5-122">Agir em mensagens inadequadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af1d5-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="af1d5-123">Depois de configurar suas políticas e receber alertas de conformidade de comunicação para mensagens do Microsoft Teams, é hora de os revisadores de conformidade em sua organização tomarem medidas nessas mensagens.</span><span class="sxs-lookup"><span data-stu-id="af1d5-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="af1d5-124">Os revisadores podem ajudar a proteger sua organização, revisando alertas de conformidade de comunicação e removendo mensagens sinalizadas da exibição no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="af1d5-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Remover uma mensagem no Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="af1d5-126">Mensagens e conteúdo removidos são substituídos por notificações para os visualizadores explicando que a mensagem ou conteúdo foi removido e qual política é aplicável à remoção.</span><span class="sxs-lookup"><span data-stu-id="af1d5-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="af1d5-127">O remetente da mensagem ou conteúdo removido também é notificado do status de remoção e fornecido com o conteúdo da mensagem original para contexto relacionado à sua remoção.</span><span class="sxs-lookup"><span data-stu-id="af1d5-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="af1d5-128">O remetente também pode exibir a condição de política específica que se aplica à remoção da mensagem.</span><span class="sxs-lookup"><span data-stu-id="af1d5-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="af1d5-129">Exemplo de dica de política vista pelo remetente:</span><span class="sxs-lookup"><span data-stu-id="af1d5-129">Example of policy tip seen by sender:</span></span>

![Dica de política para remetente](./media/communication-compliance-warning-1.png)

<span data-ttu-id="af1d5-131">Exemplo de notificação de condição de política vista pelo remetente:</span><span class="sxs-lookup"><span data-stu-id="af1d5-131">Example of policy condition notification seen by the sender:</span></span>

![Informações de condição de política para remetente](./media/communication-compliance-warning-2.png)

<span data-ttu-id="af1d5-133">Exemplo de dica de política vista pelo destinatário:</span><span class="sxs-lookup"><span data-stu-id="af1d5-133">Example of policy tip seen by recipient:</span></span>

![Dica de política para destinatário](./media/communication-compliance-warning-3.png)