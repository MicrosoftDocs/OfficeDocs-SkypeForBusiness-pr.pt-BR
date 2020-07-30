---
title: Modelos de equipe para pequenas e médias empresas criadas com o Microsoft Graph
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
description: Use os modelos predefinidos do Microsoft Teams incorporados ao Microsoft Graph para criar com rapidez e facilidade as equipes para pequenas e médias empresas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9807e7f3694731af398abd83189698420ec36b8a
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506144"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="9ffbc-103">Modelos de equipe integrados ao Microsoft Graph para pequenas e médias empresas</span><span class="sxs-lookup"><span data-stu-id="9ffbc-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="9ffbc-104">Os modelos do Microsoft Teams permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="9ffbc-105">Para empresas de pequeno e médio porte, os modelos podem ser especialmente poderosos, pois ajudam os administradores a implantar equipes rapidamente em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="9ffbc-106">Os modelos também ajudam a orientar os usuários e começar a usar o Microsoft Teams com eficiência.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="9ffbc-107">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="9ffbc-108">Atualmente, oferecemos três modelos SMB de primeira empresa que você pode aproveitar para várias situações.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="9ffbc-109">Todos os modelos criarão equipes *particulares* .</span><span class="sxs-lookup"><span data-stu-id="9ffbc-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="9ffbc-110">Depois de criar as equipes e se preparar para a sua organização, você pode definir a privacidade para *toda* a organização ou *pública*, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-110">Once you have created the Teams and are ready to roll-out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="9ffbc-111">Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](get-started-with-teams-templates.md)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-111">To learn more about team templates in general, please see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="9ffbc-112">Modelo de toda a empresa</span><span class="sxs-lookup"><span data-stu-id="9ffbc-112">Company-Wide template</span></span>
<span data-ttu-id="9ffbc-113">O modelo para toda a empresa destina-se à comunicação e colaboração que são relevantes para toda a empresa.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="9ffbc-114">Você pode usar o canal geral para anúncios em toda a empresa, notícias do setor ou publicações executivas.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="9ffbc-115">O canal de recursos humanos é um ótimo lugar para consolidar todas as atividades relacionadas a RH, como Postagens de trabalho, novos recursos de integração de funcionários, treinamento e desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training and development.</span></span> <span data-ttu-id="9ffbc-116">O canal de coisas divertidas fornece uma plataforma social para todas as postagens divertidas e divertidas.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="9ffbc-117">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="9ffbc-117">Base template type</span></span>  | <span data-ttu-id="9ffbc-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9ffbc-118">baseTemplateId</span></span> | <span data-ttu-id="9ffbc-119">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="9ffbc-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="9ffbc-120">SMB</span><span class="sxs-lookup"><span data-stu-id="9ffbc-120">SMB -</span></span> <br><span data-ttu-id="9ffbc-121">Em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="9ffbc-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="9ffbc-122">Canais</span><span class="sxs-lookup"><span data-stu-id="9ffbc-122">Channels</span></span> <ul><li><span data-ttu-id="9ffbc-123">Geral\*</span><span class="sxs-lookup"><span data-stu-id="9ffbc-123">General\*</span></span></li><li><span data-ttu-id="9ffbc-124">Recursos humanos\*</span><span class="sxs-lookup"><span data-stu-id="9ffbc-124">Human Resources\*</span></span></li><li><span data-ttu-id="9ffbc-125">Coisas divertidas\*</span><span class="sxs-lookup"><span data-stu-id="9ffbc-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="9ffbc-126">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="9ffbc-126">Apps</span></span><ul><li><span data-ttu-id="9ffbc-127">Portal da empresa (website fixado ao canal de **recursos humanos** )</span><span class="sxs-lookup"><span data-stu-id="9ffbc-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="9ffbc-128">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="9ffbc-128">Team properties</span></span> <ul><li><span data-ttu-id="9ffbc-129">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="9ffbc-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="9ffbc-130">\* Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="9ffbc-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="9ffbc-131">Para criar a equipe de toda a empresa por meio de padrões predefinidos do modelo predefinido, forneça a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="9ffbc-132">Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="9ffbc-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="9ffbc-133">Solicitação</span><span class="sxs-lookup"><span data-stu-id="9ffbc-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="9ffbc-134">Modelo de equipe executiva</span><span class="sxs-lookup"><span data-stu-id="9ffbc-134">Executive Team template</span></span>

