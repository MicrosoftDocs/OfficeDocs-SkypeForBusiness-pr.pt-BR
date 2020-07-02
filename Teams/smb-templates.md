---
title: Modelos de equipe para empresas de pequeno e médio porte
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
description: Use os modelos predefinidos do Microsoft Teams para criar com rapidez e facilidade empresas para empresas de pequeno e médio porte.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1de5e0459168c7586f0b8e18a33153ca1519853a
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944024"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a>Comece a usar os modelos do teams para pequenas e médias empresas

Os modelos do Microsoft Teams permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Para empresas de pequeno e médio porte, os modelos podem ser especialmente poderosos, pois ajudam os administradores a implantar equipes rapidamente em toda a organização. Os modelos também ajudam a orientar os usuários e começar a usar o Microsoft Teams com eficiência. Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização.

Atualmente, oferecemos três modelos SMB de primeira empresa que você pode aproveitar para várias situações. Todos os modelos criarão equipes *particulares* . Depois de criar as equipes e se preparar para a sua organização, você pode definir a privacidade para *toda* a organização ou *pública*, conforme apropriado. Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](get-started-with-teams-templates.md)do Microsoft Teams.

## <a name="company-wide-template"></a>Modelo de toda a empresa
O modelo para toda a empresa destina-se à comunicação e colaboração que são relevantes para toda a empresa. Você pode usar o canal geral para anúncios em toda a empresa, notícias do setor ou publicações executivas. O canal de recursos humanos é um ótimo lugar para consolidar todas as atividades relacionadas a RH, como Postagens de trabalho, novos recursos de integração de funcionários, treinamento e desenvolvimento. O canal de coisas divertidas fornece uma plataforma social para todas as postagens divertidas e divertidas.

| Tipo de modelo base  | baseTemplateId | Propriedades que vêm com este modelo base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>Em toda a empresa | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canais <ul><li>Geral\*</li><li>Recursos humanos\*</li><li>Coisas divertidas\*</li></ul><br> Aplicativos<ul><li>Portal da empresa (website fixado ao canal de **recursos humanos** ) </li> </UL><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como particular</li></ul> |

* Canais de favoritos automáticos 

Para criar a equipe de toda a empresa por meio de padrões predefinidos do modelo predefinido, forneça a representação JSON do objeto de equipe no corpo da solicitação. Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Solicitação 
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

## <a name="executive-team-template"></a>Modelo de equipe executiva

O modelo de equipe executiva é ideal para criar uma equipe para que executivos da empresa se comuniquem e colaborem em iniciativas da empresa, como prioridades anuais, orçamentos fiscais, iniciativas estratégicas, principais clientes, etc. Este modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos.

| Tipo de modelo base  | baseTemplateId | Propriedades que vêm com este modelo base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>Equipe de executivos | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canais <ul><li>Geral\*</li><li>Priva\*</li></ul> Aplicativos<ul><li>OneNote (fixado ao canal **privado** )</li> <li>Planner (fixado ao canal **privado** ) </li></ul><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como particular</li></ul> | 

* Canais de favoritos automáticos<br>

Para criar a equipe de executivos, basta usar os padrões do modelo predefinido, fornecer a representação JSON do objeto de equipe no corpo da solicitação. Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Solicitação 
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

## <a name="departmental-team-template"></a>Modelo de equipe departamental

O modelo de equipe departamental pode ser usado para criar uma equipe para departamentos individuais ou para projetos. O modelo de equipe de finanças é ideal para todas as postagens, anúncios e colaboração diária e comunicação dentro dos membros da equipe de Finanças (e membros da equipe executiva, conforme apropriado). O modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos. Também fornecemos o script a seguir para a equipe de Finanças que pode ser usada para estender o modelo para departamentos adicionais ou projetos específicos adicionando, excluindo ou editando a sua preferência. Por exemplo, se você tiver um departamento de *marketing* , o script poderá ser adaptado renomeando-se a equipe do *departamento de finanças* ao *marketing* para criar uma nova equipe de marketing

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>Finanças  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canais <ul><li>Geral\*</li><li>Priva\*</li></ul><br> Aplicativos<ul><li>OneNote (fixado ao canal **privado** )</li> <li>Planner (fixado ao canal **privado** ) </li> </ul><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como particular</li></ul> | 

* Canais de favoritos automáticos

Para criar a equipe de finanças, basta usar os padrões do modelo predefinido, fornecer a representação JSON do objeto de equipe no corpo da solicitação. Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Solicitação 
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

### <a name="example-finance-team-template-extension-script"></a>Exemplo: script de extensão de modelo de equipe financeira

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

## <a name="related-topics"></a>Tópicos relacionados

- [Introdução aos modelos do Teams](get-started-with-teams-templates.md)
- [Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (na visualização)

