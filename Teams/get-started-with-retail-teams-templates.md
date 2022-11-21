---
title: Usar modelos de equipe de varejo
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
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
ms.openlocfilehash: e32430990450fbe72cf80efd5eb960a28e3315a1
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131320"
---
# <a name="use-retail-team-templates"></a>Usar modelos de equipe de varejo

## <a name="overview"></a>Visão geral

Os modelos de equipe no Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo uma estrutura de equipe predefinida de configurações, canais e aplicativos pré-instalados.

Para varejistas, os modelos de equipe podem ser especialmente poderosos, pois ajudam você a implantar rapidamente equipes consistentes em sua organização. Os modelos também ajudam a equipe a se orientar sobre como usar efetivamente o Teams.

O Teams inclui modelos projetados especificamente para necessidades do varejista. Use esses modelos pré-criados para criar rapidamente equipes para que a equipe se comunique e colabore. Neste artigo, apresentamos cada um desses modelos e recomendamos como usá-los.

A maneira como você gerencia e trabalha com modelos de equipe depende se você é um administrador ou desenvolvedor.

|Se você estiver: | Em seguida, você: |
| ---- | --------- |
| Um administrador ou profissional de IT |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Um desenvolvedor | [Use Microsoft Graph](#use-team-templates-with-microsoft-graph) para criar equipes com base em modelos de equipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gerenciar modelos de equipe no centro de administração do Teams

Como administrador, você pode gerenciar os modelos de equipe no Centro de administração do Microsoft Teams. Aqui, você pode exibir os detalhes sobre cada modelo. Você também pode [criar e atribuir políticas de modelos](templates-policies.md) para sua equipe controlar quais modelos são vistos no Teams para a [criação de equipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Para saber mais sobre modelos de equipe em geral, consulte [Introdução aos modelos de equipe no Centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md).

Atualmente, oferecemos os seguintes modelos de equipe de varejo pré-criados. Para exibi-los, no painel de navegação esquerdo do Centro de administração do Teams, acesse **Teams** > **Modelos do Teams**.

> [!NOTE]
> Um asterisco (*) indica que o modelo é um *modelo conectado do Microsoft 365*. Quando os usuários criam uma equipe usando o modelo, o modelo do SharePoint conectado é aplicado ao site e à equipe. Componentes do SharePoint, como páginas, listas e integrações do Power Platform, são adicionados automaticamente e fixados como guias para o canal Geral na equipe. Os usuários podem editar essas páginas e listas diretamente de dentro do Teams.
>
> Para saber mais sobre modelos do SharePoint, consulte [Aplicar e personalizar modelos de site do SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Gerenciar uma Loja*

Reúna seus funcionários de varejo em uma experiência central para gerenciar tarefas, compartilhar documentos e resolver problemas de clientes. Integre aplicativos adicionais para simplificar os processos de início e término de turnos.

> [!div class="mx-tdBreakAll"]
>| Tipo de modelo |TemplateId | Propriedades que vêm com este modelo |
>| ------------------|-- |----------------------------------------------------- |
>| Gerenciar uma Loja| `retailStore` |Canais: <ul><li>Geral<li>Shift Handoff</li><li>Preparação da Loja</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Aprovações</li><li>Inspeção</li><li>Listas<ul><li>Lista de inventário</li></ul></li><li>Páginas do SharePoint<ul><li>Nossa loja</li></ul></li><li>Turnos</li><li>Tarefas por Planejador e Para Fazer</li><li>Wiki</li></ul>|

### <a name="retail-for-managers"></a>Varejo para Gerentes*

Crie uma equipe para um conjunto de gerentes para colaborar entre lojas ou regiões. Por exemplo, se sua organização tiver regiões, você poderá criar uma equipe para a região da Califórnia e incluir todos os gerentes de loja nessa região, juntamente com o gerente regional dessa região.

> [!div class="mx-tdBreakAll"]
>| Tipo de modelo| TemplateId | Propriedades que vêm com este modelo |
>| ------------------|- |----------------------------------------------------- |
>| Varejo para Gerentes| `retailManagerCollaboration` |Canais: <ul><li>Geral<li>Operações</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Aprovações</li><li>Inspeção</li><li>Páginas do SharePoint<ul><li>Nossa loja</li></ul></li><li>Tarefas por Planejador e Para Fazer</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Usar os modelos do Teams com o Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Aqui estão os modelos de equipe de varejo pré-criados.

> [!NOTE]
> Um asterisco (*) indica que o modelo é um *modelo conectado do Microsoft 365*. Quando os usuários criam uma equipe usando o modelo, o modelo do SharePoint conectado é aplicado ao site e à equipe. Componentes do SharePoint, como páginas, listas e integrações do Power Platform, são adicionados automaticamente e fixados como guias para o canal Geral na equipe. Os usuários podem editar essas páginas e listas diretamente de dentro do Teams.
>
> Para saber mais sobre modelos do SharePoint, consulte [Aplicar e personalizar modelos de site do SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Gerenciar uma Loja*

Use este modelo para criar uma equipe para cada local de repositório de varejo em sua organização.

> [!div class="mx-tdBreakAll"]
>| Tipo de modelo | TemplateId | Canais de modelo |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Varejo - <br>Loja | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| Canais <ul><li>Geral</li><li>Shift Handoff</li><li>Preparação da Loja</li><li>Aprendizado</li></ul>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Pública</li></ul> <br>Permissões de membro <ul><li>Não é possível criar, atualizar ou excluir canais </li><li>Não é possível adicionar ou remover aplicativos </li><li>Não é possível criar, atualizar ou remover guias</li><li>Não é possível criar, atualizar ou remover conectores</li><ul>|

Maneiras recomendadas de personalizar o modelo de Loja para sua organização:

- Se sua organização tiver departamentos dentro de cada loja, adicione um canal para cada departamento. Adicionar um canal facilita a comunicação e a colaboração dentro do departamento.

- Se sua organização tiver sites internos (por exemplo, um site do Microsoft Office SharePoint Online), considere fixá-los como guias no canal de equipe relevante.

### <a name="retail-for-managers"></a>Varejo para Gerentes*

Use este modelo para criar uma equipe para um conjunto de gerentes para colaborar entre lojas ou regiões. Por exemplo, se sua organização tiver regiões, você poderá criar uma equipe para a região da Califórnia e incluir todos os gerentes de loja nessa região, juntamente com o gerente regional dessa região.

> [!div class="mx-tdBreakAll"]
>| Tipo de modelo | TemplateId | Canais de modelo |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Varejo - <br>Colaboração do Gerente | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')`| Canais <ul><li>Geral</li><li>Operações</li><li>Aprendizado</li></ul>Propriedades de equipe <ul><li>Visibilidade da equipe definida como Privada</li></ul> <br>Permissões de membro <ul><li>Pode criar, atualizar e excluir canais </li><li>Pode adicionar e remover aplicativos </li><li>Pode criar, atualizar e remover guias</li><li>Pode criar, atualizar e remover conectores</li><ul>|

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

> [!NOTE]
> Se você estiver usando o Microsoft Graph para criar uma equipe de um grupo ou equipe existente do Microsoft 365 usando um modelo conectado do Microsoft 365, o modelo conectado do SharePoint não será aplicado automaticamente ao site ou à equipe. Você precisará aplicar manualmente o modelo de site do SharePoint depois que a equipe for criada. No Teams, acesse a equipe, selecione **Mais opções** no canto superior direito > **Abrir no SharePoint**. Em seguida, escolha **Configurações** > **Aplicar um modelo de site** e selecione o modelo de site correspondente.

## <a name="related-articles"></a>Artigos relacionados

- [Introdução aos modelos de equipe no Centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar uma equipe a partir de um modelo](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introdução aos modelos de equipe usando Microsoft Graph](get-started-with-teams-templates.md)