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
description: Aprenda a usar os modelos do Teams para criar estruturas de equipe projetadas para as necessidades do varejista, fornecendo configurações predefinidas, canais e aplicativos pré-instalados.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424631"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introdução aos modelos do Teams no varejo

Os modelos do Teams permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Os modelos do Teams têm definições previamente criadas de estruturas de equipe projetadas em torno das necessidades dos varejistas. Você pode usar modelos do Teams para criar rapidamente os tipos de equipes que funcionam bem para varejistas e implantá-los em sua organização. Você também pode estender os modelos do Teams para criar equipes adaptadas às suas necessidades organizacionais específicas.

Neste artigo, apresentaremos cada um dos modelos do Teams e como recomendamos usá-los.

Este artigo é para você se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização de varejo. Você já implantou o serviço Teams em sua organização. Se você ainda não implementou o Teams, comece lendo [Como implementar o Microsoft Teams](How-to-roll-out-teams.md).

Para saber mais sobre os modelos de equipe em geral, confira [Primeiros passos com os modelos do Teams](get-started-with-teams-templates.md).

## <a name="store-template"></a>Modelo de Loja

O modelo de Loja é ideal para criar uma equipe para representar um local de loja individual. Usando o modelo de Loja, você pode criar uma equipe para cada local de loja de varejo em sua organização.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo - <br>Loja | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canais <ul><li>Entrega dos turnos\*</li><li>Aprendizado\*</li></ul>\*Canais favoritos automáticos<br><br>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Pública</li></ul> <br>Permissões de membro <ul><li>Não é possível criar/atualizar/excluir canais </li><li>Não é possível adicionar/remover aplicativos </li><li>Não é possível criar/atualizar/remover guias</li><li>Não é possível criar/atualizar/remover conectores</li><ul>|
||||

Maneiras recomendadas de personalizar o modelo de Loja para sua organização:

- Se sua organização tiver departamentos dentro de cada loja, adicione um canal para cada departamento. Adicionar um canal facilita a comunicação e a colaboração dentro do departamento.

- Se sua organização tiver sites internos (por exemplo, um site do Microsoft Office SharePoint Online), considere fixá-los como guias no canal de equipe relevante. Confira [Introdução aos modelos do Teams para varejo](get-started-with-teams-templates.md) para instruções.

## <a name="manager-collaboration-template"></a>Modelo Colaboração de Gerente

O modelo Colaboração de Gerente é outro dos modelos do Teams desenvolvidos em torno das necessidades dos varejistas. O modelo Colaboração de Gerente é ideal para criar uma equipe para um conjunto de gerentes para colaborar em lojas/regiões e muito mais. Por exemplo, se sua organização tem regiões, você pode criar uma equipe de Colaboração de Gerente para a Região da Califórnia e incluir todos os gerentes de loja dessa região, bem como o gerente regional dessa região.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo - <br>Loja | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canais <ul><li>Operações\*</li><li>Aprendizado\*</li></ul>\*Canais favoritos automáticos<br><br>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Privada</li></ul> <br>Permissões de membro <ul><li>É possível criar/atualizar/excluir canais </li><li>É possível adicionar/remover aplicativos </li><li>É possível criar/atualizar/remover guias</li><li>É possível criar/atualizar/remover conectores</li><ul>|
||||

Maneiras recomendadas de personalizar o modelo Colaboração de Gerente para sua organização:

- Se sua organização tiver sites internos, como um site do Microsoft Office SharePoint Online, que são relevantes para gerentes, considere fixá-los como guias em um canal de equipe relevante. Você pode dar uma olhada na [documentação do modelo do Microsoft Teams](get-started-with-teams-templates.md) para obter instruções.

## <a name="how-to-use-first-party-templates"></a>Como usar modelos de primeiros

Para usar esses modelos, basta alterar a propriedade "template@odata.bind" no corpo da solicitação de "padrão" para as TemplateIDs acima.  Para saber mais sobre como implantar modelos do Teams, confira o artigo do Microsoft Graph sobre como [criar um Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Os canais no modelo serão criados automaticamente na guia Geral.

### <a name="example-store-template-extension-script"></a>Exemplo: Script de extensão de modelo de Loja

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

[Introdução aos modelos do Teams no Centro de administração](get-started-with-teams-templates-in-the-admin-console.md)
