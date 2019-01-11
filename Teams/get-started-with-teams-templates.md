---
title: Introdução ao modelos de equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Saiba como usar modelos de equipes para criar uma equipe com canais predefinidos.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801460"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="05b99-103">Introdução ao modelos de equipes</span><span class="sxs-lookup"><span data-stu-id="05b99-103">Get started with Teams templates</span></span> 

<span data-ttu-id="05b99-104">Modelos de equipes são pré-criados definições da estrutura de uma equipe Projetado levando em consideração uma necessidade comercial ou projeto.</span><span class="sxs-lookup"><span data-stu-id="05b99-104">Teams templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="05b99-105">Você pode usar modelos de equipes para criar rapidamente os espaços de colaboração avançada com canais para tópicos diferentes e pré-instalação de aplicativos seja obtida dos planejamentos nos serviços e conteúdo de missão crítica.</span><span class="sxs-lookup"><span data-stu-id="05b99-105">You can use Teams templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="05b99-106">Os modelos de equipes fornecem uma estrutura de equipe predefinidas que pode ajudá-lo a criar facilmente equipes consistentes em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="05b99-106">Teams templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="05b99-107">Neste artigo, vamos explicar as propriedades que podem ser definidas nos modelos, qual modelo base tipos forem, e como você pode usar algumas solicitações para criar uma equipe a partir de um modelo de exemplo.</span><span class="sxs-lookup"><span data-stu-id="05b99-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="05b99-108">Este artigo é para você, se você estiver:</span><span class="sxs-lookup"><span data-stu-id="05b99-108">This article is for you if you're:</span></span>

- <span data-ttu-id="05b99-109">Responsável pelo planejamento, implantação e gerenciamento de várias equipes em toda a organização</span><span class="sxs-lookup"><span data-stu-id="05b99-109">Responsible for planning, deploying, and managing multiple teams across your organization</span></span><br>
- <span data-ttu-id="05b99-110">Um desenvolvedor querer criar programaticamente uma equipe com aplicativos e canais predefinidos</span><span class="sxs-lookup"><span data-stu-id="05b99-110">A developer wanting to programmatically create a team with predefined channels and apps</span></span> 

## <a name="teams-template-capabilities"></a><span data-ttu-id="05b99-111">Recursos do modelo de equipes</span><span class="sxs-lookup"><span data-stu-id="05b99-111">Teams template capabilities</span></span>

<span data-ttu-id="05b99-112">A maioria das propriedades em uma equipe são incluídas e suportado por modelos.</span><span class="sxs-lookup"><span data-stu-id="05b99-112">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="05b99-113">Mas há algumas propriedades e recursos que não são suportados no momento.</span><span class="sxs-lookup"><span data-stu-id="05b99-113">But there are a few properties and features that are not currently supported.</span></span> <span data-ttu-id="05b99-114">A tabela a seguir fornece um resumo rápido o que está incluído e o que não está incluído nos modelos de equipes.</span><span class="sxs-lookup"><span data-stu-id="05b99-114">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="05b99-115">**Propriedades da equipe compatíveis com os modelos de equipes**</span><span class="sxs-lookup"><span data-stu-id="05b99-115">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="05b99-116">**Propriedades da equipe ainda não é suportadas por modelos de equipes**</span><span class="sxs-lookup"><span data-stu-id="05b99-116">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="05b99-117">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="05b99-117">Base template type</span></span> | <span data-ttu-id="05b99-118">Associação de equipe</span><span class="sxs-lookup"><span data-stu-id="05b99-118">Team membership</span></span> |
| <span data-ttu-id="05b99-119">Nome da equipe</span><span class="sxs-lookup"><span data-stu-id="05b99-119">Team name</span></span> | <span data-ttu-id="05b99-120">Imagem de equipe</span><span class="sxs-lookup"><span data-stu-id="05b99-120">Team picture</span></span> |
| <span data-ttu-id="05b99-121">Descrição da equipe</span><span class="sxs-lookup"><span data-stu-id="05b99-121">Team description</span></span> | <span data-ttu-id="05b99-122">Configurações de canal</span><span class="sxs-lookup"><span data-stu-id="05b99-122">Channel settings</span></span> |
| <span data-ttu-id="05b99-123">Visibilidade de equipe (pública ou privada)</span><span class="sxs-lookup"><span data-stu-id="05b99-123">Team visibility (public or private)</span></span> | <span data-ttu-id="05b99-124">Conectores</span><span class="sxs-lookup"><span data-stu-id="05b99-124">Connectors</span></span> |
| <span data-ttu-id="05b99-125">Configurações de equipe (por exemplo, o membro, o convidado, @ menções)</span><span class="sxs-lookup"><span data-stu-id="05b99-125">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="05b99-126">Arquivos e conteúdo</span><span class="sxs-lookup"><span data-stu-id="05b99-126">Files and content</span></span> |
| <span data-ttu-id="05b99-127">Autofavorito canal</span><span class="sxs-lookup"><span data-stu-id="05b99-127">Auto-favorite channel</span></span> | |
| <span data-ttu-id="05b99-128">Aplicativo instalado</span><span class="sxs-lookup"><span data-stu-id="05b99-128">Installed app</span></span> | |
| <span data-ttu-id="05b99-129">Guias fixados</span><span class="sxs-lookup"><span data-stu-id="05b99-129">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="05b99-130">Podemos vai ser adicionando mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique novamente para obter as informações mais atualizadas sobre propriedades com suporte.</span><span class="sxs-lookup"><span data-stu-id="05b99-130">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="05b99-131">Quais são os tipos de modelo base?</span><span class="sxs-lookup"><span data-stu-id="05b99-131">What are base template types?</span></span>

