---
title: Usar modelos de equipe financeira
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Saiba como gerenciar e usar modelos de equipe financeira no centro de administração do Teams e com o Microsoft Graph para criar equipes de forma rápida e fácil para sua organização de serviços financeiros.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 096bab4289d5ac9e81c63f83cd73efd41d98e7be
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198684"
---
# <a name="use-financial-team-templates"></a>Usar modelos de equipe financeira

Os modelos de equipe no Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo uma estrutura de equipe predefinida de configurações, canais e aplicativos pré-instalados.

Para organizações de serviços financeiros, os modelos de equipe podem ser especialmente poderosos, pois ajudam você a implantar rapidamente equipes consistentes em sua organização. Os modelos também ajudam a equipe a se orientar sobre como usar efetivamente o Teams.

O Teams inclui modelos projetados para organizações de serviços financeiros. Use esses modelos pré-criados para criar rapidamente equipes para que a equipe se comunique e colabore. Neste artigo, apresentamos cada um desses modelos e recomendamos como usá-los.

A maneira como você gerencia e trabalha com modelos de equipe depende se você é um administrador ou desenvolvedor.

|Se você estiver: | Em seguida, você: |
| ---- | --------- |
| Um administrador ou profissional de IT |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Um desenvolvedor | [Use Microsoft Graph](#use-team-templates-with-microsoft-graph) para criar equipes com base em modelos de equipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gerenciar modelos de equipe no centro de administração do Teams

Como administrador, você pode gerenciar os modelos de equipe no Centro de administração do Microsoft Teams. Aqui, você pode exibir os detalhes sobre cada modelo. Você também pode [criar e atribuir políticas de modelos](templates-policies.md) para sua equipe controlar quais modelos são vistos no Teams para a [criação de equipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Para saber mais sobre modelos de equipe em geral, consulte [Introdução aos modelos de equipe no Centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md).

Atualmente, oferecemos os seguintes modelos de equipe pré-criados para organizações de serviços financeiros. Para exibi-los, no painel de navegação esquerdo do Centro de administração do Teams, acesse **Teams** > **Modelos do Teams**.

### <a name="collaborate-within-a-bank-branch"></a>Colaborar em uma filial bancária

Centralize a colaboração entre funcionários da sua agência bancária em conferências, reuniões com clientes, processos de negócios, como colaboração em hipotecas, e mantenha todos informados com comunicados e elogios.

| Tipo de modelo |TemplateId| Propriedades que vêm com este modelo |
| ------------------ |--|----------------------------------------------------- |
|Filial bancária| `CollaborateWithinABankBranch`|Canais: <ul><li>Geral<li>Comunicados</li><li>Insuidades</li><li>Reuniões com clientes</li><li>Pedido de aprovação </li><li>Treinamento</li><li>Desenvolvimento de Habilidades</li><li>Processamento de empréstimos</li><li>Reclamações do cliente</li><li>Parabéns</li><li>Diversão</li><li>Conformidade</li></ul>Aplicativos:<ul><li>Elogio </li><li>Relator de Problemas</li><li>Wiki</li><li>Calendário</li><li>Aprovações</li><li>Boletins</li><li>Ideias</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Usar modelos de equipe com Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0&preserve-view=true), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0&preserve-view=true).

### <a name="bank-branch"></a>Filial bancária

Centralize a colaboração entre funcionários da sua agência bancária em conferências, reuniões com clientes, processos de negócios, como colaboração em hipotecas, e mantenha todos informados com comunicados e elogios.

| Tipo de modelo |TemplateId| Canais de modelo |
| ------------------ |--|----------------------------------------------------- |
|Filial bancária|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|Geral<br>Comunicados<br>Insuidades<br>Reuniões com clientes<br>Pedido de aprovação<br>Treinamento<br>Desenvolvimento de Habilidades<br>Processamento de empréstimos<br>Reclamações do cliente<br>Parabéns<br>Diversão<br>Conformidade|
||||

> [!NOTE]
> Para obter modelos de equipe adicionais que se aplicam a organizações de serviços financeiros, consulte [Modelos de equipe criados no Microsoft Graph para pequenas e médias empresas](smb-templates.md).

## <a name="related-articles"></a>Artigos relacionados

- [Introdução aos modelos de equipe no Centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar uma equipe a partir de um modelo](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introdução aos modelos de equipe usando Microsoft Graph](get-started-with-teams-templates.md)