---
title: Usar modelos de equipe de varejo
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
- m365-frontline
ms.localizationpriority: high
search.appverid: MET150
description: Saiba como gerenciar e usar os modelos de equipe de varejo no centro de administração do Teams e com o Microsoft Graph para criar equipes de forma rápida e fácil para sua organização de varejo.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e8d908a0c6183f4d305b0b622060cfd2ed78922
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396292"
---
# <a name="use-retail-team-templates"></a>Usar modelos de equipe de varejo

Os modelos de equipe no Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo uma estrutura de equipe predefinida de configurações, canais e aplicativos pré-instalados.

Para varejistas, os modelos de equipe podem ser especialmente poderosos, pois ajudam você a implantar rapidamente equipes consistentes em sua organização. Os modelos também ajudam a equipe a se orientar sobre como usar efetivamente o Teams.

O Teams inclui modelos projetados especificamente para necessidades do varejista. Use esses modelos pré-criados para criar rapidamente equipes para que a equipe se comunique e colabore. Neste artigo, apresentamos cada um desses modelos e recomendamos como usá-los.

A maneira como você gerencia e trabalha com modelos de equipe depende se você é um administrador ou desenvolvedor.

|Se você estiver: | Em seguida, você: |
| ---- | --------- |
| Um administrador ou profissional de IT |[Gerencie modelos de equipe no centro de administração do Teams](#manage-team-templates-in-the-teams-admin-center). Exiba modelos de equipe e aplique políticas de modelos para controlar quais modelos sua equipe pode usar no Teams para criar equipes. |
| Um desenvolvedor | [Use Microsoft Graph](#use-team-templates-with-microsoft-graph) para criar equipes com base em modelos de equipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gerenciar modelos de equipe no centro de administração do Teams

Como administrador, você pode gerenciar os modelos de equipe no Centro de administração do Microsoft Teams. Aqui, você pode exibir os detalhes sobre cada modelo. Você também pode [criar e atribuir políticas de modelos](templates-policies.md) para sua equipe controlar quais modelos são vistos no Teams para a [criação de equipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Para saber mais sobre modelos de equipe em geral, consulte [Introdução aos modelos de equipe no Centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md).

Atualmente, oferecemos os seguintes modelos de equipe de varejo pré-criados. Para exibi-los, no painel de navegação esquerdo do Centro de administração do Teams, acesse **Teams** > **Modelos do Teams**.

### <a name="organize-a-store"></a>Organizar uma loja

Reúna seus funcionários de varejo em uma experiência central para gerenciar tarefas, compartilhar documentos e resolver problemas de clientes. Integre aplicativos adicionais para simplificar os processos de início e término de turnos.

| Tipo de modelo |TemplateId | Propriedades que vêm com este modelo |
| ------------------|-- |----------------------------------------------------- |
|Organizar uma store| `retailStore` |Canais: <ul><li>Geral<li>Mudança de entrega</li><li>Preparação da loja<ul><li>Inspeção&sup1;</li></ul></li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Wiki</li><li>Tarefas</li><li>Turnos</li><li>Inspeção</li></ul>|

&sup1;Aplicativo adicionado ao canal como uma guia.

### <a name="manager-collaboration"></a>Colaboração do Gerente

O modelo de Colaboração do Gerente é ideal para criar uma equipe para que um conjunto de gerentes colabore em lojas, regiões e assim por diante. Por exemplo, se sua organização tiver regiões, você poderá criar uma equipe de Colaboração do Gerente para a região da Califórnia e incluir todos os gerentes de loja nessa região, juntamente com o gerente regional dessa região.

| Tipo de modelo| TemplateId | Propriedades que vêm com este modelo |
| ------------------|- |----------------------------------------------------- |
|Varejo para gerentes|`retailManagerCollaboration` |Canais: <ul><li>Geral<li>Operações<ul><li>Tarefas (Tarefas de Operações)&sup1;</li><li>Inspeção&sup1;</li></ul></li><li>Aprendizado<ul><li>Tarefas (Tarefas de Aprendizagem)&sup1;</li></ul></li></ul> Apps: <ul><li>Wiki</li><li>Tarefas</li><li>Inspeção</li></ul>|
||||

&sup1;Aplicativo adicionado ao canal como uma guia.

## <a name="use-team-templates-with-microsoft-graph"></a>Usar os modelos do Teams com o Microsoft Graph

Os desenvolvedores podem usar o Microsoft Graph para criar equipes a partir de modelos de equipe pré-criados. Para saber mais sobre como usar modelos de equipe com o Microsoft Graph, consulte [ Introdução aos modelos de equipe usando Microsoft Graph](get-started-with-teams-templates.md), [Visão geral da API do Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) e [tipo de recurso teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Aqui estão os modelos de equipe de varejo pré-criados.

### <a name="store"></a>Repositório

O modelo de Loja é ideal para criar uma equipe para representar um local de loja individual. Usando o modelo de Loja, você pode criar uma equipe para cada local de loja de varejo em sua organização.

| Tipo de modelo | TemplateId | Canais de modelo |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo - <br>Loja | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| Canais <ul><li>Geral</li><li>Entrega de turno&sup2;</li><li>Preparação da loja</li><li>Aprendizado&sup2;</li></ul>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Pública</li></ul> <br>Permissões de membro <ul><li>Não é possível criar, atualizar ou excluir canais </li><li>Não é possível adicionar ou remover aplicativos </li><li>Não é possível criar, atualizar ou remover guias</li><li>Não é possível criar, atualizar ou remover conectores</li><ul>|
||||

&sup2;Canais marcados como favorito automaticamente

Maneiras recomendadas de personalizar o modelo de Loja para sua organização:

- Se sua organização tiver departamentos dentro de cada loja, adicione um canal para cada departamento. Adicionar um canal facilita a comunicação e a colaboração dentro do departamento.

- Se sua organização tiver sites internos (por exemplo, um site do Microsoft Office SharePoint Online), considere fixá-los como guias no canal de equipe relevante.

### <a name="manager-collaboration"></a>Colaboração do Gerente

O modelo de Colaboração do Gerente é ideal para criar uma equipe para que um conjunto de gerentes colabore em lojas, regiões e assim por diante. Por exemplo, se sua organização tiver regiões, você poderá criar uma equipe de Colaboração do Gerente para a região da Califórnia e incluir todos os gerentes de loja nessa região, juntamente com o gerente regional dessa região.

| Tipo de modelo | TemplateId | Canais de modelo |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo - <br>Loja | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canais <ul><li>Geral</li><li>Operações&sup2;</li><li>Aprendizado&sup2;</li></ul>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Privada</li></ul> <br>Permissões de membro <ul><li>Pode criar, atualizar e excluir canais </li><li>Pode adicionar e remover aplicativos </li><li>Pode criar, atualizar e remover guias</li><li>Pode criar, atualizar e remover conectores</li><ul>|
||||

&sup2;Canais marcados como favorito automaticamente

Maneiras recomendadas de personalizar o modelo Colaboração de Gerente para sua organização:

- Se sua organização tiver sites internos, como um site do Microsoft Office SharePoint Online, que são relevantes para gerentes, considere fixá-los como guias em um canal de equipe relevante.

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Como usar modelos de equipe com o Microsoft Graph

Para usar esses modelos, altere a propriedade 'template@odata.bind' no corpo da solicitação de 'padrão' para as TemplateIds acima.  Para obter mais informações sobre como implantar modelos de equipe, consulte o artigo do Microsoft Graph sobre como [criar uma equipe](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Os canais no modelo serão criados automaticamente na guia **Geral**.

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

## <a name="related-articles"></a>Artigos relacionados

- [Introdução aos modelos de equipe no Centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar uma equipe a partir de um modelo](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introdução aos modelos de equipe usando Microsoft Graph](get-started-with-teams-templates.md)