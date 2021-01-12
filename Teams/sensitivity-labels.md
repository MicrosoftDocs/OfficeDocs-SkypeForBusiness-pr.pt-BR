---
title: Rótulos de sensibilidade para o Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795766"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="f1d15-103">Rótulos de sensibilidade para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1d15-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="f1d15-104">[Os rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permitem que os administradores do Teams regulam o acesso a conteúdos organizacionais confidenciais criados durante a colaboração nas equipes.</span><span class="sxs-lookup"><span data-stu-id="f1d15-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="f1d15-105">Você pode definir rótulos de sensibilidade e suas políticas associadas no Centro [de Conformidade.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)</span><span class="sxs-lookup"><span data-stu-id="f1d15-105">You can define sensitivity labels and their associated policies in the [Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="f1d15-106">Esses rótulos e políticas são aplicados automaticamente às equipes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f1d15-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="f1d15-107">Qual é a diferença entre rótulos de sensibilidade e rótulos de classificação do Teams?</span><span class="sxs-lookup"><span data-stu-id="f1d15-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="f1d15-108">Os rótulos de sensibilidade são diferentes dos rótulos de classificação.</span><span class="sxs-lookup"><span data-stu-id="f1d15-108">Sensitivity labels are different from classification labels.</span></span> <span data-ttu-id="f1d15-109">Rótulos de classificação são cadeias de caracteres de texto que podem ser associadas a um grupo do Microsoft 365, mas não têm políticas reais associadas a eles.</span><span class="sxs-lookup"><span data-stu-id="f1d15-109">Classification labels are text strings that can be associated with a Microsoft 365 Group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="f1d15-110">Você usa rótulos de classificação como metadados para impor manualmente políticas por meio de scripts e ferramentas internas.</span><span class="sxs-lookup"><span data-stu-id="f1d15-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="f1d15-111">Por outro lado, os rótulos de sensibilidade e suas políticas são automaticamente impostos de ponta a ponta por meio de uma combinação da plataforma grupos, do Centro de Conformidade e & segurança e dos serviços do Teams.</span><span class="sxs-lookup"><span data-stu-id="f1d15-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="f1d15-112">Os rótulos de sensibilidade oferecem suporte poderoso à infraestrutura para proteger os dados confidenciais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f1d15-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="f1d15-113">Para migrar seus grupos existentes do uso de rótulos de classificação para usar rótulos de sensibilidade, use as instruções nos rótulos de classificação e sensibilidade do Azure Active Directory para grupos [do Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)</span><span class="sxs-lookup"><span data-stu-id="f1d15-113">To migrate your existing groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="f1d15-114">Criar, gerenciar e publicar rótulos de sensibilidade para o Teams</span><span class="sxs-lookup"><span data-stu-id="f1d15-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="f1d15-115">Para saber como habilitar, criar e publicar rótulos de sensibilidade para o Teams, consulte Usar rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, grupos [do Microsoft 365 e sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="f1d15-115">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="f1d15-116">Criar, atualizar e excluir rótulos de sensibilidade exigem sequenciamento cuidadoso com rótulos de publicação para os usuários.</span><span class="sxs-lookup"><span data-stu-id="f1d15-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="f1d15-117">Qualquer desvio na sequência pode resultar em erros persistentes de criação de equipe para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="f1d15-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="f1d15-118">Portanto, é fundamental fazer o seguinte <a href="#createpublishlabels"></a>ao criar e publicar <a href="#manageerrors">rótulos,</a>modificar e excluir rótulos publicados <a href="#modifydeletelabels">e</a>gerenciar erros de criação de equipe.</span><span class="sxs-lookup"><span data-stu-id="f1d15-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="f1d15-119">**Criar e publicar rótulos** <a name="createpublishlabels"></a></span><span class="sxs-lookup"><span data-stu-id="f1d15-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="f1d15-120">Quando um rótulo é criado e publicado no Centro de Conformidade, pode levar até 10 minutos para que o rótulo se torne visível na interface de criação de equipes.</span><span class="sxs-lookup"><span data-stu-id="f1d15-120">When a label is created and published in the Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="f1d15-121">Use as etapas a seguir para publicar o rótulo de todos os usuários no locatário:</span><span class="sxs-lookup"><span data-stu-id="f1d15-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="f1d15-122">Crie o rótulo e publique-o para algumas contas de usuário selecionadas no locatário.</span><span class="sxs-lookup"><span data-stu-id="f1d15-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="f1d15-123">Quando o rótulo for publicado, aguarde 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="f1d15-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="f1d15-124">Após 10 minutos, tente criar uma equipe com o rótulo usando uma das contas de usuário que têm acesso ao rótulo.</span><span class="sxs-lookup"><span data-stu-id="f1d15-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="f1d15-125">Se a equipe tiver criado com êxito na etapa 3, vá em frente e publique o rótulo para os usuários restantes no locatário.</span><span class="sxs-lookup"><span data-stu-id="f1d15-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="f1d15-126">**Modificar e excluir rótulos publicados** <a name="modifydeletelabels"></a></span><span class="sxs-lookup"><span data-stu-id="f1d15-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="f1d15-127">Excluir ou modificar o rótulo enquanto ele estiver associado a políticas de sensibilidade pode resultar em falhas de criação de equipe em todo o locatário.</span><span class="sxs-lookup"><span data-stu-id="f1d15-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="f1d15-128">Portanto, antes de excluir ou modificar um rótulo, primeiro você deve desassociar o rótulo de suas políticas associadas.</span><span class="sxs-lookup"><span data-stu-id="f1d15-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="f1d15-129">Use as etapas a seguir</span><span class="sxs-lookup"><span data-stu-id="f1d15-129">Use the following steps</span></span>  
<span data-ttu-id="f1d15-130">para excluir ou modificar um rótulo:</span><span class="sxs-lookup"><span data-stu-id="f1d15-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="f1d15-131">Remova o rótulo de todas as políticas que usam o rótulo.</span><span class="sxs-lookup"><span data-stu-id="f1d15-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="f1d15-132">Como alternativa, você também pode excluir as políticas por conta própria.</span><span class="sxs-lookup"><span data-stu-id="f1d15-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="f1d15-133">Quando o rótulo for removido das políticas ou as políticas em si são excluídas, aguarde 10 minutos antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="f1d15-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="f1d15-134">Após 10 minutos, iniciar a interface de criação de equipe e garantir que o rótulo não seja mais visível para qualquer usuário no locatário.</span><span class="sxs-lookup"><span data-stu-id="f1d15-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="f1d15-135">Agora você pode excluir ou modificar o rótulo com segurança.</span><span class="sxs-lookup"><span data-stu-id="f1d15-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="f1d15-136">**Gerenciar erros de criação de equipe** <a name="manageerrors"></a></span><span class="sxs-lookup"><span data-stu-id="f1d15-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="f1d15-137">Se a criação da equipe começar a falhar a qualquer momento durante a visualização pública, você terá duas opções:</span><span class="sxs-lookup"><span data-stu-id="f1d15-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="f1d15-138">Verifique se os rótulos de sensibilidade não são obrigatórios para qualquer usuário durante a criação da equipe.</span><span class="sxs-lookup"><span data-stu-id="f1d15-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="f1d15-139">Desativar rótulos de sensibilidade usando os scripts em [Habilitar esta visualização.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)</span><span class="sxs-lookup"><span data-stu-id="f1d15-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="f1d15-140">Observe que a configuração EnableMIPLabels deve ser definida como false da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f1d15-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="f1d15-141">Usando rótulos de sensibilidade com o Teams</span><span class="sxs-lookup"><span data-stu-id="f1d15-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="f1d15-142">Aqui estão alguns cenários de exemplo de como você pode usar rótulos de sensibilidade com o Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f1d15-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="f1d15-143">Configuração de privacidade das equipes</span><span class="sxs-lookup"><span data-stu-id="f1d15-143">Privacy setting of teams</span></span>

<span data-ttu-id="f1d15-144">Você pode criar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite que os usuários criem equipes com uma configuração de privacidade específica (pública ou privada).</span><span class="sxs-lookup"><span data-stu-id="f1d15-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="f1d15-145">Por exemplo, você cria um rótulo chamado "Confidencial &" no Centro de Conformidade e Segurança e configura o Teams para que qualquer equipe criada com esse rótulo seja uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="f1d15-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="f1d15-146">Quando um usuário cria uma nova  equipe e seleciona o rótulo Confidencial, a única opção de privacidade disponível para o usuário é **Particular**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="f1d15-147">Outras opções de privacidade, como Público e toda a organização, estão desabilitadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="f1d15-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Captura de tela do rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="f1d15-149">Da mesma forma, se o usuário selecionar **Geral** ao criar uma nova equipe, ele só poderá criar equipes públicas ou em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="f1d15-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

<span data-ttu-id="f1d15-151">Quando a equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais da equipe.</span><span class="sxs-lookup"><span data-stu-id="f1d15-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

<span data-ttu-id="f1d15-153">Um proprietário da equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, indo para a equipe e clicando em **Editar equipe.**</span><span class="sxs-lookup"><span data-stu-id="f1d15-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Captura de tela do rótulo de sensibilidade nas propriedades da equipe](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="f1d15-155">Acesso de convidados às equipes</span><span class="sxs-lookup"><span data-stu-id="f1d15-155">Guest access to teams</span></span>

<span data-ttu-id="f1d15-156">Você pode especificar se uma equipe criada com um rótulo específico permite o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="f1d15-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="f1d15-157">As equipes criadas com um rótulo que não permite o acesso de convidados estão disponíveis apenas para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f1d15-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="f1d15-158">Pessoas de fora da sua organização não podem ser adicionadas à equipe.</span><span class="sxs-lookup"><span data-stu-id="f1d15-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f1d15-159">Rótulos de sensibilidade no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1d15-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="f1d15-160">Você pode definir rótulos de sensibilidade ao criar ou editar uma equipe no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1d15-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f1d15-161">Os rótulos de sensibilidade também são  visíveis nas propriedades da equipe e na coluna Classificação, na página Gerenciar equipes do centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1d15-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="f1d15-162">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="f1d15-162">Known issues</span></span>

<span data-ttu-id="f1d15-163">**Suporte para rótulos de sensibilidade nas APIs do Teams Graph, cmdlets e modelos do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f1d15-163">**Support for sensitivity labels in Teams Graph APIs, PowerShell cmdlets and templates**</span></span>

<span data-ttu-id="f1d15-164">Atualmente, os usuários não poderão aplicar rótulos de sensibilidade em equipes criadas diretamente por meio de APIs do Graph, cmdlets do PowerShell e modelos.</span><span class="sxs-lookup"><span data-stu-id="f1d15-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, PowerShell cmdlets, and templates.</span></span>

<span data-ttu-id="f1d15-165">**Suporte para rótulos de sensibilidade em SKUs EDU do Teams**</span><span class="sxs-lookup"><span data-stu-id="f1d15-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="f1d15-166">No momento, os rótulos de sensibilidade não têm suporte para clientes que usam SKUs do Teams Education.</span><span class="sxs-lookup"><span data-stu-id="f1d15-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="f1d15-167">**Editando rótulos de sensibilidade diretamente em um conjunto de sites do SharePoint para canais privados**</span><span class="sxs-lookup"><span data-stu-id="f1d15-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="f1d15-168">Os canais privados criados em uma equipe herdam o rótulo de sensibilidade que foi aplicado em uma equipe.</span><span class="sxs-lookup"><span data-stu-id="f1d15-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="f1d15-169">Além disso, o mesmo rótulo é aplicado automaticamente no conjunto de sites do SharePoint para o canal privado.</span><span class="sxs-lookup"><span data-stu-id="f1d15-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="f1d15-170">Se um usuário atualizar diretamente o rótulo de sensibilidade em um conjunto de sites do SharePoint para um canal privado, esse rótulo não será atualizado no cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="f1d15-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="f1d15-171">Nesse cenário, os usuários continuarão a ver o rótulo de sensibilidade aplicado em uma equipe no header de canal privado.</span><span class="sxs-lookup"><span data-stu-id="f1d15-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="f1d15-172">**Tempos de propagação para alterações aplicadas a rótulos de sensibilidade fora do aplicativo Teams**</span><span class="sxs-lookup"><span data-stu-id="f1d15-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="f1d15-173">As alterações feitas em rótulos de sensibilidade fora do aplicativo Teams podem levar até 24 horas para refletir no aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="f1d15-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="f1d15-174">Isso se aplica a quaisquer alterações feitas para habilitar ou desabilitar rótulos para um locatário, alterações em nomes de rótulos, configurações e políticas.</span><span class="sxs-lookup"><span data-stu-id="f1d15-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="f1d15-175">Além disso, qualquer alteração em um rótulo feita diretamente em um grupo ou conjunto de sites do SharePoint que dê apoio à equipe pode levar até 24 horas para se propagar para o aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="f1d15-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
