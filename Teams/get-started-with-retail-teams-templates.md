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
description: Saiba como usar modelos do Teams para criar estruturas de equipe projetadas para necessidades do revendedor, fornecendo configurações, canais e aplicativos pré-instalados predefinidos.
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

Os modelos do Teams permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Os modelos do Teams têm definições predefinida de estruturas de equipe projetadas em torno das necessidades do varejista. Você pode usar modelos do Teams para criar rapidamente os tipos de equipes que funcionam bem para revendedores e implantá-los em toda a organização. Você também pode estender os modelos do Teams para criar equipes adaptadas às suas necessidades organizacionais específicas.

Neste artigo, apresentaremos cada um dos modelos do Teams e recomendaremos como usá-los.

Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em sua organização de varejo. Você já implantou o serviço do Teams em sua organização. Se você ainda não tiver lançado o Teams, comece lendo o livro Como [lançar o Microsoft Teams.](How-to-roll-out-teams.md)

Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar modelos do Teams.](get-started-with-teams-templates.md)

## <a name="store-template"></a>Modelo da Loja

O modelo da Store é ideal para criar uma equipe para representar um local de loja de varejo individual. Usando o modelo da Store, você pode criar uma equipe para cada local da loja de varejo em sua organização.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo – <br>Repositório | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canais <ul><li>Entrega de turnos\*</li><li>Aprendizagem\*</li></ul>\*Canais favoritos automáticos<br><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como Pública</li></ul> <br>Permissões de membro <ul><li>Não é possível criar/atualizar/excluir canais </li><li>Não é possível adicionar/remover aplicativos </li><li>Não é possível criar/atualizar/remover guias</li><li>Não é possível criar/atualizar/remover conectores</li><ul>|
||||

Maneiras recomendadas de personalizar o modelo da Store para sua organização:

- Se sua organização tiver departamentos dentro de cada loja, adicione um canal para cada departamento. Adicionar um canal facilita a comunicação e a colaboração dentro do departamento.

- Se sua organização tiver qualquer site interno (por exemplo, um site do SharePoint), considere fixá-los como guias no canal de equipe relevante. Consulte Instruções [sobre como começar a usar modelos do Teams.](get-started-with-teams-templates.md)

## <a name="manager-collaboration-template"></a>Modelo de Colaboração do Gerente

O modelo colaboração do Gerente é outro dos modelos do Teams projetados em torno das necessidades do varejista. O modelo colaboração do Gerente é ideal para criar uma equipe para um conjunto de gerentes colaborarem entre lojas/regiões e muito mais. Por exemplo, se sua organização tiver regiões, você poderá criar uma equipe de Colaboração do Gerente para a Região da Califórnia e incluir todos os gerentes de loja nessa região, bem como o gerente regional dessa região.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo – <br>Repositório | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canais <ul><li>Operações\*</li><li>Aprendizagem\*</li></ul>\*Canais favoritos automáticos<br><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como Particular</li></ul> <br>Permissões de membro <ul><li>Pode criar/atualizar/excluir canais </li><li>Pode adicionar/remover aplicativos </li><li>Pode criar/atualizar/remover guias</li><li>Pode criar/atualizar/remover conectores</li><ul>|
||||

Maneiras recomendadas de personalizar o modelo de Colaboração do Gerente para sua organização:

- Se sua organização tiver sites internos, como um site do SharePoint, relevantes para os gerentes, considere fixá-los como guias em um canal de equipe relevante. Você pode dar uma olhada na documentação do [Modelo do Microsoft Teams para](get-started-with-teams-templates.md) obter instruções.

## <a name="how-to-use-first-party-templates"></a>Como usar modelos de primeira parte

Para usar esses modelos, altere a propriedade 'template@odata.bind' no corpo da solicitação de 'padrão' para as IDs modelo acima.  Para obter mais informações sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph sobre como [criar uma Equipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Os canais no modelo serão criados automaticamente na guia Geral.

### <a name="example-store-template-extension-script"></a>Exemplo: Script de extensão de modelo da Store

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
## <a name="relate-topic"></a>Relacionar tópico

[Começar a usar modelos do Teams no Centro de administração](get-started-with-teams-templates-in-the-admin-console.md)
