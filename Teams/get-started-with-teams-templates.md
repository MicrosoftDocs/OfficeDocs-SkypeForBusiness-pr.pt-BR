---
title: Introdução ao modelos de equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 7850ad245eebee96b6852e7f0cc57a35adcca9f7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295003"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="51616-103">Introdução ao modelos de equipes</span><span class="sxs-lookup"><span data-stu-id="51616-103">Get started with Teams templates</span></span> 

<span data-ttu-id="51616-104">Modelos de equipe são pré-criados definições da estrutura de uma equipe Projetado levando em consideração uma necessidade comercial ou projeto.</span><span class="sxs-lookup"><span data-stu-id="51616-104">Team templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="51616-105">Você pode usar modelos de equipe para criar rapidamente os espaços de colaboração avançada com canais para tópicos diferentes e pré-instalação de aplicativos seja obtida dos planejamentos nos serviços e conteúdo de missão crítica.</span><span class="sxs-lookup"><span data-stu-id="51616-105">You can use team templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="51616-106">Os modelos de equipe fornecem uma estrutura de equipe predefinidas que pode ajudá-lo a criar facilmente equipes consistentes em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="51616-106">Team templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="51616-107">Neste artigo, vamos explicar as propriedades que podem ser definidas nos modelos, qual modelo base tipos forem, e como você pode usar algumas solicitações para criar uma equipe a partir de um modelo de exemplo.</span><span class="sxs-lookup"><span data-stu-id="51616-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="51616-108">Este artigo é para você, se você estiver:</span><span class="sxs-lookup"><span data-stu-id="51616-108">This article is for you if you're:</span></span>

<span data-ttu-id="51616-109">• Responsáveis por planejar, implantar e gerenciando várias equipes entre seu desenvolvedor de • uma organização procurando para criar uma equipe com canais e predefinidos aplicativos programaticamente</span><span class="sxs-lookup"><span data-stu-id="51616-109">•   Responsible for planning, deploying, and managing multiple teams across your organization •   A developer looking to create a team with predefined channels and apps programmatically</span></span>

## <a name="team-template-capabilities"></a><span data-ttu-id="51616-110">Recursos do modelo de equipe</span><span class="sxs-lookup"><span data-stu-id="51616-110">Team template capabilities</span></span>

<span data-ttu-id="51616-111">A maioria das propriedades em uma equipe são incluídas e suportado por modelos.</span><span class="sxs-lookup"><span data-stu-id="51616-111">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="51616-112">No entanto, há algumas propriedades e recursos que não são suportados atualmente.</span><span class="sxs-lookup"><span data-stu-id="51616-112">However, there are a few properties and features that are currently not supported.</span></span> <span data-ttu-id="51616-113">A tabela a seguir fornece um resumo rápido o que está incluído e o que não está incluído nos modelos de equipes.</span><span class="sxs-lookup"><span data-stu-id="51616-113">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="51616-114">**Propriedades da equipe compatíveis com os modelos de equipes**</span><span class="sxs-lookup"><span data-stu-id="51616-114">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="51616-115">**Propriedades da equipe ainda não é suportadas por modelos de equipes**</span><span class="sxs-lookup"><span data-stu-id="51616-115">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="51616-116">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="51616-116">Base template type</span></span> | <span data-ttu-id="51616-117">Associação de equipe</span><span class="sxs-lookup"><span data-stu-id="51616-117">Team membership</span></span> |
| <span data-ttu-id="51616-118">Nome da equipe</span><span class="sxs-lookup"><span data-stu-id="51616-118">Team name</span></span> | <span data-ttu-id="51616-119">Imagem de equipe</span><span class="sxs-lookup"><span data-stu-id="51616-119">Team picture</span></span> |
| <span data-ttu-id="51616-120">Descrição da equipe</span><span class="sxs-lookup"><span data-stu-id="51616-120">Team description</span></span> | <span data-ttu-id="51616-121">Configurações de canal (por exemplo, autofavorito e privacidade)</span><span class="sxs-lookup"><span data-stu-id="51616-121">Channel settings (for example, auto-favorite and privacy)</span></span> |
| <span data-ttu-id="51616-122">Visibilidade de equipe (pública ou privada)</span><span class="sxs-lookup"><span data-stu-id="51616-122">Team visibility (public or private)</span></span> | <span data-ttu-id="51616-123">Conectores</span><span class="sxs-lookup"><span data-stu-id="51616-123">Connectors</span></span> |
| <span data-ttu-id="51616-124">Configurações de equipe (por exemplo, o membro, o convidado, @ menções)</span><span class="sxs-lookup"><span data-stu-id="51616-124">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="51616-125">Arquivos e conteúdo</span><span class="sxs-lookup"><span data-stu-id="51616-125">Files and content</span></span> |
| <span data-ttu-id="51616-126">Autofavorito canal</span><span class="sxs-lookup"><span data-stu-id="51616-126">Auto-favorite channel</span></span> | |
| <span data-ttu-id="51616-127">Aplicativo instalado</span><span class="sxs-lookup"><span data-stu-id="51616-127">Installed app</span></span> | |
| <span data-ttu-id="51616-128">Guias fixados</span><span class="sxs-lookup"><span data-stu-id="51616-128">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="51616-129">Podemos vai ser adicionando mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique novamente para obter as informações mais atualizadas sobre propriedades com suporte.</span><span class="sxs-lookup"><span data-stu-id="51616-129">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="51616-130">Quais são os tipos de modelo base?</span><span class="sxs-lookup"><span data-stu-id="51616-130">What are base template types?</span></span>

