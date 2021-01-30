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
ms.openlocfilehash: 6a8d677b4acd56e6de5681d40a1e1aa69008a1ad
ms.sourcegitcommit: 6262deaede6f25b17624d7468eff7a2863eeacf7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50043955"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="226cf-104">Visualização Pública do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="226cf-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="226cf-p102">Talvez os recursos incluídos na pré-visualização possam estar incompletos e possam sofrer alterações antes de ficarem disponíveis no lançamento público. Eles são fornecidoas apenas para fins de avaliação e exploração.</span><span class="sxs-lookup"><span data-stu-id="226cf-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="226cf-p103">A Visualização Pública para Microsoft Teams fornece acesso antecipado a recursos não lançados no Teams. As visualizações permitem que você explore e teste os próximos recursos. Também agradecemos comentários sobre qualquer recurso em visualizações públicas. A visualização pública é habilitada por usuário da equipe, então você não precisa se preocupar em afetar toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="226cf-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="226cf-111">Para obter uma lista do que está disponível na visualização pública do Teams, visite as [Notas de Versão do Canal Atual (Pré-visualização)](https://docs.microsoft.com/officeupdates/current-channel-preview).</span><span class="sxs-lookup"><span data-stu-id="226cf-111">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](https://docs.microsoft.com/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="226cf-112">Definir a política de atualização</span><span class="sxs-lookup"><span data-stu-id="226cf-112">Set the Update policy</span></span>

<span data-ttu-id="226cf-113">A visualização pública é habilitada por usuário, e a opção de ativar a visualização pública é controlada por uma política administrativa.</span><span class="sxs-lookup"><span data-stu-id="226cf-113">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="226cf-114">As políticas de atualização são usadas para gerenciar o Microsoft Teams e os usuários de visualização do Office que verão recursos de pré-lançamento ou pré-visualização no aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="226cf-114">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="226cf-115">Você pode usar a política Global (Padrão em toda a organização) e personalizá-la ou criar uma ou mais políticas personalizadas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="226cf-115">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="226cf-116">A política precisa ser atribuída a usuários específicos porque não sobrescreve a política global.</span><span class="sxs-lookup"><span data-stu-id="226cf-116">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="226cf-117">Entre no Centro de administração.</span><span class="sxs-lookup"><span data-stu-id="226cf-117">Sign in to the admin center.</span></span>
2. <span data-ttu-id="226cf-118">Selecione **Teams**>**Atualizar políticas**.</span><span class="sxs-lookup"><span data-stu-id="226cf-118">Select **Teams**>**Update policies**.</span></span>

   ![Selecionar a opção Atualizar políticas](media/updatePolicies.png)

3. <span data-ttu-id="226cf-120">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="226cf-120">Select **Add**.</span></span>
4. <span data-ttu-id="226cf-121">Nomeie a política de atualização, adicione uma descrição e ative **Mostrar recursos de pré-visualização**.</span><span class="sxs-lookup"><span data-stu-id="226cf-121">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="226cf-122">Também é possível definir a política usando o Windows PowerShell usando o cmdlet`CsTeamsUpdateManagementPolicy`.</span><span class="sxs-lookup"><span data-stu-id="226cf-122">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="226cf-123">Habilitar visualização pública</span><span class="sxs-lookup"><span data-stu-id="226cf-123">Enable public preview</span></span>

<span data-ttu-id="226cf-124">Para habilitar a visualização pública em uma área de trabalho ou cliente da web, você precisa realizar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="226cf-124">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="226cf-125">Selecione o perfil para exibir o menu Teams.</span><span class="sxs-lookup"><span data-stu-id="226cf-125">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="226cf-126">Selecione **Sobre** → **Visualização pública**.</span><span class="sxs-lookup"><span data-stu-id="226cf-126">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="226cf-127">Selecione **Alternar para Visualização pública**.</span><span class="sxs-lookup"><span data-stu-id="226cf-127">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="226cf-128">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="226cf-128">Related topics</span></span>

[<span data-ttu-id="226cf-129">Pré-visualização do desenvolvedor público</span><span class="sxs-lookup"><span data-stu-id="226cf-129">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)

