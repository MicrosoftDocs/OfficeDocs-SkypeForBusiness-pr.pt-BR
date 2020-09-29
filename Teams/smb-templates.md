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
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294547"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="39756-103">Modelos de equipe integrados ao Microsoft Graph para pequenas e médias empresas</span><span class="sxs-lookup"><span data-stu-id="39756-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="39756-104">Os modelos do Microsoft Teams permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="39756-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="39756-105">Para empresas de pequeno e médio porte, os modelos podem ser especialmente poderosos, pois ajudam os administradores a implantar equipes rapidamente em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="39756-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="39756-106">Os modelos também ajudam a orientar os usuários e começar a usar o Microsoft Teams com eficiência.</span><span class="sxs-lookup"><span data-stu-id="39756-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="39756-107">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="39756-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="39756-108">Atualmente, oferecemos três modelos SMB de primeira empresa que você pode aproveitar para várias situações.</span><span class="sxs-lookup"><span data-stu-id="39756-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="39756-109">Todos os modelos criarão equipes *particulares* .</span><span class="sxs-lookup"><span data-stu-id="39756-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="39756-110">Depois de criar as equipes e estar pronto para se implantar em sua organização, você pode definir a privacidade para *toda* a organização ou *pública*, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="39756-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="39756-111">Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](get-started-with-teams-templates.md)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="39756-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="39756-112">Modelo de toda a empresa</span><span class="sxs-lookup"><span data-stu-id="39756-112">Company-Wide template</span></span>
<span data-ttu-id="39756-113">O modelo para toda a empresa destina-se à comunicação e colaboração que são relevantes para toda a empresa.</span><span class="sxs-lookup"><span data-stu-id="39756-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="39756-114">Você pode usar o canal geral para anúncios em toda a empresa, notícias do setor ou publicações executivas.</span><span class="sxs-lookup"><span data-stu-id="39756-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="39756-115">O canal de recursos humanos é um ótimo lugar para consolidar todas as atividades relacionadas a RH, como Postagens de trabalho, novos recursos de integração de funcionários, treinamento e desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="39756-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="39756-116">O canal de coisas divertidas fornece uma plataforma social para todas as postagens divertidas e divertidas.</span><span class="sxs-lookup"><span data-stu-id="39756-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="39756-117">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="39756-117">Base template type</span></span>  | <span data-ttu-id="39756-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="39756-118">baseTemplateId</span></span> | <span data-ttu-id="39756-119">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="39756-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="39756-120">SMB</span><span class="sxs-lookup"><span data-stu-id="39756-120">SMB -</span></span> <br><span data-ttu-id="39756-121">Em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="39756-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="39756-122">Canais</span><span class="sxs-lookup"><span data-stu-id="39756-122">Channels</span></span> <ul><li><span data-ttu-id="39756-123">Geral\*</span><span class="sxs-lookup"><span data-stu-id="39756-123">General\*</span></span></li><li><span data-ttu-id="39756-124">Recursos humanos\*</span><span class="sxs-lookup"><span data-stu-id="39756-124">Human Resources\*</span></span></li><li><span data-ttu-id="39756-125">Coisas divertidas\*</span><span class="sxs-lookup"><span data-stu-id="39756-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="39756-126">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="39756-126">Apps</span></span><ul><li><span data-ttu-id="39756-127">Portal da empresa (website fixado ao canal de **recursos humanos** )</span><span class="sxs-lookup"><span data-stu-id="39756-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="39756-128">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="39756-128">Team properties</span></span> <ul><li><span data-ttu-id="39756-129">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="39756-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="39756-130">\* Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="39756-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="39756-131">Para criar a equipe de toda a empresa por meio de padrões predefinidos do modelo predefinido, forneça a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="39756-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="39756-132">Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="39756-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="39756-133">Solicitação</span><span class="sxs-lookup"><span data-stu-id="39756-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="39756-134">Modelo de equipe executiva</span><span class="sxs-lookup"><span data-stu-id="39756-134">Executive Team template</span></span>