<span data-ttu-id="05b99-132">Tipos de modelo base são modelos especiais que a Microsoft criou para setores específicos.</span><span class="sxs-lookup"><span data-stu-id="05b99-132">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="05b99-133">Esses modelos base geralmente contêm proprietários aplicativos que não estão disponíveis nas propriedades do repositório e a equipe que ainda não são aceitas individualmente nos modelos de equipes.</span><span class="sxs-lookup"><span data-stu-id="05b99-133">These base templates often contain proprietary apps that aren't available in the store and team properties that are not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="05b99-134">Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais com propriedades adicionais que você gostaria de especificar.</span><span class="sxs-lookup"><span data-stu-id="05b99-134">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="05b99-135">Mas alguns tipos de modelo base contém propriedades que não podem ser substituídas.</span><span class="sxs-lookup"><span data-stu-id="05b99-135">But some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="05b99-136">Por padrão, o modelo base é definido para o **padrão** que não contenha nenhum apps proprietárias adicionais ou propriedades especiais.</span><span class="sxs-lookup"><span data-stu-id="05b99-136">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="05b99-137">Abaixo é a lista atual de tipos de base modelos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="05b99-137">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="05b99-138">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="05b99-138">Base template type</span></span> | <span data-ttu-id="05b99-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="05b99-139">baseTemplateId</span></span> | <span data-ttu-id="05b99-140">Aplicativos de proprietário do modelo base e propriedades especiais</span><span class="sxs-lookup"><span data-stu-id="05b99-140">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="05b99-141">Standard</span><span class="sxs-lookup"><span data-stu-id="05b99-141">Standard</span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | <span data-ttu-id="05b99-142">Não há aplicativos adicionais e propriedades</span><span class="sxs-lookup"><span data-stu-id="05b99-142">No additional apps and properties</span></span> |
| <span data-ttu-id="05b99-143">Educação-</span><span class="sxs-lookup"><span data-stu-id="05b99-143">Education -</span></span> <br><span data-ttu-id="05b99-144">Equipe de classe<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="05b99-144">Class team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | <span data-ttu-id="05b99-145">Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="05b99-145">Apps:</span></span><ul><li><span data-ttu-id="05b99-146">Bloco de anotações de classe do OneNote (fixados a guia **Geral** )</span><span class="sxs-lookup"><span data-stu-id="05b99-146">OneNote Class Notebook (pinned to the **General** tab)</span></span> </li><li><span data-ttu-id="05b99-147">Aplicativo de atribuições (fixado a guia **Geral** )</span><span class="sxs-lookup"><span data-stu-id="05b99-147">Assignments app (pinned to the **General** tab)</span></span></li></ul> <span data-ttu-id="05b99-148">Propriedades de equipe:</span><span class="sxs-lookup"><span data-stu-id="05b99-148">Team properties:</span></span><ul><li><span data-ttu-id="05b99-149">Visibilidade da equipe é definido como **HiddenMembership** (não pode ser substituída)</span><span class="sxs-lookup"><span data-stu-id="05b99-149">Team visibility set to **HiddenMembership** (cannot be overridden)</span></span></li></ul> |
| <span data-ttu-id="05b99-150">Educação-</span><span class="sxs-lookup"><span data-stu-id="05b99-150">Education -</span></span><br><span data-ttu-id="05b99-151">A equipe da equipe<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="05b99-151">Staff team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | <span data-ttu-id="05b99-152">Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="05b99-152">Apps:</span></span><ul><li><span data-ttu-id="05b99-153">Bloco de anotações de equipe do OneNote (fixados a guia **Geral** )</span><span class="sxs-lookup"><span data-stu-id="05b99-153">OneNote Staff Notebook (pinned to the **General** tab)</span></span></li></ul> |
|<span data-ttu-id="05b99-154">Educação-</span><span class="sxs-lookup"><span data-stu-id="05b99-154">Education -</span></span><br><span data-ttu-id="05b99-155">Equipe PLC</span><span class="sxs-lookup"><span data-stu-id="05b99-155">PLC team</span></span> |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | <span data-ttu-id="05b99-156">Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="05b99-156">Apps:</span></span><ul><li><span data-ttu-id="05b99-157">Anotações do OneNote PLC (fixados a guia **Geral** )</span><span class="sxs-lookup"><span data-stu-id="05b99-157">OneNote PLC Notebook (pinned to the **General** tab)</span></span></ul></li>|
|||

