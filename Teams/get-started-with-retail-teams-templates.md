---
title: Introdução aos modelos do Teams no varejo
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar modelos de equipe para criar estruturas de equipe projetadas para as necessidades do revendedor fornecendo configurações, canais e aplicativos pré-instalados predefinidos.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424631"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introdução aos modelos do Teams no varejo

Os modelos de equipe permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Os modelos de equipe têm definições predefinidas de estruturas de equipe projetadas com base nas necessidades do revendedor. Você pode usar modelos do teams para criar rapidamente os tipos de equipes que funcionam bem para varejistas e implantá-las em toda a organização. Você também pode estender os modelos de equipe para criar equipes que sejam adequadas às suas necessidades organizacionais específicas.

Neste artigo, apresentaremos cada um dos modelos de equipe e recomendaremos como usá-los.

Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização de varejo. Você já implantou o serviço Microsoft Teams em sua organização. Se você ainda não distribuiu o Microsoft Teams, comece lendo o guia [como implantar o Microsoft Teams](How-to-roll-out-teams.md).

Para saber mais sobre os modelos de equipe em geral, confira [introdução aos modelos](get-started-with-teams-templates.md)do Microsoft Teams.

## <a name="store-template"></a>Modelo da loja

O modelo da loja é ideal para criar uma equipe para representar um local individual da loja de varejo. Usando o modelo da loja, você pode criar uma equipe para cada local da loja de varejo em sua organização.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo <br>Repositório | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canais <ul><li>Entrega de turnos\*</li><li>Aprendizagem\*</li></ul>\*Canais de favoritos automáticos<br><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como Public</li></ul> <br>Permissões de membro <ul><li>Não é possível criar/atualizar/excluir canais </li><li>Não é possível adicionar/remover aplicativos </li><li>Não é possível criar/atualizar/remover guias</li><li>Não é possível criar/atualizar/remover conectores</li><ul>|
||||

Maneiras recomendadas de personalizar o modelo de loja para sua organização:

- Se a sua organização tiver departamentos em cada loja, adicione um canal para cada departamento. Adicionar um canal facilita a comunicação e a colaboração dentro do departamento.

- Se sua organização tiver sites internos (por exemplo, um site do SharePoint), considere fixar como guias no canal da equipe relevante. Confira o introdução ao [Teams templates](get-started-with-teams-templates.md) para obter instruções.

## <a name="manager-collaboration-template"></a>Modelo de colaboração do gerente

O modelo de colaboração do gerente é outro um dos modelos de equipe projetados em torno das necessidades do revendedor. O modelo de colaboração do gerente é ideal para criar uma equipe para um conjunto de gerentes colaborar em lojas/regiões e muito mais. Por exemplo, se a sua organização tiver regiões, você pode criar uma equipe de colaboração do gerente para a região da Califórnia e incluir todos os gerentes da loja nessa região, bem como o gerente regional dessa região.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo <br>Repositório | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canais <ul><li>Operações\*</li><li>Aprendizagem\*</li></ul>\*Canais de favoritos automáticos<br><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como particular</li></ul> <br>Permissões de membro <ul><li>Pode criar/atualizar/excluir canais </li><li>Pode adicionar/remover aplicativos </li><li>Pode criar/atualizar/remover guias</li><li>Pode criar/atualizar/remover conectores</li><ul>|
||||

Maneiras recomendadas de personalizar o modelo de colaboração do gerente para sua organização:

- Se a sua organização tiver qualquer site interno, como um site do SharePoint, que seja relevante para gerentes, considere fixar as guias em um canal de equipe relevante. Você pode dar uma olhada na [documentação do modelo do Microsoft Teams](get-started-with-teams-templates.md) para obter instruções.

## <a name="how-to-use-first-party-templates"></a>Como usar modelos de primeira empresa

Para usar esses modelos, altere a propriedade ' template@odata. BIND ' no corpo da solicitação de ' Standard ' para a TemplateIDs acima.  Para obter mais informações sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph sobre como [criar uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Os canais no modelo serão automaticamente criados na guia geral.

### <a name="example-store-template-extension-script"></a>Exemplo: armazenar script de extensão de modelo

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
## <a name="relate-topic"></a>Tópico de relação

[Introdução aos modelos do Microsoft Teams no centro de administração](get-started-with-teams-templates-in-the-admin-console.md)