<span data-ttu-id="51616-131">Tipos de modelo base são modelos especiais que a Microsoft criou para setores específicos.</span><span class="sxs-lookup"><span data-stu-id="51616-131">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="51616-132">Esses modelos base geralmente contêm proprietários aplicativos que não estão disponíveis nas propriedades do repositório e a equipe que ainda não suportadas individualmente nos modelos de equipes.</span><span class="sxs-lookup"><span data-stu-id="51616-132">These base templates often contain proprietary apps that aren't available in the store and team properties not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="51616-133">Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais com propriedades adicionais que você gostaria de especificar.</span><span class="sxs-lookup"><span data-stu-id="51616-133">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="51616-134">No entanto, alguns tipos de modelo base contêm propriedades que não podem ser substituídas.</span><span class="sxs-lookup"><span data-stu-id="51616-134">However, some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="51616-135">Por padrão, o modelo base é definido para o **padrão** que não contenha nenhum apps proprietárias adicionais ou propriedades especiais.</span><span class="sxs-lookup"><span data-stu-id="51616-135">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="51616-136">Abaixo é a lista atual de tipos de base modelos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="51616-136">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="51616-137">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="51616-137">Base template type</span></span> | <span data-ttu-id="51616-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="51616-138">baseTemplateId</span></span> | <span data-ttu-id="51616-139">Aplicativos de proprietário do modelo base e propriedades especiais</span><span class="sxs-lookup"><span data-stu-id="51616-139">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="51616-140">Standard</span><span class="sxs-lookup"><span data-stu-id="51616-140">Standard</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | <span data-ttu-id="51616-141">Não há aplicativos adicionais e propriedades</span><span class="sxs-lookup"><span data-stu-id="51616-141">No additional apps and properties</span></span> |
| <span data-ttu-id="51616-142">Saúde - coordenação de atendimento médico</span><span class="sxs-lookup"><span data-stu-id="51616-142">Healthcare - care coordination</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | <span data-ttu-id="51616-143">Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="51616-143">Apps:</span></span><br/> <span data-ttu-id="51616-144">-App os pacientes (fixado a guia **Geral** )</span><span class="sxs-lookup"><span data-stu-id="51616-144">- Patients app (pinned to the **General** tab)</span></span><br/> <br/><span data-ttu-id="51616-145">Canais:</span><span class="sxs-lookup"><span data-stu-id="51616-145">Channels:</span></span> <br/> <span data-ttu-id="51616-146">-Comunicados</span><span class="sxs-lookup"><span data-stu-id="51616-146">- Announcements</span></span><br/> <span data-ttu-id="51616-147">-Diabetes</span><span class="sxs-lookup"><span data-stu-id="51616-147">- Diabetes</span></span><br/> <span data-ttu-id="51616-148">-Cardiovascular</span><span class="sxs-lookup"><span data-stu-id="51616-148">- Cardiovascular</span></span><br/> <span data-ttu-id="51616-149">-Registered enfermeiras</span><span class="sxs-lookup"><span data-stu-id="51616-149">- Registered nurses</span></span> |
| <span data-ttu-id="51616-150">Saúde - huddle de processo</span><span class="sxs-lookup"><span data-stu-id="51616-150">Healthcare - process huddle</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | <span data-ttu-id="51616-151">Canais:</span><span class="sxs-lookup"><span data-stu-id="51616-151">Channels:</span></span><br/> <span data-ttu-id="51616-152">-Evitáveis mortes</span><span class="sxs-lookup"><span data-stu-id="51616-152">- Avoidable deaths</span></span><br/> <span data-ttu-id="51616-153">-Revisão mortality</span><span class="sxs-lookup"><span data-stu-id="51616-153">- Mortality review</span></span> <br/> <span data-ttu-id="51616-154">-Impedindo divide-se</span><span class="sxs-lookup"><span data-stu-id="51616-154">- Preventing falls</span></span> <br/> <span data-ttu-id="51616-155">-Planos de sepsis</span><span class="sxs-lookup"><span data-stu-id="51616-155">- Sepsis plans</span></span> |
| <span data-ttu-id="51616-156">Educação - classe equipe<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="51616-156">Education - Class team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | <span data-ttu-id="51616-157">Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="51616-157">Apps:</span></span><br/> <span data-ttu-id="51616-158">-Bloco de anotações de classe OneNote (fixados a guia **Geral** )</span><span class="sxs-lookup"><span data-stu-id="51616-158">- OneNote Class Notebook (pinned to the **General** tab)</span></span> <br/> <span data-ttu-id="51616-159">-App atribuições (fixado a guia **Geral** )</span><span class="sxs-lookup"><span data-stu-id="51616-159">- Assignments app (pinned to the **General** tab)</span></span> <br/><br/> <span data-ttu-id="51616-160">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="51616-160">Team properties</span></span> <br/> <span data-ttu-id="51616-161">-Visibilidade equipe definida como **HiddenMembership** (não pode ser substituída)</span><span class="sxs-lookup"><span data-stu-id="51616-161">- Team visibility set to **HiddenMembership** (cannot be overridden)</span></span> |
| <span data-ttu-id="51616-162">A equipe de educação - equipe<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="51616-162">Education - Staff team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | <span data-ttu-id="51616-163">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="51616-163">Apps</span></span><br/> <span data-ttu-id="51616-164">-Bloco de anotações da equipe OneNote (fixados a guia **Geral** )</span><span class="sxs-lookup"><span data-stu-id="51616-164">- OneNote Staff Notebook (pinned to the **General** tab)</span></span> |

