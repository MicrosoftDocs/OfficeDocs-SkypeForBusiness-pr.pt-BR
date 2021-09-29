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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9273f8519fd7aeea90ff35f49ca0d6986afa2d59
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991100"
---
# <a name="use-financial-team-templates"></a>Usar modelos de equipe financeira

Os modelos de equipe no Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo uma estrutura de equipe predefinida de configurações, canais e aplicativos pré-instalados.

Para organizações de serviços financeiros, os modelos de equipe podem ser especialmente poderosos, pois ajudam você a implantar rapidamente equipes consistentes em sua organização. Os modelos também ajudam a equipe a se orientar sobre como usar efetivamente o Teams.

O Teams inclui modelos projetados para organizações de serviços financeiros. Use esses modelos pré-criados para criar rapidamente equipes para que a equipe se comunique e colabore. Neste artigo, apresentamos cada um desses modelos e recomendamos como usá-los.

A maneira como você gerencia e trabalha com modelos de equipe depende se você é um administrador ou desenvolvedor.

|Se você for: | Em seguida, você: |
| ---- | --------- |
| Um administrador ou profissional de TI |[Gerenciar modelos de equipe no centro de administração do Teams](#manage-team-templates-in-the-teams-admin-center). Exiba modelos de equipe e aplique políticas de modelos para controlar quais modelos sua equipe pode usar no Teams para criar equipes. |
| Um desenvolvedor | [Use Microsoft Graph](#use-team-templates-with-microsoft-graph) para criar equipes com base em modelos de equipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gerenciar modelos de equipe no centro de administração do Teams

Como administrador, você pode gerenciar modelos de equipe no centro de administração do Microsoft Teams. Aqui, você pode exibir detalhes sobre cada modelo. Você também pode [criar e atribuir políticas de modelos](templates-policies.md) para sua equipe controlar quais modelos eles veem no Teams para [criação de equipes](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c).

Para saber mais sobre modelos de equipe em geral, consulte [Introdução aos modelos de equipe no centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md).

Atualmente, oferecemos os seguintes modelos de equipe pré-criados para organizações de serviços financeiros. Para exibi-los, no painel de navegação esquerdo do Centro de administração do Teams, acesse **Teams** > **Modelos do Teams**.

### <a name="collaborate-within-a-bank-branch"></a>Colaborar em uma filial bancária

Centralize a colaboração entre funcionários da sua agência bancária em conferências, reuniões com clientes, processos de negócios, como colaboração em hipotecas, e mantenha todos informados com comunicados e elogios.

| Tipo de modelo |TemplateId| Propriedades que vêm com este modelo |
| ------------------ |--|----------------------------------------------------- |
|Filial bancária| `CollaborateWithinABankBranch`|Canais: <ul><li>Geral<li>Comunicados</li><li>Insuidades</li><li>Reuniões com clientes</li><li>Pedido de aprovação </li><li>Treinamento</li><li>Desenvolvimento de Habilidades</li><li>Processamento de empréstimos</li><li>Reclamações do cliente</li><li>Parabéns</li><li>Diversão</li><li>Conformidade</li></ul>Aplicativos:<ul><li>Elogio </li><li>Relator de Problemas</li><li>Wiki</li><li>Calendário</li><li>Aprovações</li><li>Boletins</li><li>Ideias</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Usar modelos de equipe com Microsoft Graph

Os desenvolvedores podem usar Microsoft Graph para criar equipes com base em modelos de equipe pré-criados. Para saber mais sobre como usar modelos de equipe com o Microsoft Graph, consulte [ Introdução aos modelos de equipe usando Microsoft Graph](get-started-with-teams-templates.md), [Visão geral da API do Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) e [tipo de recurso teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="bank-branch"></a>Filial bancária

Centralize a colaboração entre funcionários da sua agência bancária em conferências, reuniões com clientes, processos de negócios, como colaboração em hipotecas, e mantenha todos informados com comunicados e elogios.

| Tipo de modelo |TemplateId| Canais de modelo |
| ------------------ |--|----------------------------------------------------- |
|Filial bancária|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|Geral<br>Comunicados<br>Insuidades<br>Reuniões com clientes<br>Pedido de aprovação<br>Treinamento<br>Desenvolvimento de Habilidades<br>Processamento de empréstimos<br>Reclamações do cliente<br>Parabéns<br>Diversão<br>Conformidade|
||||

> [!NOTE]
> Para obter modelos adicionais que se aplicam à organização de serviços financeiros, consulte [Modelos de equipe criados no Microsoft Graph para pequenas e médias empresas](smb-templates.md).