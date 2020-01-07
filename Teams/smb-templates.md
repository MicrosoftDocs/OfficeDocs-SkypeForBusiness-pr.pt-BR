---
title: Comece a usar os modelos do teams para pequenas e médias empresas
author: kenwith
ms.author: kenwith
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Comece a usar os modelos do teams para pequenas e médias empresas
ms.openlocfilehash: 3ca5e78f3a61f1e272960dc1d7338bd06f81d4c6
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952764"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a><span data-ttu-id="07c12-103">Comece a usar os modelos do teams para pequenas e médias empresas</span><span class="sxs-lookup"><span data-stu-id="07c12-103">Get started with Teams templates for Small and Medium Businesses</span></span>

<span data-ttu-id="07c12-104">Os modelos do Microsoft Teams permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="07c12-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="07c12-105">Para empresas de pequeno e médio porte, os modelos podem ser especialmente poderosos, pois ajudam os administradores a implantar equipes rapidamente em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="07c12-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="07c12-106">Os modelos também ajudam a orientar os usuários e começar a usar o Microsoft Teams com eficiência.</span><span class="sxs-lookup"><span data-stu-id="07c12-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="07c12-107">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="07c12-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="07c12-108">Atualmente, oferecemos três modelos SMB de primeira festa que você pode aproveitar para várias situações.</span><span class="sxs-lookup"><span data-stu-id="07c12-108">We currently offer three first party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="07c12-109">Todos os modelos criarão equipes *particulares* .</span><span class="sxs-lookup"><span data-stu-id="07c12-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="07c12-110">Depois de criar as equipes e se preparar para a sua organização, você pode definir a privacidade para *toda* a organização ou *pública*, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="07c12-110">Once you have created the Teams and are ready to roll-out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="07c12-111">Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](get-started-with-teams-templates.md)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="07c12-111">To learn more about team templates in general, please see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="07c12-112">Modelo de toda a empresa</span><span class="sxs-lookup"><span data-stu-id="07c12-112">Company-Wide template</span></span>
<span data-ttu-id="07c12-113">O modelo para toda a empresa destina-se à comunicação e colaboração que são relevantes para toda a empresa.</span><span class="sxs-lookup"><span data-stu-id="07c12-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="07c12-114">Você pode usar o canal geral para anúncios em toda a empresa, notícias do setor ou publicações executivas.</span><span class="sxs-lookup"><span data-stu-id="07c12-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="07c12-115">O canal de recursos humanos é um ótimo lugar para consolidar todas as atividades relacionadas a RH, como Postagens de trabalho, novos recursos de integração de funcionários, treinamento e desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="07c12-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training and development.</span></span> <span data-ttu-id="07c12-116">O canal de coisas divertidas fornece uma plataforma social para todas as postagens divertidas e divertidas.</span><span class="sxs-lookup"><span data-stu-id="07c12-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="07c12-117">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="07c12-117">Base template type</span></span>  | <span data-ttu-id="07c12-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="07c12-118">baseTemplateId</span></span> | <span data-ttu-id="07c12-119">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="07c12-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="07c12-120">SMB</span><span class="sxs-lookup"><span data-stu-id="07c12-120">SMB -</span></span> <br><span data-ttu-id="07c12-121">Em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="07c12-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="07c12-122">Canais</span><span class="sxs-lookup"><span data-stu-id="07c12-122">Channels</span></span> <ul><li><span data-ttu-id="07c12-123">Geral\*</span><span class="sxs-lookup"><span data-stu-id="07c12-123">General\*</span></span></li><li><span data-ttu-id="07c12-124">Recursos humanos\*</span><span class="sxs-lookup"><span data-stu-id="07c12-124">Human Resources\*</span></span></li><li><span data-ttu-id="07c12-125">Coisas divertidas\*</span><span class="sxs-lookup"><span data-stu-id="07c12-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="07c12-126">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="07c12-126">Apps</span></span><ul><li><span data-ttu-id="07c12-127">Portal da empresa (website fixado ao canal de **recursos humanos** )</span><span class="sxs-lookup"><span data-stu-id="07c12-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="07c12-128">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="07c12-128">Team properties</span></span> <ul><li><span data-ttu-id="07c12-129">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="07c12-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="07c12-130">\* Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="07c12-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="07c12-131">Para criar a equipe de toda a empresa por meio de padrões predefinidos do modelo predefinido, forneça a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="07c12-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="07c12-132">Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="07c12-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="07c12-133">Solicitação</span><span class="sxs-lookup"><span data-stu-id="07c12-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="07c12-134">Modelo de equipe executiva</span><span class="sxs-lookup"><span data-stu-id="07c12-134">Executive Team template</span></span>

