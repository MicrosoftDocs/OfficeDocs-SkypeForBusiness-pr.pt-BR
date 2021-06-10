---
title: Visualização pública no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenha mais informações sobre a prévia pública no Microsoft Teams. Experimente novos recursos e forneça comentários.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: b0719e68dcbf1c73c15ee58e8c7d6be08f359aa5
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863252"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="331e6-104">Visualização Pública do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="331e6-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="331e6-p102">Os recursos incluídos na versão prévia podem não estar completos e podem sofrer alterações antes de se tornarem disponíveis no lançamento público. Eles são fornecidos apenas para fins de avaliação e exploração. Sem suporte na Nuvem da comunidade Office 365 Government.</span><span class="sxs-lookup"><span data-stu-id="331e6-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only. Not supported in Office 365 Government Community Cloud (GCC).</span></span>

<span data-ttu-id="331e6-p103">A Visualização Pública para Microsoft Teams fornece acesso antecipado a recursos não lançados no Teams. As visualizações permitem que você explore e teste os próximos recursos. Também agradecemos comentários sobre qualquer recurso em visualizações públicas. A visualização pública é habilitada por usuário da equipe, então você não precisa se preocupar em afetar toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="331e6-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="331e6-112">Para obter uma lista do que está disponível na visualização pública do Teams, visite as [Notas de Versão do Canal Atual (Pré-visualização)](/officeupdates/current-channel-preview).</span><span class="sxs-lookup"><span data-stu-id="331e6-112">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="331e6-113">Definir a política de atualização</span><span class="sxs-lookup"><span data-stu-id="331e6-113">Set the Update policy</span></span>

<span data-ttu-id="331e6-p104">A visualização pública é habilitada por usuário, e a opção para ativar a visualização pública é controlada em uma política administrativa. As políticas de atualização são usadas para gerenciar o Teams e os usuários de visualização do Office que verão os recursos de pré-lançamento ou de pré-visualização no aplicativo do Teams. Você pode usar a política Global (padrão Org-wide) e personalizá-la, ou criar uma ou mais políticas personalizadas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="331e6-p104">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy. Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app. You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users. The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="331e6-118">Entre no Centro de administração.</span><span class="sxs-lookup"><span data-stu-id="331e6-118">Sign in to the admin center.</span></span>
2. <span data-ttu-id="331e6-119">Selecione **Teams**>**Atualizar políticas**.</span><span class="sxs-lookup"><span data-stu-id="331e6-119">Select **Teams**>**Update policies**.</span></span>

   ![Selecionar a opção Atualizar políticas](media/updatePolicies.png)

3. <span data-ttu-id="331e6-121">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="331e6-121">Select **Add**.</span></span>
4. <span data-ttu-id="331e6-122">Nomeie a política de atualização, adicione uma descrição e ative **Mostrar recursos de pré-visualização**.</span><span class="sxs-lookup"><span data-stu-id="331e6-122">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="331e6-123">Também é possível definir a política usando o Windows PowerShell usando o cmdlet`CsTeamsUpdateManagementPolicy`.</span><span class="sxs-lookup"><span data-stu-id="331e6-123">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="331e6-124">Habilitar visualização pública</span><span class="sxs-lookup"><span data-stu-id="331e6-124">Enable public preview</span></span>

<span data-ttu-id="331e6-125">Para habilitar a visualização pública em uma área de trabalho ou cliente da web, você precisa realizar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="331e6-125">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="331e6-126">Selecione os três pontos à esquerda do seu perfil para exibir o menu Teams.</span><span class="sxs-lookup"><span data-stu-id="331e6-126">Select the three dots to the left of your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="331e6-127">Selecione **Sobre** > **Visualização pública**.</span><span class="sxs-lookup"><span data-stu-id="331e6-127">Select **About** > **Public preview**.</span></span>
3. <span data-ttu-id="331e6-128">Selecione **Alternar para Visualização pública**.</span><span class="sxs-lookup"><span data-stu-id="331e6-128">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="331e6-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="331e6-129">Related topics</span></span>

[<span data-ttu-id="331e6-130">Pré-visualização do desenvolvedor público</span><span class="sxs-lookup"><span data-stu-id="331e6-130">Public developer preview</span></span>](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
