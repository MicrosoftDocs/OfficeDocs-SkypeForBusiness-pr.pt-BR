---
title: Conformidade de comunicação do Microsoft Teams
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
ms.openlocfilehash: 01d9906044fe0ea8472cd8bb2ba8ccf247cdbeb9
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121691"
---
# <a name="communication-compliance-for-microsoft-teams"></a><span data-ttu-id="c794e-103">Conformidade de comunicação do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c794e-103">Communication compliance for Microsoft Teams</span></span>

<span data-ttu-id="c794e-104">A conformidade com comunicações faz parte da nova solução de risco do insider definida no Microsoft 365, que ajuda a minimizar os riscos de comunicação, ajudando você a detectar, capturar e fazer ações de correção para mensagens inadequadas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c794e-104">Communication compliance is part of the new insider risk solution set in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="c794e-105">Isso ajuda a identificar uma linguagem ofensiva e um antiassédio em canais de equipe ou 1:1 e chats em grupo.</span><span class="sxs-lookup"><span data-stu-id="c794e-105">It helps in identifying Offensive language and anti-harassment in Team Channels or 1:1 and Group chats.</span></span> <span data-ttu-id="c794e-106">Você também pode definir políticas para ver se as informações confidenciais estão sendo compartilhadas como parte dos canais da equipe ou 1:1 e chats em grupo.</span><span class="sxs-lookup"><span data-stu-id="c794e-106">You can also set policies to see if any Sensitive information is being shared as part of Team channels or 1:1 and Group chats.</span></span> <span data-ttu-id="c794e-107">Para obter mais informações sobre diferentes tipos de políticas e como configurar, consulte o [artigo M365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="c794e-107">For more information on different types of policies and how to set up refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-teams"></a><span data-ttu-id="c794e-108">Como usar a conformidade com comunicações no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c794e-108">How to use communication compliance in Teams</span></span>

### <a name="identify-inappropriate-messages"></a><span data-ttu-id="c794e-109">Identificar mensagens inadequadas</span><span class="sxs-lookup"><span data-stu-id="c794e-109">Identify inappropriate messages</span></span>

<span data-ttu-id="c794e-110">Se você deseja identificar as mensagens que são enviadas no Microsoft Teams (1:1, chats em grupo ou conversas de canal) contenham idiomas ofensivos ou antiassédio, você pode habilitar políticas para identificar isso, e o revisor pode examinar as mensagens e tomar as medidas necessárias, como enviar material de treinamento ou encaminhar para as autoridades certas.</span><span class="sxs-lookup"><span data-stu-id="c794e-110">If you want to identify any messages that are sent in Microsoft Teams (1:1, Group Chats or Channel conversations) contain Offensive Language or anti-harassment, you can enable policies to identify this and the reviewer can look into the messages and take necessary steps like sending training material or escalate to the right authorities.</span></span>

### <a name="identify-sensitive-or-regulatory-information"></a><span data-ttu-id="c794e-111">Identificar informações confidenciais ou normativas</span><span class="sxs-lookup"><span data-stu-id="c794e-111">Identify sensitive or Regulatory information</span></span>

<span data-ttu-id="c794e-112">Se você quiser verificar mensagens enviadas no Microsoft Teams (1:1, chats em grupo ou conversas de canal) para obter informações confidenciais ou tipos regulatórios, poderá escolher políticas que ofereçam suporte a tipos confidenciais ou regulatórios predefinidos.</span><span class="sxs-lookup"><span data-stu-id="c794e-112">If you want to scan messages sent in Microsoft Teams (1:1, Group Chats or Channel conversations) for sensitive information or regulatory types, you can choose policies that support predefined sensitive or regulatory types.</span></span>

> [!NOTE]
> <span data-ttu-id="c794e-113">Os canais privados não são compatíveis com a conformidade de comunicação.</span><span class="sxs-lookup"><span data-stu-id="c794e-113">Private channels are not supported by communication compliance.</span></span>

### <a name="custom-policy"></a><span data-ttu-id="c794e-114">Política personalizada</span><span class="sxs-lookup"><span data-stu-id="c794e-114">Custom Policy</span></span>

