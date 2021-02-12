---
title: Modelos do Teams para pequenas e médias empresas criadas com o Microsoft Graph
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
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294547"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Modelos do Teams integrados ao Microsoft Graph para Pequenas e Médias Empresas

Os modelos do Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Para pequenas e médias empresas, os modelos podem ser especialmente poderosos, pois ajudam os administradores a implantar rapidamente o Teams em sua organização. Os modelos também ajudam a orientar os usuários e começar a usar o Teams com eficiência. Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização.

Atualmente, oferecemos três modelos SMB de primeira mão que você pode aproveitar para várias situações. Todos os modelos criarão *o Private* Teams. Depois de criar o Teams e estiver pronto para ser criado para sua organização, você poderá definir a privacidade para Toda *a* Organização ou *Público,* conforme apropriado. Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar os modelos do Teams.](get-started-with-teams-templates.md)

## <a name="company-wide-template"></a>Company-Wide modelo
O Company-Wide é destinado à comunicação e à colaboração relevantes para toda a empresa. Você pode usar o canal Geral para comunicados de toda a empresa, notícias do setor ou postagens executivas. O canal recursos humanos é um ótimo lugar para consolidar todas as atividades relacionadas ao RH, como postagens de trabalho, integração de novos funcionários, treinamento e desenvolvimento. O canal Coisas Divertidas fornece uma plataforma social para todas as postagens aleatórias e divertidas.

| Tipo de modelo base  | baseTemplateId | Propriedades que vêm com este modelo base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Toda a empresa | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canais <ul><li>Geral\*</li><li>Recursos Humanos\*</li><li>Coisas divertidas\*</li></ul><br> Aplicativos<ul><li>Portal da Empresa (site fixado no canal **de Recursos Humanos)** </li> </UL><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como Particular</li></ul> |

*Canais favoritos automáticos 

Para criar a Company-Wide de equipe, a partir do modelo predefinida, fornecer a representação JSON do objeto de equipe no corpo da solicitação. Para saber mais sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph [sobre como criar uma Equipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

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

## <a name="executive-team-template"></a>Modelo de Equipe Executiva

O modelo de Equipe Executiva é ideal para criar uma equipe para que os executivos da empresa se comuniquem e colaborem em iniciativas da empresa, como prioridades anuais, orçamentos fiscais, iniciativas estratégicas e clientes principais. Este modelo vem com um *canal* particular para convidar usuários selecionados para tópicos específicos.

| Tipo de modelo base  | baseTemplateId | Propriedades que vêm com este modelo base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Equipe de Executivos | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canais <ul><li>Geral\*</li><li>Privada \*</li></ul> Aplicativos<ul><li>OneNote (fixado no **canal** Particular)</li> <li>Planner (fixado no **canal** Particular) </li></ul><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como Particular</li></ul> | 

*Canais favoritos automáticos<br>

Para criar a equipe Executivos, a partir do modelo predefinida, fornecer a representação JSON do objeto de equipe no corpo da solicitação. Para saber mais sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph [sobre como criar uma Equipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

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

## <a name="departmental-team-template"></a>Modelo de Equipe Do Departamento

O modelo de equipe departmental pode ser usado para criar uma equipe para departamentos individuais ou para projetos. O modelo de equipe de Finanças é ideal para todas as postagens, comunicados e colaboração diária e comunicação dentro dos membros da equipe de Finanças e membros da equipe executiva, conforme apropriado. O modelo vem com um *canal* particular para convidar usuários selecionados para tópicos específicos. Também fornecemos o script abaixo para a equipe de Finanças que pode ser usado para estender o modelo a departamentos adicionais ou projetos específicos adicionais adicionando, excluindo ou editando ao seu gosto. Por exemplo, se você tiver um departamento de *Marketing,* o script  poderá ser adaptado renomeando a equipe de Finanças para *Marketing* para criar uma nova equipe de Marketing

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finanças  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canais <ul><li>Geral\*</li><li>Privada \*</li></ul><br> Aplicativos<ul><li>OneNote (fixado no **canal** Particular)</li> <li>Planner (fixado no **canal** Particular) </li> </ul><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como Particular</li></ul> | 

*Canais favoritos automáticos

Para criar a equipe de Finanças, a partir do modelo predefinida, fornece a representação JSON do objeto da equipe no corpo da solicitação. Para saber mais sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph [sobre como criar uma Equipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

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

### <a name="example-finance-team-template-extension-script"></a>Exemplo: script de extensão de modelo de Equipe de Finanças

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

- [Começar a usar modelos do Teams no console de administração](get-started-with-teams-templates-in-the-admin-console.md)
- [Introdução aos modelos do Teams](get-started-with-teams-templates.md)
- [Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (na visualização)

