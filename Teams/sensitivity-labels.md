---
title: Rótulos de sensibilidade do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Saiba como definir e usar rótulos de sensibilidade no Microsoft Teams.
ms.openlocfilehash: 4f1bdc4715fd1375cff637604c93962e2f30c258
ms.sourcegitcommit: d7f49f8c28cba32d3715ea1965c736e6ba574bda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45091264"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="81b6d-103">Rótulos de sensibilidade do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81b6d-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="81b6d-104">Os [Rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permitem que os administradores de equipe regulam o acesso a conteúdo organizacional confidencial criado durante a colaboração dentro do teams.</span><span class="sxs-lookup"><span data-stu-id="81b6d-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="81b6d-105">Você pode definir rótulos de sensibilidade e suas políticas associadas no [centro de conformidade de & de segurança](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="81b6d-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="81b6d-106">Esses rótulos e políticas são automaticamente aplicados ao Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="81b6d-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="81b6d-107">Qual é a diferença entre rótulos de sensibilidade e rótulos de classificação de equipes?</span><span class="sxs-lookup"><span data-stu-id="81b6d-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="81b6d-108">Rótulos de sensibilidade são diferentes dos rótulos de classificação que exigem que você os crie usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81b6d-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="81b6d-109">Os rótulos de classificação são cadeias de caracteres de texto que podem ser associadas a um grupo, mas não têm políticas reais associadas a eles.</span><span class="sxs-lookup"><span data-stu-id="81b6d-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="81b6d-110">Você usa rótulos de classificação como metadados para impor políticas manualmente por meio de ferramentas e scripts internos.</span><span class="sxs-lookup"><span data-stu-id="81b6d-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="81b6d-111">Por outro lado, as etiquetas de sensibilidade e suas políticas são automaticamente impostas de ponta a ponta por meio de uma combinação da plataforma de grupos, do centro de conformidade & do centro de conformidade e dos serviços do teams.</span><span class="sxs-lookup"><span data-stu-id="81b6d-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="81b6d-112">Os rótulos de sensibilidade fornecem suporte avançado à infraestrutura para proteger os dados confidenciais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="81b6d-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="81b6d-113">Para migrar seus grupos existentes de rótulos de classificação para usar rótulos de sensibilidade, use as instruções em [Rótulos de classificação e sensibilidade do Azure Active Directory para grupos do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="81b6d-113">To migrate your existing Groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>
## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="81b6d-114">Criar, gerenciar e publicar rótulos de sensibilidade para equipes</span><span class="sxs-lookup"><span data-stu-id="81b6d-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="81b6d-115">Para saber como habilitar, criar e publicar rótulos de sensibilidade para equipes, consulte [Rótulos de classificação e sensibilidade do Azure Active Directory para grupos do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="81b6d-115">For how to enable, create, and publish sensitivity labels for Teams, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="81b6d-116">Criar, atualizar e excluir rótulos de sensibilidade exigem sequenciamento cuidadoso com rótulos de publicação para usuários.</span><span class="sxs-lookup"><span data-stu-id="81b6d-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="81b6d-117">Qualquer desvio na sequência pode resultar em erros persistentes de criação de equipe para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="81b6d-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="81b6d-118">Portanto, é essencial fazer o seguinte quando você <a href="#createpublishlabels">cria e publica rótulos</a>, <a href="#modifydeletelabels">modifica e exclui rótulos publicados</a>e <a href="#manageerrors">gerencia erros de criação de equipe</a>.</span><span class="sxs-lookup"><span data-stu-id="81b6d-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="81b6d-119">**Criar e publicar rótulos** <a name="createpublishlabels"> </a></span><span class="sxs-lookup"><span data-stu-id="81b6d-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="81b6d-120">Quando um rótulo é criado e publicado no centro de conformidade do & de segurança, pode levar até 10 minutos para o rótulo ficar visível na interface de criação do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81b6d-120">When a label is created and published in the Security & Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="81b6d-121">Use as etapas a seguir para publicar o rótulo para todos os usuários no locatário:</span><span class="sxs-lookup"><span data-stu-id="81b6d-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="81b6d-122">Crie o rótulo e publique-o para algumas contas de usuário selecionadas no locatário.</span><span class="sxs-lookup"><span data-stu-id="81b6d-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="81b6d-123">Quando o rótulo for publicado, aguarde 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="81b6d-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="81b6d-124">Após 10 minutos, tente criar uma equipe com o rótulo usando uma das contas de usuário que têm acesso ao rótulo.</span><span class="sxs-lookup"><span data-stu-id="81b6d-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="81b6d-125">Se a equipe criou com êxito a etapa 3, siga em frente e publique o rótulo dos usuários remanescentes no locatário.</span><span class="sxs-lookup"><span data-stu-id="81b6d-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="81b6d-126">**Modificar e excluir rótulos publicados** <a name="modifydeletelabels"> </a></span><span class="sxs-lookup"><span data-stu-id="81b6d-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="81b6d-127">Excluir ou modificar o rótulo enquanto ele está associado a políticas de sensibilidade pode resultar em falhas de criação de equipe em todo o locatário.</span><span class="sxs-lookup"><span data-stu-id="81b6d-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="81b6d-128">Portanto, antes de excluir ou modificar um rótulo, primeiro você deve desassociar o rótulo de suas políticas associadas.</span><span class="sxs-lookup"><span data-stu-id="81b6d-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="81b6d-129">Use as etapas a seguir</span><span class="sxs-lookup"><span data-stu-id="81b6d-129">Use the following steps</span></span>  
<span data-ttu-id="81b6d-130">para excluir ou modificar um rótulo:</span><span class="sxs-lookup"><span data-stu-id="81b6d-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="81b6d-131">Remova o rótulo de todas as políticas que usam o rótulo.</span><span class="sxs-lookup"><span data-stu-id="81b6d-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="81b6d-132">Ou, se preferir, você também pode excluir as próprias políticas.</span><span class="sxs-lookup"><span data-stu-id="81b6d-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="81b6d-133">Quando o rótulo é removido das políticas ou as próprias diretivas são excluídas, aguarde 10 minutos antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="81b6d-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="81b6d-134">Após 10 minutos, inicie a interface de criação de equipe e certifique-se de que o rótulo não fique mais visível para qualquer usuário no locatário.</span><span class="sxs-lookup"><span data-stu-id="81b6d-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="81b6d-135">Agora você pode excluir ou modificar o rótulo com segurança.</span><span class="sxs-lookup"><span data-stu-id="81b6d-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="81b6d-136">**Gerenciar erros** <a name="manageerrors"> </a> de criação de equipe</span><span class="sxs-lookup"><span data-stu-id="81b6d-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="81b6d-137">Se a criação de equipe começar a falhar em qualquer ponto durante a visualização pública, você terá duas opções:</span><span class="sxs-lookup"><span data-stu-id="81b6d-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="81b6d-138">Certifique-se de que os rótulos de sensibilidade não sejam obrigatórios para qualquer usuário durante a criação da equipe.</span><span class="sxs-lookup"><span data-stu-id="81b6d-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="81b6d-139">Desative os rótulos de sensibilidade usando os scripts em [habilitar esta visualização](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span><span class="sxs-lookup"><span data-stu-id="81b6d-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="81b6d-140">Observe que a configuração EnableMIPLabels deve ser definida como false da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="81b6d-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="81b6d-141">Usar rótulos de sensibilidade com o Teams</span><span class="sxs-lookup"><span data-stu-id="81b6d-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="81b6d-142">Aqui estão alguns exemplos de cenários de como você pode usar rótulos de sensibilidade com o Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="81b6d-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="81b6d-143">Configuração de privacidade do teams</span><span class="sxs-lookup"><span data-stu-id="81b6d-143">Privacy setting of teams</span></span>

<span data-ttu-id="81b6d-144">Você pode criar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite que os usuários criem equipes com uma configuração específica de privacidade (pública ou particular).</span><span class="sxs-lookup"><span data-stu-id="81b6d-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="81b6d-145">Por exemplo, você pode criar um rótulo chamado "confidencial" no centro de conformidade do & de segurança e configurar o Microsoft Teams para que qualquer equipe criada com esse rótulo deve ser uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="81b6d-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="81b6d-146">Quando um usuário cria uma nova equipe e seleciona o rótulo **confidencial** , a única opção de privacidade que está disponível para o usuário é **particular**.</span><span class="sxs-lookup"><span data-stu-id="81b6d-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="81b6d-147">Outras opções de privacidade, como público e toda a organização, são desabilitadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="81b6d-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Captura de tela de rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="81b6d-149">Da mesma forma, se o usuário selecionar **geral** quando criar uma nova equipe, ele só poderá criar equipes públicas ou de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="81b6d-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

<span data-ttu-id="81b6d-151">Quando a equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais da equipe.</span><span class="sxs-lookup"><span data-stu-id="81b6d-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

<span data-ttu-id="81b6d-153">Um proprietário de equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, acessando a equipe e, em seguida, clicando em **Editar equipe**.</span><span class="sxs-lookup"><span data-stu-id="81b6d-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="81b6d-155">Acesso de convidado a equipes</span><span class="sxs-lookup"><span data-stu-id="81b6d-155">Guest access to teams</span></span>

<span data-ttu-id="81b6d-156">Você pode especificar se uma equipe criada com um rótulo específico permite acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="81b6d-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="81b6d-157">As equipes criadas com um rótulo que não permite acesso de convidado só estão disponíveis para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="81b6d-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="81b6d-158">Pessoas de fora da sua organização não podem ser adicionadas à equipe.</span><span class="sxs-lookup"><span data-stu-id="81b6d-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="81b6d-159">Rótulos de sensibilidade no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81b6d-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="81b6d-160">Você pode definir rótulos de sensibilidade ao criar ou editar uma equipe no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81b6d-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="81b6d-161">Os rótulos de sensibilidade também são visíveis nas propriedades da equipe e na coluna **classificação** na página gerenciar equipes do centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81b6d-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="81b6d-162">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="81b6d-162">Known issues</span></span>

<span data-ttu-id="81b6d-163">**Rótulos padrão filho não exibidos durante a criação da equipe**</span><span class="sxs-lookup"><span data-stu-id="81b6d-163">**Child default labels not showing during team creation**</span></span>

<span data-ttu-id="81b6d-164">Atualmente, um rótulo filho definido como o rótulo padrão para equipes não será exibido na parte superior da lista na lista de rótulos de sensibilidade no modelo de criação de equipe.</span><span class="sxs-lookup"><span data-stu-id="81b6d-164">Currently, a child label set as the default label for Teams will not show at the top of the list in the sensitivity labels dropdown in the team creation model.</span></span> <span data-ttu-id="81b6d-165">Os criadores de equipe ainda podem usar o menu suspenso para aplicar o rótulo filho como solução alternativa.</span><span class="sxs-lookup"><span data-stu-id="81b6d-165">Team creators can still use the dropdown to apply the child label as a workaround.</span></span>

<span data-ttu-id="81b6d-166">**Suporte para rótulos de sensibilidade em APIs de gráficos do Teams, cmdlets e modelos do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="81b6d-166">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="81b6d-167">Atualmente, os usuários não poderão aplicar rótulos de sensibilidade em equipes criadas diretamente por meio de APIs de gráfico, cmdlets e modelos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81b6d-167">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="81b6d-168">**Suporte para rótulos de sensibilidade em SKUs EDU do teams**</span><span class="sxs-lookup"><span data-stu-id="81b6d-168">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="81b6d-169">No momento, os rótulos de sensibilidade não são aceitos para clientes que usam SKUs de educação do teams.</span><span class="sxs-lookup"><span data-stu-id="81b6d-169">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="81b6d-170">**Edição de rótulos de sensibilidade diretamente em um conjunto de sites do SharePoint para canais privados**</span><span class="sxs-lookup"><span data-stu-id="81b6d-170">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="81b6d-171">Os canais privados criados em uma equipe herdam o rótulo de sensibilidade que foi aplicado a uma equipe.</span><span class="sxs-lookup"><span data-stu-id="81b6d-171">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="81b6d-172">Além disso, o mesmo rótulo é aplicado automaticamente no conjunto de sites do SharePoint para o canal privado.</span><span class="sxs-lookup"><span data-stu-id="81b6d-172">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="81b6d-173">Se um usuário atualizar diretamente o rótulo de sensibilidade em um conjunto de sites do SharePoint para um canal privado, esse rótulo não será atualizado no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="81b6d-173">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="81b6d-174">Nesse cenário, os usuários continuarão a ver o rótulo de sensibilidade aplicado a uma equipe no cabeçalho do canal privado.</span><span class="sxs-lookup"><span data-stu-id="81b6d-174">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="81b6d-175">**Tempo de propagação de alterações aplicadas a rótulos de sensibilidade fora do aplicativo Teams**</span><span class="sxs-lookup"><span data-stu-id="81b6d-175">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="81b6d-176">As alterações feitas em rótulos de sensibilidade fora do aplicativo Teams podem levar até 24 horas para refletir no aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="81b6d-176">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="81b6d-177">Isso se aplica a qualquer alteração feita para habilitar ou desabilitar rótulos de um locatário, alterações em nomes de rótulo, configurações e políticas.</span><span class="sxs-lookup"><span data-stu-id="81b6d-177">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="81b6d-178">Além disso, qualquer alteração em um rótulo feito diretamente em um grupo ou conjunto de sites do SharePoint que faz backup da equipe pode levar até 24 horas para se propagar para o aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="81b6d-178">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
