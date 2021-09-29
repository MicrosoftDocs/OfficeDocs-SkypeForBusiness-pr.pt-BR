---
title: Começar a usar modelos de equipe usando o Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba mais sobre os modelos de equipe disponíveis apenas com o Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e570faff4ec7138457f7cd52e101a0a3632d64d2
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991110"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Começar a usar modelos de equipe usando o Microsoft Graph

> [!NOTE]
> Atualmente, os modelos de equipe não suportam a criação de canais privados. A criação de canal privado não está incluída nas definições de modelo.

Um modelo de equipe no Microsoft Teams é uma definição da estrutura de uma equipe projetada em torno de uma necessidade de negócios ou projeto. Com modelos de equipe, você pode criar espaços de colaboração rich com configurações, canais e aplicativos predefinidos. Os modelos de equipe podem ajudá-lo a implantar equipes consistentes em sua organização.

Com o Microsoft Graph, você usa os modelos de equipe pré-construídos que estão incluídos Teams criar equipes. Neste artigo, você aprenderá sobre as propriedades que podem ser definidas em modelos e os modelos que estão disponíveis apenas com o Microsoft Graph.

Este artigo é para você se você:

- Responsável pelo planejamento, implantação e gerenciamento de várias equipes em sua organização<br>
- Um desenvolvedor que deseja criar programaticamente uma equipe com canais e aplicativos predefinidos

## <a name="team-template-capabilities"></a>Recursos de modelo de equipe

A maioria das propriedades em uma equipe são incluídas e suportadas por modelos. No momento, há algumas propriedades e recursos que não são suportados. Aqui está um resumo rápido do que está incluído e o que não está incluído nos modelos de equipe.

| **Propriedades de equipe suportadas por modelos de equipe** | **Propriedades de equipe ainda não suportadas por modelos de equipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações de equipe (por exemplo, membro, convidado, @ menções) | Arquivos e conteúdo |
| Canal favorito automático | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Vamos adicionar mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique se há informações mais atualizadas sobre propriedades com suporte.

## <a name="pre-built-templates"></a>Modelos pré-construídos

Modelos de equipe pré-criados são modelos criados para setores específicos. Aqui estão os modelos pré-construídos que estão disponíveis apenas com o Microsoft Graph.

| Tipo de modelo | TemplateId | Propriedades que vêm com este modelo |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Sem aplicativos e propriedades adicionais |
| Educação -<br>Equipe de Classe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Apps:<ul><li>OneNote Bloco de Anotações de Classe (fixado na **guia Geral)** </li><li>Aplicativo assignments (fixado na **guia Geral)**</li></ul> Propriedades de equipe:<ul><li>Visibilidade de equipe definida como **HiddenMembership** (não pode ser substituído)</li></ul> |
| Educação -<br>Equipe de Equipe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Apps:<ul><li>OneNote Bloco de Anotações de Equipe (fixado na **guia Geral)**</li></ul> |
|Educação -<br>Equipe DO PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<ul><li>OneNote Bloco de anotações PLC (fixado na **guia Geral)**</ul></li>|

> [!NOTE]
> Para obter uma lista de modelos pré-construídos que você pode usar no cliente Teams e com o Microsoft Graph, consulte Get started with [team templates in the Teams admin center](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="related-articles"></a>Artigos relacionados

- [Começar a usar modelos de equipe no Teams de administração](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar uma equipe](/graph/api/team-post?view=graph-rest-beta) (em visualização)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
