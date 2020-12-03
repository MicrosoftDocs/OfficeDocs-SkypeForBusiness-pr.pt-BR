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
ms.openlocfilehash: ab48796f877f6af33b8a3c1b2bc5a3cc56e7bd1e
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530978"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="8aea5-104">Visualização Pública do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8aea5-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="8aea5-p102">Talvez os recursos incluídos na pré-visualização possam estar incompletos e possam sofrer alterações antes de ficarem disponíveis no lançamento público. Eles são fornecidoas apenas para fins de avaliação e exploração.</span><span class="sxs-lookup"><span data-stu-id="8aea5-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="8aea5-p103">A Pré-visualização Pública do Microsoft Teams oferece acesso antecipado aos recursos inéditos no Teams. As pré-visualizações permitem que você explore e teste os recursos que estão por vir. Também agradecemos comentários sobre qualquer recurso nas pré-visualizações públicas. A pré-visualização pública está habilitada para cada usuário do Teams, portanto, você não precisa se preocupar em afetar a sua organização.</span><span class="sxs-lookup"><span data-stu-id="8aea5-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled each Teams user, so you don't need to worry about affecting your entire organization.</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="8aea5-111">Definir a política de Atualização</span><span class="sxs-lookup"><span data-stu-id="8aea5-111">Set the Update policy</span></span>

 <span data-ttu-id="8aea5-112">A visualização pública é habilitada para cada usuário e a opção de ativar a visualização pública é controlada em uma política administrativa.</span><span class="sxs-lookup"><span data-stu-id="8aea5-112">Public preview is enabled for each user, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="8aea5-113">As políticas de atualização são usadas para gerenciar o Microsoft Teams e os usuários de visualização do Office que verão recursos de pré-lançamento ou pré-visualização no aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8aea5-113">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="8aea5-114">Você pode usar a política Global (Padrão em toda a organização) e personalizá-la ou criar uma ou mais políticas personalizadas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="8aea5-114">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="8aea5-115">A política precisa ser atribuída a usuários específicos porque não sobrescreve a política global.</span><span class="sxs-lookup"><span data-stu-id="8aea5-115">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="8aea5-116">Entre no Centro de administração.</span><span class="sxs-lookup"><span data-stu-id="8aea5-116">Sign in to the admin center.</span></span>
2. <span data-ttu-id="8aea5-117">Selecione **Teams**>**Atualizar políticas**.</span><span class="sxs-lookup"><span data-stu-id="8aea5-117">Select **Teams**>**Update policies**.</span></span>

   ![Selecionar a opção Atualizar políticas](media/updatePolicies.png)

3. <span data-ttu-id="8aea5-119">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8aea5-119">Select **Add**.</span></span>
4. <span data-ttu-id="8aea5-120">Nomeie a política de atualização, adicione uma descrição e ative **Mostrar recursos de pré-visualização**.</span><span class="sxs-lookup"><span data-stu-id="8aea5-120">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="8aea5-121">Também é possível definir a política usando o Windows PowerShell usando o cmdlet`CsTeamsUpdateManagementPolicy`.</span><span class="sxs-lookup"><span data-stu-id="8aea5-121">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="8aea5-122">Habilitar visualização pública</span><span class="sxs-lookup"><span data-stu-id="8aea5-122">Enable public preview</span></span>

<span data-ttu-id="8aea5-123">Para habilitar a visualização pública em uma área de trabalho ou cliente da web, você precisa realizar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="8aea5-123">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="8aea5-124">Selecione o perfil para exibir o menu Teams.</span><span class="sxs-lookup"><span data-stu-id="8aea5-124">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="8aea5-125">Selecione **Sobre** → **Visualização pública**.</span><span class="sxs-lookup"><span data-stu-id="8aea5-125">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="8aea5-126">Selecione **Alternar para Visualização pública**.</span><span class="sxs-lookup"><span data-stu-id="8aea5-126">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8aea5-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8aea5-127">Related topics</span></span>

[<span data-ttu-id="8aea5-128">Pré-visualização do desenvolvedor público</span><span class="sxs-lookup"><span data-stu-id="8aea5-128">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