<span data-ttu-id="07c12-135">O modelo de equipe executiva é ideal para criar uma equipe para que executivos da empresa se comuniquem e colaborem em iniciativas da empresa, como prioridades anuais, orçamentos fiscais, iniciativas estratégicas, principais clientes, etc. Este modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="07c12-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, top clients, etc. This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="07c12-136">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="07c12-136">Base template type</span></span>  | <span data-ttu-id="07c12-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="07c12-137">baseTemplateId</span></span> | <span data-ttu-id="07c12-138">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="07c12-138">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="07c12-139">SMB</span><span class="sxs-lookup"><span data-stu-id="07c12-139">SMB -</span></span> <br><span data-ttu-id="07c12-140">Equipe de executivos</span><span class="sxs-lookup"><span data-stu-id="07c12-140">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="07c12-141">Canais</span><span class="sxs-lookup"><span data-stu-id="07c12-141">Channels</span></span> <ul><li><span data-ttu-id="07c12-142">Geral\*</span><span class="sxs-lookup"><span data-stu-id="07c12-142">General\*</span></span></li><li><span data-ttu-id="07c12-143">Priva\*</span><span class="sxs-lookup"><span data-stu-id="07c12-143">Private \*</span></span></li></ul> <span data-ttu-id="07c12-144">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="07c12-144">Apps</span></span><ul><li><span data-ttu-id="07c12-145">OneNote (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="07c12-145">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="07c12-146">Planner (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="07c12-146">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="07c12-147">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="07c12-147">Team properties</span></span> <ul><li><span data-ttu-id="07c12-148">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="07c12-148">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="07c12-149">\* Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="07c12-149">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="07c12-150">Para criar a equipe de executivos, basta usar os padrões do modelo predefinido, fornecer a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="07c12-150">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="07c12-151">Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="07c12-151">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="07c12-152">Solicitação</span><span class="sxs-lookup"><span data-stu-id="07c12-152">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company’s leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="07c12-153">Modelo de equipe departamental</span><span class="sxs-lookup"><span data-stu-id="07c12-153">Departmental Team template</span></span>

<span data-ttu-id="07c12-154">O modelo de equipe departamental pode ser usado para criar uma equipe para departamentos individuais ou para projetos.</span><span class="sxs-lookup"><span data-stu-id="07c12-154">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="07c12-155">O modelo de equipe de finanças é ideal para todas as postagens, anúncios e colaboração diária e comunicação dentro dos membros da equipe de Finanças (e membros da equipe executiva, conforme apropriado).</span><span class="sxs-lookup"><span data-stu-id="07c12-155">The Finance team template is ideal for all posts, announcements and daily collaboration and communication within the Finance team members (and executive team members as appropriate).</span></span> <span data-ttu-id="07c12-156">O modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="07c12-156">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="07c12-157">Também fornecemos o script a seguir para a equipe de Finanças que pode ser usada para estender o modelo para departamentos adicionais ou projetos específicos adicionando, excluindo ou editando a sua preferência.</span><span class="sxs-lookup"><span data-stu-id="07c12-157">We also provide the script below for the Finance team which can be used to extend the template to additional departments or specific projects by adding, deleting from or editing to your liking.</span></span> <span data-ttu-id="07c12-158">Por exemplo, se você tiver um departamento de *marketing* , o script poderá ser adaptado renomeando-se a equipe do *departamento de finanças* ao *marketing* para criar uma nova equipe de marketing</span><span class="sxs-lookup"><span data-stu-id="07c12-158">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="07c12-159">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="07c12-159">Base template type</span></span> | <span data-ttu-id="07c12-160">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="07c12-160">baseTemplateId</span></span> | <span data-ttu-id="07c12-161">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="07c12-161">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="07c12-162">SMB</span><span class="sxs-lookup"><span data-stu-id="07c12-162">SMB -</span></span> <br><span data-ttu-id="07c12-163">Finanças</span><span class="sxs-lookup"><span data-stu-id="07c12-163">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="07c12-164">Canais</span><span class="sxs-lookup"><span data-stu-id="07c12-164">Channels</span></span> <ul><li><span data-ttu-id="07c12-165">Geral\*</span><span class="sxs-lookup"><span data-stu-id="07c12-165">General\*</span></span></li><li><span data-ttu-id="07c12-166">Priva\*</span><span class="sxs-lookup"><span data-stu-id="07c12-166">Private \*</span></span></li></ul><br> <span data-ttu-id="07c12-167">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="07c12-167">Apps</span></span><ul><li><span data-ttu-id="07c12-168">OneNote (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="07c12-168">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="07c12-169">Planner (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="07c12-169">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="07c12-170">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="07c12-170">Team properties</span></span> <ul><li><span data-ttu-id="07c12-171">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="07c12-171">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="07c12-172">\* Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="07c12-172">\*Auto-favorited channels</span></span>

<span data-ttu-id="07c12-173">Para criar a equipe de finanças, basta usar os padrões do modelo predefinido, fornecer a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="07c12-173">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="07c12-174">Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="07c12-174">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="07c12-175">Solicitação</span><span class="sxs-lookup"><span data-stu-id="07c12-175">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="07c12-176">Exemplo: script de extensão de modelo de equipe financeira</span><span class="sxs-lookup"><span data-stu-id="07c12-176">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="07c12-177">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="07c12-177">Related topics</span></span>

- [<span data-ttu-id="07c12-178">Introdução aos modelos do Teams</span><span class="sxs-lookup"><span data-stu-id="07c12-178">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="07c12-179">[Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (na visualização)</span><span class="sxs-lookup"><span data-stu-id="07c12-179">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

