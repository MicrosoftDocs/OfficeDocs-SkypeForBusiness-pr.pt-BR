---
title: Modelos do Teams para Pequenas e Médias Empresas criadas com o Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Use modelos predefinidos do Microsoft Teams integrados ao Microsoft Graph para criar equipes de forma rápida e fácil para pequenas e médias empresas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116989"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="8cfa8-103">Modelos do Teams integrados ao Microsoft Graph para Pequenas e Médias Empresas</span><span class="sxs-lookup"><span data-stu-id="8cfa8-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="8cfa8-104">Os modelos do Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="8cfa8-105">Para pequenas e médias empresas, os modelos podem ser especialmente poderosos, pois ajudam os administradores a implantar rapidamente o Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="8cfa8-106">Os modelos também ajudam a orientar os usuários e a começar a usar o Teams com eficiência.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="8cfa8-107">Este artigo é para você se você for responsável por planejar, implantar e gerenciar várias equipes em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="8cfa8-108">Atualmente, oferecemos três modelos SMB de primeira parte que você pode aproveitar para várias situações.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="8cfa8-109">Todos os modelos criarão *o Private* Teams.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="8cfa8-110">Depois de criar o Teams e estiver pronto para a sua organização, você poderá definir a privacidade como *Toda a* Organização ou *Público,* conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="8cfa8-111">Para saber mais sobre modelos de equipe em geral, confira [a1/10 sobre modelos do Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="8cfa8-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="8cfa8-112">Company-Wide modelo</span><span class="sxs-lookup"><span data-stu-id="8cfa8-112">Company-Wide template</span></span>
<span data-ttu-id="8cfa8-113">O Company-Wide é destinado à comunicação e colaboração relevantes para toda a empresa.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="8cfa8-114">Você pode usar o canal Geral para comunicados, notícias do setor ou postagens executivas em toda a empresa.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="8cfa8-115">O canal de Recursos Humanos é um ótimo local para consolidar todas as atividades relacionadas ao RH, como postagens de trabalho, integração, treinamento e desenvolvimento de novos funcionários.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="8cfa8-116">O canal Coisas Divertidas fornece uma plataforma social para todas as postagens aleatórias e divertidas.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="8cfa8-117">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="8cfa8-117">Base template type</span></span>  | <span data-ttu-id="8cfa8-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8cfa8-118">baseTemplateId</span></span> | <span data-ttu-id="8cfa8-119">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="8cfa8-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="8cfa8-120">SMB -</span><span class="sxs-lookup"><span data-stu-id="8cfa8-120">SMB -</span></span> <br><span data-ttu-id="8cfa8-121">Toda a empresa</span><span class="sxs-lookup"><span data-stu-id="8cfa8-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="8cfa8-122">Canais</span><span class="sxs-lookup"><span data-stu-id="8cfa8-122">Channels</span></span> <ul><li><span data-ttu-id="8cfa8-123">Geral\*</span><span class="sxs-lookup"><span data-stu-id="8cfa8-123">General\*</span></span></li><li><span data-ttu-id="8cfa8-124">Recursos Humanos\*</span><span class="sxs-lookup"><span data-stu-id="8cfa8-124">Human Resources\*</span></span></li><li><span data-ttu-id="8cfa8-125">Coisas divertidas\*</span><span class="sxs-lookup"><span data-stu-id="8cfa8-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="8cfa8-126">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="8cfa8-126">Apps</span></span><ul><li><span data-ttu-id="8cfa8-127">Portal da Empresa (Site fixado no **canal de Recursos Humanos)**</span><span class="sxs-lookup"><span data-stu-id="8cfa8-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="8cfa8-128">Propriedades de equipe</span><span class="sxs-lookup"><span data-stu-id="8cfa8-128">Team properties</span></span> <ul><li><span data-ttu-id="8cfa8-129">Visibilidade da equipe definida como Privada</span><span class="sxs-lookup"><span data-stu-id="8cfa8-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="8cfa8-130">\*Canais favoritos automaticamente</span><span class="sxs-lookup"><span data-stu-id="8cfa8-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="8cfa8-131">Para criar a equipe Company-Wide, a partir do modelo pré-definido, fornece a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="8cfa8-132">Para saber mais sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph [sobre a criação de uma Equipe](/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="8cfa8-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="8cfa8-133">Solicitação</span><span class="sxs-lookup"><span data-stu-id="8cfa8-133">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a><span data-ttu-id="8cfa8-134">Modelo de Equipe Executiva</span><span class="sxs-lookup"><span data-stu-id="8cfa8-134">Executive Team template</span></span>

<span data-ttu-id="8cfa8-135">O modelo de Equipe Executiva é ideal para criar uma equipe para executivos da empresa se comunicarem e colaborarem em iniciativas da empresa, como prioridades anuais, orçamentos fiscais, iniciativas estratégicas e clientes principais.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="8cfa8-136">Este modelo vem com um *canal privado* para convidar usuários selecionados para tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="8cfa8-137">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="8cfa8-137">Base template type</span></span>  | <span data-ttu-id="8cfa8-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8cfa8-138">baseTemplateId</span></span> | <span data-ttu-id="8cfa8-139">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="8cfa8-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="8cfa8-140">SMB -</span><span class="sxs-lookup"><span data-stu-id="8cfa8-140">SMB -</span></span> <br><span data-ttu-id="8cfa8-141">Equipe de Executivos</span><span class="sxs-lookup"><span data-stu-id="8cfa8-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="8cfa8-142">Canais</span><span class="sxs-lookup"><span data-stu-id="8cfa8-142">Channels</span></span> <ul><li><span data-ttu-id="8cfa8-143">Geral\*</span><span class="sxs-lookup"><span data-stu-id="8cfa8-143">General\*</span></span></li><li><span data-ttu-id="8cfa8-144">Private \*</span><span class="sxs-lookup"><span data-stu-id="8cfa8-144">Private \*</span></span></li></ul> <span data-ttu-id="8cfa8-145">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="8cfa8-145">Apps</span></span><ul><li><span data-ttu-id="8cfa8-146">OneNote (fixado no **canal** privado)</span><span class="sxs-lookup"><span data-stu-id="8cfa8-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="8cfa8-147">Planner (fixado no **canal** privado)</span><span class="sxs-lookup"><span data-stu-id="8cfa8-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="8cfa8-148">Propriedades de equipe</span><span class="sxs-lookup"><span data-stu-id="8cfa8-148">Team properties</span></span> <ul><li><span data-ttu-id="8cfa8-149">Visibilidade da equipe definida como Privada</span><span class="sxs-lookup"><span data-stu-id="8cfa8-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="8cfa8-150">\*Canais favoritos automaticamente</span><span class="sxs-lookup"><span data-stu-id="8cfa8-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="8cfa8-151">Para criar a equipe Executivos, a partir do modelo pré-definido, fornece a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="8cfa8-152">Para saber mais sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph [sobre a criação de uma Equipe](/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="8cfa8-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="8cfa8-153">Solicitação</span><span class="sxs-lookup"><span data-stu-id="8cfa8-153">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="8cfa8-154">Modelo de equipe de departamento</span><span class="sxs-lookup"><span data-stu-id="8cfa8-154">Departmental Team template</span></span>

<span data-ttu-id="8cfa8-155">O modelo de equipe departmental pode ser usado para criar uma equipe para departamentos individuais ou para projetos.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="8cfa8-156">O modelo de equipe de Finanças é ideal para todas as postagens, comunicados e colaboração diária e comunicação dentro dos membros da equipe de Finanças e membros da equipe executiva, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="8cfa8-157">O modelo vem com um *canal Privado* para convidar usuários selecionados para tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="8cfa8-158">Também fornecemos o script abaixo para a equipe de Finanças que pode ser usado para estender o modelo a departamentos adicionais ou projetos específicos adicionais adicionando, excluindo ou editando ao seu gosto.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="8cfa8-159">Por exemplo, se você tiver um departamento de *Marketing,* o script poderá ser adaptado renomeando a equipe de *Finanças* para *Marketing* para criar uma nova equipe de Marketing</span><span class="sxs-lookup"><span data-stu-id="8cfa8-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="8cfa8-160">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="8cfa8-160">Base template type</span></span> | <span data-ttu-id="8cfa8-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8cfa8-161">baseTemplateId</span></span> | <span data-ttu-id="8cfa8-162">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="8cfa8-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="8cfa8-163">SMB -</span><span class="sxs-lookup"><span data-stu-id="8cfa8-163">SMB -</span></span> <br><span data-ttu-id="8cfa8-164">Finanças</span><span class="sxs-lookup"><span data-stu-id="8cfa8-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="8cfa8-165">Canais</span><span class="sxs-lookup"><span data-stu-id="8cfa8-165">Channels</span></span> <ul><li><span data-ttu-id="8cfa8-166">Geral\*</span><span class="sxs-lookup"><span data-stu-id="8cfa8-166">General\*</span></span></li><li><span data-ttu-id="8cfa8-167">Private \*</span><span class="sxs-lookup"><span data-stu-id="8cfa8-167">Private \*</span></span></li></ul><br> <span data-ttu-id="8cfa8-168">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="8cfa8-168">Apps</span></span><ul><li><span data-ttu-id="8cfa8-169">OneNote (fixado no **canal** privado)</span><span class="sxs-lookup"><span data-stu-id="8cfa8-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="8cfa8-170">Planner (fixado no **canal** privado)</span><span class="sxs-lookup"><span data-stu-id="8cfa8-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="8cfa8-171">Propriedades de equipe</span><span class="sxs-lookup"><span data-stu-id="8cfa8-171">Team properties</span></span> <ul><li><span data-ttu-id="8cfa8-172">Visibilidade da equipe definida como Privada</span><span class="sxs-lookup"><span data-stu-id="8cfa8-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="8cfa8-173">\*Canais favoritos automaticamente</span><span class="sxs-lookup"><span data-stu-id="8cfa8-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="8cfa8-174">Para criar a equipe de Finanças, a partir do modelo pré-definido, fornece a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="8cfa8-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="8cfa8-175">Para saber mais sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph [sobre a criação de uma Equipe](/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="8cfa8-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="8cfa8-176">Solicitação</span><span class="sxs-lookup"><span data-stu-id="8cfa8-176">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="8cfa8-177">Exemplo: script de extensão do modelo de equipe de finanças</span><span class="sxs-lookup"><span data-stu-id="8cfa8-177">Example: Finance Team template extension script</span></span>

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a><span data-ttu-id="8cfa8-178">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8cfa8-178">Related topics</span></span>

- [<span data-ttu-id="8cfa8-179">Começar a usar modelos do Teams no console de administração</span><span class="sxs-lookup"><span data-stu-id="8cfa8-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="8cfa8-180">Introdução aos modelos do Teams</span><span class="sxs-lookup"><span data-stu-id="8cfa8-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="8cfa8-181">[Criar equipe](/graph/api/team-post?view=graph-rest-beta) (na visualização)</span><span class="sxs-lookup"><span data-stu-id="8cfa8-181">[Create team](/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>