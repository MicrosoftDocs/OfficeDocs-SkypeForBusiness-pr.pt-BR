---
title: Conformidade de comunicação com Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Learning sobre conformidade de comunicação, parte do conjunto de soluções de risco insider, Microsoft Teams perspectiva (isso faz parte da funcionalidade de conformidade de comunicação do M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5957e8900a9b3d9915a88e3ad8bf5e18c7a08b3
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126897"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="81266-103">Conformidade de comunicação com Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81266-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="81266-104">A conformidade de comunicação é uma solução de risco interna no Microsoft 365 que ajuda a minimizar os riscos de comunicação, ajudando você a detectar, capturar e agir em mensagens inadequadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="81266-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="81266-105">Para Microsoft Teams, a conformidade de [](/microsoft-365/compliance/communication-compliance-feature-reference) comunicação ajuda a identificar os seguintes tipos de conteúdo inadequado em canais Teams, canais Teams privados ou em chats em grupo e 1:1:</span><span class="sxs-lookup"><span data-stu-id="81266-105">For Microsoft Teams, communication compliance helps identify the [following types](/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels, Private Teams channels, or in 1:1 and group chats:</span></span>

- <span data-ttu-id="81266-106">Idioma ofensivo, profano e assediante</span><span class="sxs-lookup"><span data-stu-id="81266-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="81266-107">Imagens de adulto, racy e gory</span><span class="sxs-lookup"><span data-stu-id="81266-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="81266-108">Compartilhamento de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="81266-108">Sharing of sensitive information</span></span>

<span data-ttu-id="81266-109">Para obter mais informações sobre a conformidade de comunicação e como configurar políticas para sua organização, consulte Conformidade de comunicação [em Microsoft 365](/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="81266-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="81266-110">Como usar a conformidade de comunicação Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81266-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="81266-111">A conformidade e a Microsoft Teams de comunicação são fortemente integradas e podem ajudar a minimizar os riscos de comunicação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="81266-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="81266-112">Depois de configurar suas primeiras políticas de conformidade de comunicação, você poderá gerenciar ativamente mensagens inadequadas Microsoft Teams conteúdo e mensagens que são sinalizadas automaticamente em alertas.</span><span class="sxs-lookup"><span data-stu-id="81266-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="81266-113">Introdução</span><span class="sxs-lookup"><span data-stu-id="81266-113">Getting started</span></span>

<span data-ttu-id="81266-114">Começar com a conformidade de comunicação no [](/microsoft-365/compliance/communication-compliance-plan) Microsoft Teams começa com o planejamento e a criação de políticas pré-definidas ou personalizadas para identificar atividades de usuário inadequadas em canais Teams ou em 1:1 e grupos.</span><span class="sxs-lookup"><span data-stu-id="81266-114">Getting started with communication compliance in Microsoft Teams begins with [planning](/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="81266-115">Lembre-se de que você precisará [configurar](/microsoft-365/compliance/communication-compliance-configure) algumas permissões e pré-requisitos básicos como parte do processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="81266-115">Keep in mind that you'll need to [configure](/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="81266-116">Teams administradores podem configurar políticas de conformidade de comunicação nos seguintes níveis:</span><span class="sxs-lookup"><span data-stu-id="81266-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="81266-117">**Nível do** usuário: as políticas nesse nível se aplicam a um usuário Teams usuário individual ou podem ser aplicadas a todos os usuários Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="81266-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="81266-118">Essas políticas abrangem mensagens que esses usuários podem enviar em chats de grupo ou 1:1.</span><span class="sxs-lookup"><span data-stu-id="81266-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="81266-119">As comunicações de chat para os usuários são monitoradas automaticamente em todos os Microsoft Teams onde os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="81266-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="81266-120">**Teams nível**: as políticas nesse nível se aplicam a um canal da Equipe da Microsoft, incluindo um canal Privado.</span><span class="sxs-lookup"><span data-stu-id="81266-120">**Teams level**: Policies at this level apply to a Microsoft Team channel, including a Private channel.</span></span> <span data-ttu-id="81266-121">Essas políticas abrangem mensagens enviadas somente Teams canal.</span><span class="sxs-lookup"><span data-stu-id="81266-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="81266-122">Agir em mensagens inadequadas em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81266-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="81266-123">Depois de configurar suas políticas e receber alertas de conformidade de comunicação para mensagens Microsoft Teams, é hora de os revisadores de conformidade em sua organização tomarem medidas sobre essas mensagens.</span><span class="sxs-lookup"><span data-stu-id="81266-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="81266-124">Os revisadores podem ajudar a proteger sua organização, revisando alertas de conformidade de comunicação e removendo mensagens sinalizadas da exibição Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81266-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Remover uma mensagem em Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="81266-126">Mensagens e conteúdo removidos são substituídos por notificações para os visualizadores explicando que a mensagem ou conteúdo foi removido e qual política é aplicável à remoção.</span><span class="sxs-lookup"><span data-stu-id="81266-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="81266-127">O remetente da mensagem ou conteúdo removido também é notificado do status de remoção e fornecido com o conteúdo da mensagem original para contexto relacionado à sua remoção.</span><span class="sxs-lookup"><span data-stu-id="81266-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="81266-128">O remetente também pode exibir a condição de política específica que se aplica à remoção da mensagem.</span><span class="sxs-lookup"><span data-stu-id="81266-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="81266-129">Exemplo de dica de política vista pelo remetente:</span><span class="sxs-lookup"><span data-stu-id="81266-129">Example of policy tip seen by sender:</span></span>

![Dica de política para remetente](./media/communication-compliance-warning-1.png)

<span data-ttu-id="81266-131">Exemplo de notificação de condição de política vista pelo remetente:</span><span class="sxs-lookup"><span data-stu-id="81266-131">Example of policy condition notification seen by the sender:</span></span>

![Informações de condição de política para remetente](./media/communication-compliance-warning-2.png)

<span data-ttu-id="81266-133">Exemplo de dica de política vista pelo destinatário:</span><span class="sxs-lookup"><span data-stu-id="81266-133">Example of policy tip seen by recipient:</span></span>

![Dica de política para destinatário](./media/communication-compliance-warning-3.png)