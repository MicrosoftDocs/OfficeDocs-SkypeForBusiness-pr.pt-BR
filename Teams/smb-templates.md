---
title: Modelos de equipe para pequenas e médias empresas criadas com o Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Use Microsoft Teams modelos predefinidos integrados ao Microsoft Graph para criar equipes de forma rápida e fácil para pequenas e médias empresas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 324470ffc3366750777c75776e4ae4e783dbb17f
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045677"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Modelos de equipe integrados ao Microsoft Graph para pequenas e médias empresas

Os modelos de equipe no Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo uma estrutura de equipe predefinida de configurações, canais e aplicativos pré-instalados.

Para pequenas e médias empresas, os modelos podem ser especialmente eficientes, pois ajudam você a implantar rapidamente Teams em sua organização. Os modelos também ajudam os usuários a se orientarem sobre como usar Teams. Este artigo é para você se você for responsável por planejar, implantar e gerenciar várias equipes em toda a sua organização.

Atualmente, oferecemos três modelos pré-construídos para pequenas e médias empresas que você pode usar para várias situações. Todos os modelos criam *equipes* privadas. Depois de criar as equipes e estiver pronto para a sua organização, você pode definir a privacidade como *Toda a* Organização ou *Público,* conforme apropriado.

Para saber mais sobre modelos de equipe em geral, consulte Começar a usar modelos de equipe [usando o Microsoft Graph](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>Company-Wide modelo

O Company-Wide é destinado à comunicação e colaboração para toda a empresa. Você pode usar o canal Geral para comunicados, notícias do setor ou postagens executivas em toda a empresa. O canal de Recursos Humanos é um ótimo local para consolidar todas as atividades relacionadas ao RH, como postagens de trabalho, integração, treinamento e desenvolvimento de novos funcionários. O canal Coisas Divertidas fornece uma plataforma social para todas as postagens aleatórias e divertidas.

| Tipo de modelo  | TemplateId | Propriedades que vêm com este modelo |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Toda a empresa | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canais <ul><li>Geral\*</li><li>Recursos Humanos\*</li><li>Coisas divertidas\*</li></ul><br> Aplicativos<ul><li>Portal da Empresa (Site fixado no canal **recursos** humanos) </li> </UL><br>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Privada</li></ul> |

*Canais favoritos automaticamente 

Para criar a equipe Company-Wide, fazendo as configurações padrão do modelo pré-definido, fornece a representação JSON do objeto de equipe no corpo da solicitação. Para saber mais sobre como implantar modelos de equipe, consulte o artigo do Microsoft Graph [sobre a criação de uma Equipe.](/graph/api/team-post?view=graph-rest-beta)

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

O modelo de Equipe Executiva é ideal para criar uma equipe para executivos da empresa se comunicarem e colaborarem em iniciativas da empresa, como prioridades anuais, orçamentos fiscais, iniciativas estratégicas e clientes principais. Este modelo vem com um *canal privado* para convidar usuários selecionados para tópicos específicos.

| Tipo de modelo  | TemplateId | Propriedades que vêm com este modelo |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Equipe de Executivos | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canais <ul><li>Geral\*</li><li>Private \*</li></ul> Aplicativos<ul><li>OneNote (fixado no **canal** Privado)</li> <li>Planner (fixado no **canal** privado) </li></ul><br>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Privada</li></ul> | 

*Canais favoritos automaticamente<br>

Para criar a equipe de Executivos, a partir do modelo pré-definido, fornece a representação JSON do objeto de equipe no corpo da solicitação. Para saber mais sobre como implantar modelos de equipe, consulte o artigo do Microsoft Graph [sobre a criação de uma Equipe.](/graph/api/team-post?view=graph-rest-beta)

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

## <a name="departmental-team-template"></a>Modelo de equipe de departamento

O modelo de equipe departmental pode ser usado para criar uma equipe para departamentos individuais ou para projetos. O modelo de equipe de Finanças é ideal para todas as postagens, comunicados e colaboração diária e comunicação dentro dos membros da equipe de Finanças e membros da equipe executiva, conforme apropriado. O modelo vem com um *canal privado* para convidar usuários selecionados para tópicos específicos.

Também fornecemos o script abaixo para a equipe de Finanças que pode ser usado para estender o modelo a departamentos adicionais ou projetos específicos adicionais adicionando, excluindo ou editando ao seu gosto. Por exemplo, se você tiver um departamento de *Marketing,* o script poderá ser adaptado renomeando a equipe de *Finanças* para *Marketing* para criar uma nova equipe de Marketing

| Tipo de modelo | TemplateId | Propriedades que vêm com este modelo |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finanças  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canais <ul><li>Geral\*</li><li>Private \*</li></ul><br> Aplicativos<ul><li>OneNote (fixado no **canal** Privado)</li> <li>Planner (fixado no **canal** privado) </li> </ul><br>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Privada</li></ul> | 

*Canais favoritos automaticamente

Para criar a equipe de Finanças, fazendo as configurações padrão do modelo pré-definido, fornece a representação JSON do objeto de equipe no corpo da solicitação. Para saber mais sobre como implantar modelos de equipe, consulte o artigo do Microsoft Graph [sobre a criação de uma Equipe.](/graph/api/team-post?view=graph-rest-beta)

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

### <a name="example-finance-team-template-extension-script"></a>Exemplo: script de extensão do modelo de equipe de finanças

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

- [Introdução aos modelos de equipe no Centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Introdução aos modelos de equipe usando o Microsoft Graph](get-started-with-teams-templates.md)
- [Criar equipe](/graph/api/team-post?view=graph-rest-beta) (na visualização)