<span data-ttu-id="39756-135">O modelo de equipe executiva é ideal para criar uma equipe para que executivos da empresa se comuniquem e colaborem em iniciativas da empresa, como prioridades anuais, orçamentos fiscais, iniciativas estratégicas e principais clientes.</span><span class="sxs-lookup"><span data-stu-id="39756-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="39756-136">Este modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="39756-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="39756-137">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="39756-137">Base template type</span></span>  | <span data-ttu-id="39756-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="39756-138">baseTemplateId</span></span> | <span data-ttu-id="39756-139">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="39756-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="39756-140">SMB</span><span class="sxs-lookup"><span data-stu-id="39756-140">SMB -</span></span> <br><span data-ttu-id="39756-141">Equipe de executivos</span><span class="sxs-lookup"><span data-stu-id="39756-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="39756-142">Canais</span><span class="sxs-lookup"><span data-stu-id="39756-142">Channels</span></span> <ul><li><span data-ttu-id="39756-143">Geral\*</span><span class="sxs-lookup"><span data-stu-id="39756-143">General\*</span></span></li><li><span data-ttu-id="39756-144">Priva \*</span><span class="sxs-lookup"><span data-stu-id="39756-144">Private \*</span></span></li></ul> <span data-ttu-id="39756-145">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="39756-145">Apps</span></span><ul><li><span data-ttu-id="39756-146">OneNote (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="39756-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="39756-147">Planner (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="39756-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="39756-148">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="39756-148">Team properties</span></span> <ul><li><span data-ttu-id="39756-149">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="39756-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="39756-150">\* Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="39756-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="39756-151">Para criar a equipe de executivos, basta usar os padrões do modelo predefinido, fornecer a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="39756-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="39756-152">Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="39756-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="39756-153">Solicitação</span><span class="sxs-lookup"><span data-stu-id="39756-153">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="39756-154">Modelo de equipe departamental</span><span class="sxs-lookup"><span data-stu-id="39756-154">Departmental Team template</span></span>

<span data-ttu-id="39756-155">O modelo de equipe departamental pode ser usado para criar uma equipe para departamentos individuais ou para projetos.</span><span class="sxs-lookup"><span data-stu-id="39756-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="39756-156">O modelo de equipe de finanças é ideal para todas as postagens, anúncios e colaboração diária e comunicação dentro dos membros da equipe financeira e membros da equipe executiva, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="39756-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="39756-157">O modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos.</span><span class="sxs-lookup"><span data-stu-id="39756-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="39756-158">Também fornecemos o script abaixo para a equipe de Finanças que pode ser usada para estender o modelo para departamentos adicionais ou projetos específicos adicionando, excluindo ou editando a sua preferência.</span><span class="sxs-lookup"><span data-stu-id="39756-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="39756-159">Por exemplo, se você tiver um departamento de *marketing* , o script poderá ser adaptado renomeando-se a equipe do *departamento de finanças* ao *marketing* para criar uma nova equipe de marketing</span><span class="sxs-lookup"><span data-stu-id="39756-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="39756-160">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="39756-160">Base template type</span></span> | <span data-ttu-id="39756-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="39756-161">baseTemplateId</span></span> | <span data-ttu-id="39756-162">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="39756-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="39756-163">SMB</span><span class="sxs-lookup"><span data-stu-id="39756-163">SMB -</span></span> <br><span data-ttu-id="39756-164">Finanças</span><span class="sxs-lookup"><span data-stu-id="39756-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="39756-165">Canais</span><span class="sxs-lookup"><span data-stu-id="39756-165">Channels</span></span> <ul><li><span data-ttu-id="39756-166">Geral\*</span><span class="sxs-lookup"><span data-stu-id="39756-166">General\*</span></span></li><li><span data-ttu-id="39756-167">Priva \*</span><span class="sxs-lookup"><span data-stu-id="39756-167">Private \*</span></span></li></ul><br> <span data-ttu-id="39756-168">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="39756-168">Apps</span></span><ul><li><span data-ttu-id="39756-169">OneNote (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="39756-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="39756-170">Planner (fixado ao canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="39756-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="39756-171">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="39756-171">Team properties</span></span> <ul><li><span data-ttu-id="39756-172">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="39756-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="39756-173">\* Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="39756-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="39756-174">Para criar a equipe de finanças, basta usar os padrões do modelo predefinido, fornecer a representação JSON do objeto de equipe no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="39756-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="39756-175">Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="39756-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="39756-176">Solicitação</span><span class="sxs-lookup"><span data-stu-id="39756-176">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="39756-177">Exemplo: script de extensão de modelo de equipe financeira</span><span class="sxs-lookup"><span data-stu-id="39756-177">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="39756-178">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="39756-178">Related topics</span></span>

- [<span data-ttu-id="39756-179">Introdução aos modelos do Microsoft Teams no console de administração</span><span class="sxs-lookup"><span data-stu-id="39756-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="39756-180">Introdução aos modelos do Teams</span><span class="sxs-lookup"><span data-stu-id="39756-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="39756-181">[Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (na visualização)</span><span class="sxs-lookup"><span data-stu-id="39756-181">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

