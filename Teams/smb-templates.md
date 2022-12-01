---
title: Modelos de equipe para pequenas e médias empresas criadas com Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
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
description: Use Microsoft modelos predefinidos do Teams criados no Microsoft Graph para criar equipes de forma rápida e fácil para pequenas e médias empresas.
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
ms.openlocfilehash: 85f1573cb93f5362dc046ab97e2ac621f147fe4a
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198713"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Modelos de equipe criados no Microsoft Graph para pequenas e médias empresas

Os modelos de equipe no Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo uma estrutura de equipe predefinida de configurações, canais e aplicativos pré-instalados.

Para pequenas e médias empresas, os modelos podem ser especialmente poderosos, pois ajudam você a implantar rapidamente o Teams em sua organização. Os modelos também ajudam os usuários a se orientarem sobre como usar efetivamente o Teams. Este artigo será para você se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização.

Atualmente, oferecemos três modelos pré-criados para pequenas e médias empresas que você pode usar para várias situações. Todos os modelos criam equipes *privadas* . Depois de criar as equipes e estiver pronto para ser distribuído para sua organização, você pode definir a privacidade como *Org-Wide* ou *Public*, conforme apropriado.

> [!NOTE]
> Você também pode usar Microsoft Graph para criar seus próprios modelos personalizados. Para saber mais, confira [o tipo de recurso teamTemplate](/graph/api/resources/teamtemplate).

Para saber mais sobre modelos de equipe em geral, consulte [Introdução aos modelos de equipe usando Microsoft Graph](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>modelo Company-Wide

O modelo Company-Wide destina-se à comunicação e colaboração para toda a empresa. Você pode usar o canal Geral para anúncios em toda a empresa, notícias do setor ou postagens executivas. O canal recursos humanos é um ótimo lugar para consolidar todas as atividades relacionadas ao RH, como postos de trabalho, integração, treinamento e desenvolvimento de novos funcionários. O canal Fun Stuff fornece uma plataforma social para todas as postagens aleatórias e divertidas.

| Tipo de modelo  | TemplateId | Propriedades que vêm com este modelo |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB- <br>Toda a empresa | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canais <ul><li>Geral\*</li><li>Recursos Humanos\*</li><li>Coisas divertidas\*</li></ul><br> Aplicativos<ul><li>Portal da Empresa (Site fixado no canal **de Recursos Humanos**) </li> </UL><br>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Privada</li></ul> |

*Canais favoritos automaticamente 

Para criar a equipe Company-Wide usando configurações padrão do modelo pré-definido, forneça a representação JSON do objeto team no corpo da solicitação. Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre como criar uma Equipe](/graph/api/team-post?view=graph-rest-beta&preserve-view=true).

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

## <a name="executive-team-template"></a>Modelo da Equipe Executiva

O modelo da Equipe Executiva é ideal para criar uma equipe para os executivos da empresa se comunicarem e colaborarem em iniciativas da empresa, como prioridades anuais, orçamentos fiscais, iniciativas estratégicas e clientes de ponta. Este modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos.

| Tipo de modelo  | TemplateId | Propriedades que vêm com este modelo |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB- <br>Equipe de Executivos | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canais <ul><li>Geral\*</li><li>Privada \*</li></ul> Aplicativos<ul><li>OneNote (fixado no canal **privado** )</li> <li>Planejador (fixado no canal **privado** ) </li></ul><br>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Privada</li></ul> | 

*Canais favoritos automaticamente<br>

Para criar a equipe Executivos usando configurações padrão do modelo pré-definido, forneça a representação JSON do objeto team no corpo da solicitação. Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre como criar uma Equipe](/graph/api/team-post?view=graph-rest-beta&preserve-view=true).

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

## <a name="departmental-team-template"></a>Modelo de Equipe Departamental

O modelo de equipe departamental pode ser usado para criar uma equipe para departamentos individuais ou para projetos. O modelo da equipe de finanças é ideal para todos os posts, anúncios e colaboração diária e comunicação dentro dos membros da equipe de Finanças e membros da equipe executiva, conforme apropriado. O modelo vem com um canal *privado* para convidar usuários selecionados para tópicos específicos.

Também fornecemos o script abaixo para a equipe de Finanças que pode ser usado para estender o modelo a departamentos adicionais ou projetos específicos, adicionando, excluindo ou editando ao seu gosto. Por exemplo, se você tiver um departamento de *Marketing* , o script poderá ser adaptado renomeando a equipe de *Finanças* para *Marketing* para criar uma nova equipe de Marketing

| Tipo de modelo | TemplateId | Propriedades que vêm com este modelo |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB- <br>Finanças  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canais <ul><li>Geral\*</li><li>Privada \*</li></ul><br> Aplicativos<ul><li>OneNote (fixado no canal **privado** )</li> <li>Planejador (fixado no canal **privado** ) </li> </ul><br>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Privada</li></ul> | 

*Canais favoritos automaticamente

Para criar a equipe de Finanças usando as configurações padrão do modelo pré-definido, forneça a representação JSON do objeto team no corpo da solicitação. Para saber mais sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph [sobre como criar uma Equipe](/graph/api/team-post?view=graph-rest-beta&preserve-view=true).

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

### <a name="example-finance-team-template-extension-script"></a>Exemplo: Script de extensão de modelo do Finance Team

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
- [Criar equipe](/graph/api/team-post?view=graph-rest-beta&preserve-view=true) (em versão prévia)
