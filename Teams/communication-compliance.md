---
title: Conformidade de comunicação com o Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprender sobre conformidade de comunicação, parte do conjunto de soluções de risco do Insider, da perspectiva do Microsoft Teams (isso faz parte da funcionalidade de conformidade de comunicação do M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328250"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="d6268-103">Conformidade de comunicação com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6268-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="d6268-104">Conformidade com comunicações é uma solução de risco para Insider no Microsoft 365 que ajuda a minimizar os riscos de comunicação ajudando você a detectar, capturar e agir em mensagens inadequadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d6268-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="d6268-105">Para o Microsoft Teams, a conformidade de comunicação ajuda a identificar os [seguintes tipos](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) de conteúdo inadequado em canais de equipe ou em 1:1 e chats em grupo:</span><span class="sxs-lookup"><span data-stu-id="d6268-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="d6268-106">Linguagem ofensiva, obscena e importuna</span><span class="sxs-lookup"><span data-stu-id="d6268-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="d6268-107">Imagens adultas, Racy e Gory</span><span class="sxs-lookup"><span data-stu-id="d6268-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="d6268-108">Compartilhamento de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="d6268-108">Sharing of sensitive information</span></span>

<span data-ttu-id="d6268-109">Para obter mais informações sobre conformidade de comunicação e como configurar políticas para sua organização, consulte [conformidade com comunicações no Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="d6268-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="d6268-110">Como usar a conformidade de comunicação no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6268-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="d6268-111">A conformidade de comunicação e o Microsoft Teams são totalmente integrados e podem ajudar a minimizar os riscos de comunicação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d6268-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="d6268-112">Depois de configurar suas primeiras políticas de conformidade de comunicação, você pode gerenciar ativamente mensagens inadequadas do Microsoft Teams e conteúdo automaticamente sinalizado em alertas.</span><span class="sxs-lookup"><span data-stu-id="d6268-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="d6268-113">Introdução</span><span class="sxs-lookup"><span data-stu-id="d6268-113">Getting started</span></span>

<span data-ttu-id="d6268-114">Começar a usar a conformidade de comunicação no Microsoft Teams começa com o [planejamento](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) e a criação de políticas predefinidas ou personalizadas para identificar atividades inadequadas do usuário em canais de equipe ou no 1:1 e grupos.</span><span class="sxs-lookup"><span data-stu-id="d6268-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="d6268-115">Lembre-se de que você precisará [Configurar](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) algumas permissões e pré-requisitos básicos como parte do processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="d6268-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="d6268-116">Os administradores do teams podem configurar políticas de conformidade de comunicação nos seguintes níveis:</span><span class="sxs-lookup"><span data-stu-id="d6268-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="d6268-117">**Nível do usuário**: as políticas nesse nível se aplicam a um usuário individual do teams ou podem ser aplicadas a todos os usuários do teams na sua organização.</span><span class="sxs-lookup"><span data-stu-id="d6268-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="d6268-118">Essas políticas abrangem mensagens que esses usuários podem enviar no 1:1 ou em chats em grupo.</span><span class="sxs-lookup"><span data-stu-id="d6268-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="d6268-119">As comunicações por chat para os usuários são automaticamente monitoradas em todas as equipes da Microsoft, onde os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="d6268-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="d6268-120">**Nível**de equipe: as políticas nesse nível se aplicam a um canal do Microsoft Team.</span><span class="sxs-lookup"><span data-stu-id="d6268-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="d6268-121">Essas políticas abrangem as mensagens enviadas somente no canal de equipe.</span><span class="sxs-lookup"><span data-stu-id="d6268-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="d6268-122">Agir em mensagens inadequadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6268-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="d6268-123">Depois de configurar suas políticas e ter recebido alertas de conformidade de comunicação para mensagens do Microsoft Teams, é hora de os revisores de conformidade em sua organização executarem ações nessas mensagens.</span><span class="sxs-lookup"><span data-stu-id="d6268-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="d6268-124">Os revisores podem ajudar a proteger sua organização revisando alertas de conformidade de comunicação e removendo mensagens sinalizadas do modo de exibição no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6268-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Remover uma mensagem no Microsoft Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="d6268-126">As mensagens e o conteúdo removidos são substituídos por notificações para visualizadores explicando que a mensagem ou o conteúdo foi removido e qual política se aplica à remoção.</span><span class="sxs-lookup"><span data-stu-id="d6268-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="d6268-127">O remetente da mensagem ou do conteúdo removido também é notificado sobre o status de remoção e fornecido com o conteúdo da mensagem original para contexto relacionado à sua remoção.</span><span class="sxs-lookup"><span data-stu-id="d6268-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="d6268-128">O remetente também pode exibir a condição específica da política que se aplica à remoção da mensagem.</span><span class="sxs-lookup"><span data-stu-id="d6268-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="d6268-129">Exemplo de dica de política vista pelo remetente:</span><span class="sxs-lookup"><span data-stu-id="d6268-129">Example of policy tip seen by sender:</span></span>

![Dica de política para remetente](./media/communication-compliance-warning-1.png)

<span data-ttu-id="d6268-131">Exemplo de notificação de condição da política vista pelo remetente:</span><span class="sxs-lookup"><span data-stu-id="d6268-131">Example of policy condition notification seen by the sender:</span></span>

![Informações de condição da política para o remetente](./media/communication-compliance-warning-2.png)

<span data-ttu-id="d6268-133">Exemplo de dica de política vista pelo destinatário:</span><span class="sxs-lookup"><span data-stu-id="d6268-133">Example of policy tip seen by recipient:</span></span>

![Dica de política para destinatário](./media/communication-compliance-warning-3.png)