<span data-ttu-id="51616-165">Publicação de <sup>1</sup> em outubro de 2018 tardia</span><span class="sxs-lookup"><span data-stu-id="51616-165"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="51616-166">Serão adicionados mais modelo base digita em futuras versões do Microsoft Teams, para verificar novamente as informações mais atualizadas sobre suporte a propriedades.</span><span class="sxs-lookup"><span data-stu-id="51616-166">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="51616-167">Exemplos</span><span class="sxs-lookup"><span data-stu-id="51616-167">Examples</span></span> 

<span data-ttu-id="51616-168">Você pode iniciar a criação de uma equipe via modelo instalando o [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span><span class="sxs-lookup"><span data-stu-id="51616-168">You can start creating a team via template by installing [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="51616-169">Crie uma equipe a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="51616-169">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="51616-170">Solicitações</span><span class="sxs-lookup"><span data-stu-id="51616-170">Requests</span></span>

<span data-ttu-id="51616-171">**Solicitação para criar uma equipe com o modelo base standard**</span><span class="sxs-lookup"><span data-stu-id="51616-171">**Request to create a team with the standard base template**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

<span data-ttu-id="51616-172">**Solicitação para criar uma equipe com um canal extra e invalidar membros excluam canais**</span><span class="sxs-lookup"><span data-stu-id="51616-172">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

<span data-ttu-id="51616-173">**Solicitação para criar uma equipe com todas as propriedades com suporte**</span><span class="sxs-lookup"><span data-stu-id="51616-173">**Request to create a team with all supported properties**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a><span data-ttu-id="51616-174">Resposta</span><span class="sxs-lookup"><span data-stu-id="51616-174">Response</span></span>

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
}
~~~

### <a name="get-status"></a><span data-ttu-id="51616-175">Obter o status</span><span class="sxs-lookup"><span data-stu-id="51616-175">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="51616-176">Solicitação</span><span class="sxs-lookup"><span data-stu-id="51616-176">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="51616-177">Resposta</span><span class="sxs-lookup"><span data-stu-id="51616-177">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="51616-178">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="51616-178">Related topics</span></span>

- <span data-ttu-id="51616-179">[Criar equipe](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (no modo de visualização)</span><span class="sxs-lookup"><span data-stu-id="51616-179">[Create team](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (in preview)</span></span>
- [<span data-ttu-id="51616-180">Nova equipe</span><span class="sxs-lookup"><span data-stu-id="51616-180">New-Team</span></span>](https://docs.microsoft.com/en-us/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="51616-181">Treinamento para o administrador do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51616-181">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)