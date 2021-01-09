---
title: Políticas de retenção no Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Use as políticas de retenção do Microsoft Teams para manter as mensagens necessárias para atender às políticas internas, regulamentações do setor ou necessidades legais e excluir mensagens consideradas como responsabilidades ou que não têm valor comercial legal.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786823"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="07122-103">Políticas de retenção no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07122-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="07122-104">As políticas de retenção e os rótulos de retenção do Microsoft 365 ajudam você a gerenciar com mais eficiência as informações em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07122-104">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="07122-105">Você pode definir configurações de retenção para manter os dados necessários para atender às políticas internas, regulamentações do setor ou necessidades legais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="07122-105">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs.</span></span> <span data-ttu-id="07122-106">Você também pode definir configurações de retenção para excluir dados que são considerados uma responsabilidade, que você não precisa mais manter ou que não tem valor legal ou comercial.</span><span class="sxs-lookup"><span data-stu-id="07122-106">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="07122-107">O Teams oferece suporte a políticas de retenção para mensagens de chat e canal para que, como administrador, você possa decidir proativamente se deve reter esses dados, excluí-los ou retê-los por um período específico de tempo e excluí-los.</span><span class="sxs-lookup"><span data-stu-id="07122-107">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="07122-108">Você pode aplicar uma política de retenção do Teams para toda a organização ou para usuários e equipes específicas.</span><span class="sxs-lookup"><span data-stu-id="07122-108">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="07122-109">Os rótulos de retenção não são suportados para o Teams.</span><span class="sxs-lookup"><span data-stu-id="07122-109">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="07122-110">Para saber mais sobre retenção e como você pode aplicar configurações de retenção usando políticas de retenção ou rótulos de retenção para outras cargas de trabalho no Microsoft 365, consulte Saiba mais sobre políticas de retenção e rótulos de [retenção.](https://docs.microsoft.com/microsoft-365/compliance/retention)</span><span class="sxs-lookup"><span data-stu-id="07122-110">To learn more about retention, and how you can apply retention settings by using retention policies or retention labels for other workloads in Microsoft 365, see [Learn about retention policies and retention labels](https://docs.microsoft.com/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="07122-111">O requisito mínimo de licenciamento para políticas de retenção para o Teams é o Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="07122-111">The minimum licensing requirement for retention policies for Teams is Microsoft 365 E3.</span></span> <span data-ttu-id="07122-112">Para saber mais sobre licenciamento, confira a [descrição do serviço do Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="07122-112">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-work"></a><span data-ttu-id="07122-113">Como funcionam as políticas de retenção do Teams</span><span class="sxs-lookup"><span data-stu-id="07122-113">How Teams retention policies work</span></span>

<span data-ttu-id="07122-114">As mensagens de chat do Teams são armazenadas em uma pasta oculta na caixa de correio de cada usuário incluída no chat, e as mensagens de canal do Teams são armazenadas em uma pasta oculta semelhante na caixa de correio de grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="07122-114">Teams chat messages are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> <span data-ttu-id="07122-115">Para reter mensagens sujeitas a uma política de retenção, uma cópia do conteúdo é mantida automaticamente em uma pasta oculta chamada **SubstrateHolds** como uma subpasta na pasta Itens **Recuperáveis** do Exchange.</span><span class="sxs-lookup"><span data-stu-id="07122-115">To retain messages that are subject to a retention policy, a copy of the content is automatically kept in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span> <span data-ttu-id="07122-116">Até que essas mensagens sejam permanentemente excluídas da pasta SubstrateHolds, elas permanecerão pesquisáveis pelas ferramentas de Descobertas Digitais.</span><span class="sxs-lookup"><span data-stu-id="07122-116">Until these messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="07122-117">Para obter informações detalhadas sobre o que está incluído e excluído das políticas de retenção do Teams e como essas políticas funcionam dependendo da configuração da política, consulte Saiba mais sobre retenção para o [Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)</span><span class="sxs-lookup"><span data-stu-id="07122-117">For detailed information about what's included and excluded for Teams retention policies, and how these policies work depending on your policy configuration, see [Learn about retention for Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="07122-118">Essa página explica por que, às vezes, você pode ver atrasos quando as políticas de retenção excluem mensagens.</span><span class="sxs-lookup"><span data-stu-id="07122-118">That page explains why you might sometimes see delays when retention policies delete messages.</span></span> <span data-ttu-id="07122-119">Por exemplo, as mensagens podem ficar visíveis até 7 dias após o período de expiração que você configurou na política de retenção.</span><span class="sxs-lookup"><span data-stu-id="07122-119">For example, messages can be visible up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="07122-120">Se você configurar várias políticas de retenção do Teams com configurações de retenção diferentes, os princípios de retenção resolverão quaisquer conflitos.</span><span class="sxs-lookup"><span data-stu-id="07122-120">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="07122-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="07122-121">For example:</span></span>
- <span data-ttu-id="07122-122">Se houver um conflito entre reter ou excluir o mesmo conteúdo, o conteúdo será sempre retido.</span><span class="sxs-lookup"><span data-stu-id="07122-122">If there is a conflict between retaining or deleting the same content, the content is always retained.</span></span>
- <span data-ttu-id="07122-123">Se houver um conflito quanto ao tempo para reter o mesmo conteúdo, ele será mantido pelo período de retenção mais longo.</span><span class="sxs-lookup"><span data-stu-id="07122-123">If there is a conflict in how long to retain the same content, it is retained for the longest retention period.</span></span>

<span data-ttu-id="07122-124">Esses dois princípios de retenção abordam a maioria dos conflitos que podem surgir quando você tem várias políticas de retenção para o Teams, mas para obter mais informações, consulte Os princípios de retenção ou o que [tem precedência?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="07122-124">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="07122-125">Quando usar as políticas de retenção para o Teams.</span><span class="sxs-lookup"><span data-stu-id="07122-125">When to use retention policies for Teams</span></span>

<span data-ttu-id="07122-126">Em muitos casos, as organizações consideram os dados de chat privados como um número mais passivo do que as mensagens de canal, que geralmente são conversas mais relacionadas ao projeto.</span><span class="sxs-lookup"><span data-stu-id="07122-126">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="07122-127">Você pode configurar uma política de retenção separada para chats privados (1:1 ou 1: muitos chats) e mensagens de canal.</span><span class="sxs-lookup"><span data-stu-id="07122-127">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="07122-128">Você também pode configurar políticas exclusivas que se aplicam a usuários ou equipes específicas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07122-128">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="07122-129">Nos chats do Teams, você pode selecionar a quais usuários a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="07122-129">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="07122-130">Para mensagens de canal do Teams, você pode selecionar a quais equipes a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="07122-130">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="07122-131">Por exemplo, para mensagens de canal, você pode aplicar uma política de exclusão de um ano a equipes específicas em sua organização e aplicar uma política de exclusão de três anos a todas as outras equipes.</span><span class="sxs-lookup"><span data-stu-id="07122-131">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="07122-132">Criar e gerenciar políticas de retenção para o Teams</span><span class="sxs-lookup"><span data-stu-id="07122-132">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="07122-133">Para criar uma política de retenção para chats e mensagens de canal do Teams, use as instruções da política de [retenção para locais do Teams.](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)</span><span class="sxs-lookup"><span data-stu-id="07122-133">To create a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="07122-134">Essa página tem informações adicionais sobre como criar e gerenciar políticas de retenção para outras cargas de trabalho no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07122-134">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="07122-135">Por exemplo, talvez você queira também criar uma política de retenção para grupos do Microsoft 365 para reter e excluir arquivos que são acessados no Teams e armazenados no OneDrive ou no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07122-135">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="07122-136">Experiência do usuário final</span><span class="sxs-lookup"><span data-stu-id="07122-136">End user experience</span></span>

<span data-ttu-id="07122-137">Para chats privados (chats de 1:1) ou chats em grupo, os usuários finais verão que os chats mais antigos que a configuração da política de retenção são excluídos e uma mensagem de controle informando "Excluímos mensagens mais antigas devido à política de retenção da sua organização" é mostrada sobre mensagens ainda não excluídas.</span><span class="sxs-lookup"><span data-stu-id="07122-137">For private chats (1:1 chats) or group chats, the end users will see that chats older than the retention policy configuration are deleted and a control message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="Usuário informado no Teams que a mensagem de chat é excluída por causa de uma política de retenção do Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Usuário no Teams explicando que as mensagens são excluídas como resultado de uma política de retenção do Teams":::

<span data-ttu-id="07122-140">Para mensagens de canal, os usuários finais (membros do canal) verão as mensagens excluídas desaparecerem da exibição depois que as mensagens expirarem.</span><span class="sxs-lookup"><span data-stu-id="07122-140">For Channel messages, the end users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="07122-141">Se a mensagem excluída foi uma mensagem pai de uma conversa encadeada, em vez da mensagem pai, será exibida uma mensagem informando "Esta mensagem foi excluída por causa de uma Política de Retenção".</span><span class="sxs-lookup"><span data-stu-id="07122-141">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="Captura de tela do canal antes da retenção":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Captura de tela do canal após a retenção":::

> [!NOTE]
> <span data-ttu-id="07122-144">As mensagens exibidas que os usuários finais veem como resultado de mensagens excluídas não são configuráveis no momento.</span><span class="sxs-lookup"><span data-stu-id="07122-144">The displayed messages that end users see as a result of deleted messaging are not configurable at this time.</span></span>


## <a name="related-topics"></a><span data-ttu-id="07122-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="07122-145">Related topics</span></span>

- [<span data-ttu-id="07122-146">Começar a trabalhar com políticas de retenção e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="07122-146">Get started with retention policies and retention labels</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="07122-147">Saiba mais sobre retenção para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07122-147">Learn about retention for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="07122-148">Criar e configurar políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="07122-148">Create and configure retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)