<span data-ttu-id="05b99-158">Publicação de <sup>1</sup> em outubro de 2018 tardia</span><span class="sxs-lookup"><span data-stu-id="05b99-158"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="05b99-159">Serão adicionados mais modelo base digita em futuras versões do Microsoft Teams, para verificar novamente as informações mais atualizadas sobre suporte a propriedades.</span><span class="sxs-lookup"><span data-stu-id="05b99-159">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="05b99-160">Exemplos</span><span class="sxs-lookup"><span data-stu-id="05b99-160">Examples</span></span> 

<span data-ttu-id="05b99-161">Você pode iniciar usando um modelo para criar uma equipe usando a [API do Microsoft Graph](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="05b99-161">You can start using a template to create a team by using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="05b99-162">Crie uma equipe a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="05b99-162">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="05b99-163">Solicitações</span><span class="sxs-lookup"><span data-stu-id="05b99-163">Requests</span></span>

<span data-ttu-id="05b99-164">**Solicitação para criar uma equipe com o modelo base standard**</span><span class="sxs-lookup"><span data-stu-id="05b99-164">**Request to create a team with the standard base template**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

<span data-ttu-id="05b99-165">**Solicitação para criar uma equipe com um canal extra e invalidar membros excluam canais**</span><span class="sxs-lookup"><span data-stu-id="05b99-165">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

<span data-ttu-id="05b99-166">**Solicitação para criar uma equipe com todas as propriedades com suporte**</span><span class="sxs-lookup"><span data-stu-id="05b99-166">**Request to create a team with all supported properties**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a><span data-ttu-id="05b99-167">Obter o status</span><span class="sxs-lookup"><span data-stu-id="05b99-167">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="05b99-168">Solicitação</span><span class="sxs-lookup"><span data-stu-id="05b99-168">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="05b99-169">Resposta</span><span class="sxs-lookup"><span data-stu-id="05b99-169">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="05b99-170">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="05b99-170">Related topics</span></span>

- <span data-ttu-id="05b99-171">[Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (no modo de visualização)</span><span class="sxs-lookup"><span data-stu-id="05b99-171">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>
- [<span data-ttu-id="05b99-172">Nova equipe</span><span class="sxs-lookup"><span data-stu-id="05b99-172">New-Team</span></span>](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="05b99-173">Treinamento para o administrador do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="05b99-173">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)