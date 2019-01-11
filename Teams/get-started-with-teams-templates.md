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
# <a name="get-started-with-teams-templates"></a>Introdução ao modelos de equipes 

Modelos de equipes são pré-criados definições da estrutura de uma equipe Projetado levando em consideração uma necessidade comercial ou projeto. Você pode usar modelos de equipes para criar rapidamente os espaços de colaboração avançada com canais para tópicos diferentes e pré-instalação de aplicativos seja obtida dos planejamentos nos serviços e conteúdo de missão crítica. Os modelos de equipes fornecem uma estrutura de equipe predefinidas que pode ajudá-lo a criar facilmente equipes consistentes em toda a organização. 

Neste artigo, vamos explicar as propriedades que podem ser definidas nos modelos, qual modelo base tipos forem, e como você pode usar algumas solicitações para criar uma equipe a partir de um modelo de exemplo.
 
Este artigo é para você, se você estiver:

- Responsável pelo planejamento, implantação e gerenciamento de várias equipes em toda a organização<br>
- Um desenvolvedor querer criar programaticamente uma equipe com aplicativos e canais predefinidos 

## <a name="teams-template-capabilities"></a>Recursos do modelo de equipes

A maioria das propriedades em uma equipe são incluídas e suportado por modelos. Mas há algumas propriedades e recursos que não são suportados no momento. A tabela a seguir fornece um resumo rápido o que está incluído e o que não está incluído nos modelos de equipes.

| **Propriedades da equipe compatíveis com os modelos de equipes** | **Propriedades da equipe ainda não é suportadas por modelos de equipes** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo base | Associação de equipe |
| Nome da equipe | Imagem de equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade de equipe (pública ou privada) | Conectores |
| Configurações de equipe (por exemplo, o membro, o convidado, @ menções) | Arquivos e conteúdo |
| Autofavorito canal | |
| Aplicativo instalado | |
| Guias fixados | | 

> [!NOTE]
> Podemos vai ser adicionando mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique novamente para obter as informações mais atualizadas sobre propriedades com suporte.

## <a name="what-are-base-template-types"></a>Quais são os tipos de modelo base?

Tipos de modelo base são modelos especiais que a Microsoft criou para setores específicos. Esses modelos base geralmente contêm proprietários aplicativos que não estão disponíveis nas propriedades do repositório e a equipe que ainda não são aceitas individualmente nos modelos de equipes.

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais com propriedades adicionais que você gostaria de especificar. Mas alguns tipos de modelo base contém propriedades que não podem ser substituídas. 

Por padrão, o modelo base é definido para o **padrão** que não contenha nenhum apps proprietárias adicionais ou propriedades especiais. Abaixo é a lista atual de tipos de base modelos disponíveis.

| Tipo de modelo base | baseTemplateId | Aplicativos de proprietário do modelo base e propriedades especiais |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | Não há aplicativos adicionais e propriedades |
| Educação- <br>Equipe de classe<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | Aplicativos:<ul><li>Bloco de anotações de classe do OneNote (fixados a guia **Geral** ) </li><li>Aplicativo de atribuições (fixado a guia **Geral** )</li></ul> Propriedades de equipe:<ul><li>Visibilidade da equipe é definido como **HiddenMembership** (não pode ser substituída)</li></ul> |
| Educação-<br>A equipe da equipe<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | Aplicativos:<ul><li>Bloco de anotações de equipe do OneNote (fixados a guia **Geral** )</li></ul> |
|Educação-<br>Equipe PLC |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | Aplicativos:<ul><li>Anotações do OneNote PLC (fixados a guia **Geral** )</ul></li>|
|||

Publicação de <sup>1</sup> em outubro de 2018 tardia

> [!NOTE]
> Serão adicionados mais modelo base digita em futuras versões do Microsoft Teams, para verificar novamente as informações mais atualizadas sobre suporte a propriedades.

## <a name="examples"></a>Exemplos 

Você pode iniciar usando um modelo para criar uma equipe usando a [API do Microsoft Graph](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

### <a name="create-a-team-from-a-template"></a>Crie uma equipe a partir de um modelo

#### <a name="requests"></a>Solicitações

**Solicitação para criar uma equipe com o modelo base standard**

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

**Solicitação para criar uma equipe com um canal extra e invalidar membros excluam canais**

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

**Solicitação para criar uma equipe com todas as propriedades com suporte**

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

### <a name="get-status"></a>Obter o status

#### <a name="request"></a>Solicitação

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a>Resposta

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a>Tópicos relacionados

- [Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (no modo de visualização)
- [Nova equipe](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Treinamento para o administrador do Microsoft Teams](itadmin-readiness.md)