<span data-ttu-id="9ffbc-135">O modelo de equipe executiva é ideal para criar uma equipe para que executivos da empresa se comuniquem e colaborem em iniciativas da empresa, como prioridades anuais, orçamentos fiscais, iniciativas estratégicas, principais clientes, etc. Este modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, top clients, etc. This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="9ffbc-136">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="9ffbc-136">Base template type</span></span>  | <span data-ttu-id="9ffbc-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9ffbc-137">baseTemplateId</span></span> | <span data-ttu-id="9ffbc-138">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="9ffbc-138">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="9ffbc-139">SMB</span><span class="sxs-lookup"><span data-stu-id="9ffbc-139">SMB -</span></span> <br><span data-ttu-id="9ffbc-140">Equipe de executivos</span><span class="sxs-lookup"><span data-stu-id="9ffbc-140">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="9ffbc-141">Canais</span><span class="sxs-lookup"><span data-stu-id="9ffbc-141">Channels</span></span> <ul><li><span data-ttu-id="9ffbc-142">Geral\*</span><span class="sxs-lookup"><span data-stu-id="9ffbc-142">General\*</span></span></li><li><span data-ttu-id="9ffbc-143">Priva\*</span><span class="sxs-lookup"><span data-stu-id="9ffbc-143">Private \*</span></span></li></ul> <span data-ttu-id="9ffbc-144">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="9ffbc-144">Apps</span></span><ul><li><span data-ttu-id="9ffbc-145">OneNote (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="9ffbc-145">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="9ffbc-146">Planner (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="9ffbc-146">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="9ffbc-147">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="9ffbc-147">Team properties</span></span> <ul><li><span data-ttu-id="9ffbc-148">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="9ffbc-148">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="9ffbc-149">\* Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="9ffbc-149">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="9ffbc-150">Para criar a equipe de executivos, basta usar os padrões do modelo predefinido, fornecer a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-150">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="9ffbc-151">Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="9ffbc-151">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="9ffbc-152">Solicitação</span><span class="sxs-lookup"><span data-stu-id="9ffbc-152">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="9ffbc-153">Modelo de equipe departamental</span><span class="sxs-lookup"><span data-stu-id="9ffbc-153">Departmental Team template</span></span>

<span data-ttu-id="9ffbc-154">O modelo de equipe departamental pode ser usado para criar uma equipe para departamentos individuais ou para projetos.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-154">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="9ffbc-155">O modelo de equipe de finanças é ideal para todas as postagens, anúncios e colaboração diária e comunicação dentro dos membros da equipe de Finanças (e membros da equipe executiva, conforme apropriado).</span><span class="sxs-lookup"><span data-stu-id="9ffbc-155">The Finance team template is ideal for all posts, announcements and daily collaboration and communication within the Finance team members (and executive team members as appropriate).</span></span> <span data-ttu-id="9ffbc-156">O modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-156">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="9ffbc-157">Também fornecemos o script a seguir para a equipe de Finanças que pode ser usada para estender o modelo para departamentos adicionais ou projetos específicos adicionando, excluindo ou editando a sua preferência.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-157">We also provide the script below for the Finance team which can be used to extend the template to additional departments or specific projects by adding, deleting from or editing to your liking.</span></span> <span data-ttu-id="9ffbc-158">Por exemplo, se você tiver um departamento de *marketing* , o script poderá ser adaptado renomeando-se a equipe do *departamento de finanças* ao *marketing* para criar uma nova equipe de marketing</span><span class="sxs-lookup"><span data-stu-id="9ffbc-158">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="9ffbc-159">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="9ffbc-159">Base template type</span></span> | <span data-ttu-id="9ffbc-160">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9ffbc-160">baseTemplateId</span></span> | <span data-ttu-id="9ffbc-161">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="9ffbc-161">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="9ffbc-162">SMB</span><span class="sxs-lookup"><span data-stu-id="9ffbc-162">SMB -</span></span> <br><span data-ttu-id="9ffbc-163">Finanças</span><span class="sxs-lookup"><span data-stu-id="9ffbc-163">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="9ffbc-164">Canais</span><span class="sxs-lookup"><span data-stu-id="9ffbc-164">Channels</span></span> <ul><li><span data-ttu-id="9ffbc-165">Geral\*</span><span class="sxs-lookup"><span data-stu-id="9ffbc-165">General\*</span></span></li><li><span data-ttu-id="9ffbc-166">Priva\*</span><span class="sxs-lookup"><span data-stu-id="9ffbc-166">Private \*</span></span></li></ul><br> <span data-ttu-id="9ffbc-167">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="9ffbc-167">Apps</span></span><ul><li><span data-ttu-id="9ffbc-168">OneNote (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="9ffbc-168">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="9ffbc-169">Planner (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="9ffbc-169">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="9ffbc-170">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="9ffbc-170">Team properties</span></span> <ul><li><span data-ttu-id="9ffbc-171">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="9ffbc-171">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="9ffbc-172">\* Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="9ffbc-172">\*Auto-favorited channels</span></span>

<span data-ttu-id="9ffbc-173">Para criar a equipe de finanças, basta usar os padrões do modelo predefinido, fornecer a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9ffbc-173">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="9ffbc-174">Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="9ffbc-174">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="9ffbc-175">Solicitação</span><span class="sxs-lookup"><span data-stu-id="9ffbc-175">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="9ffbc-176">Exemplo: script de extensão de modelo de equipe financeira</span><span class="sxs-lookup"><span data-stu-id="9ffbc-176">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="9ffbc-177">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9ffbc-177">Related topics</span></span>

- [<span data-ttu-id="9ffbc-178">Introdução aos modelos do Teams</span><span class="sxs-lookup"><span data-stu-id="9ffbc-178">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="9ffbc-179">[Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (na visualização)</span><span class="sxs-lookup"><span data-stu-id="9ffbc-179">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