<span data-ttu-id="c794e-115">Use este modelo para configurar canais de comunicação específicos, condições individuais de detecção e o volume de conteúdo a ser monitorado e revisado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c794e-115">Use this template to configure specific communication channels, individual detection conditions, and the amount of content to monitor and review in your organization.</span></span>

### <a name="custom-trainable-classifier"></a><span data-ttu-id="c794e-116">Classificador treinado personalizado</span><span class="sxs-lookup"><span data-stu-id="c794e-116">Custom Trainable classifier</span></span>

<span data-ttu-id="c794e-117">Use classificadores ferroviárias quando um dos classificadores prontos para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="c794e-117">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="c794e-118">Um classificador do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo dando a ele exemplos para ver.</span><span class="sxs-lookup"><span data-stu-id="c794e-118">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="c794e-119">O treinamento do classificador envolve primeiro dar a ele exemplos que sejam separados à sua categoria humana e positiva.</span><span class="sxs-lookup"><span data-stu-id="c794e-119">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="c794e-120">Depois disso, após processar esses exemplos, você testará as previsões dando a ele uma mistura de exemplos positivos e negativos.</span><span class="sxs-lookup"><span data-stu-id="c794e-120">Then, after it has processed those samples, you test the predictions by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="c794e-121">Para obter mais informações sobre isso, consulte o [artigo M365](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) para obter mais informações sobre este tópico.</span><span class="sxs-lookup"><span data-stu-id="c794e-121">To Lean more about this refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) for more on this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="c794e-122">A conformidade com comunicações agora oferece suporte a implantações híbridas do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c794e-122">Communication compliance now supports Exchange hybrid deployments.</span></span>

<span data-ttu-id="c794e-123">Conformidade de comunicação compatível com o histórico de conversas para qualquer mensagem que corresponda às políticas.</span><span class="sxs-lookup"><span data-stu-id="c794e-123">Communication compliance supports conversation history for any messages that match the polices.</span></span> <span data-ttu-id="c794e-124">Isso fornece contexto para o administrador de investigação.</span><span class="sxs-lookup"><span data-stu-id="c794e-124">This provides context to the investigating admin.</span></span>

:::image type="content" source="media/communication-compliance-1.png" alt-text="Uma tela para conformidade de comunicação no Microsoft Teams.":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a><span data-ttu-id="c794e-126">Onde as políticas de comunicação podem ser aplicadas no Teams</span><span class="sxs-lookup"><span data-stu-id="c794e-126">Where communication policies can be applied in Teams</span></span>

<span data-ttu-id="c794e-127">As políticas de conformidade de comunicação podem ser configuradas para mensagens enviadas no Microsoft Teams nos seguintes níveis:</span><span class="sxs-lookup"><span data-stu-id="c794e-127">Communication compliance policies can be setup for messages sent in Teams at the following levels:</span></span>

- <span data-ttu-id="c794e-128">Nível do usuário: um administrador pode configurar políticas em um nível de usuário individual ou aplicá-las a todos os usuários no locatário.</span><span class="sxs-lookup"><span data-stu-id="c794e-128">User level : An admin can set up policies at an individual user level or apply it to all the users on the tenant.</span></span> <span data-ttu-id="c794e-129">Isso inclui apenas as mensagens que um usuário enviou no 1:1 ou chats em grupo.</span><span class="sxs-lookup"><span data-stu-id="c794e-129">This will only covers messages that a user sent in 1:1 or Group chats.</span></span>
- <span data-ttu-id="c794e-130">Nível da equipe: um administrador também pode configurar políticas em uma equipe.</span><span class="sxs-lookup"><span data-stu-id="c794e-130">Team Level: An admin can also set up policies on a team.</span></span> <span data-ttu-id="c794e-131">Isso abrange todas as mensagens enviadas no canal da equipe (mensagens de canal privado não são suportadas).</span><span class="sxs-lookup"><span data-stu-id="c794e-131">This covers all the messages sent in the channel in that team (Private channel messages are not supported).</span></span>
