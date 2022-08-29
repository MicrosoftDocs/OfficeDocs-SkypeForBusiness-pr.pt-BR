---
title: Introdução aos modelos de equipe usando o Microsoft Graph
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
- m365-frontline
description: Saiba mais sobre os modelos de equipe que estão disponíveis apenas com o Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4251aa0293665b6fd41c66e352ca9c595378259
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397232"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Introdução aos modelos de equipe usando o Microsoft Graph

> [!NOTE]
> Atualmente, os modelos de equipe não dão suporte à criação de canais privados. A criação de canal privado não está incluída nas definições de modelo.

Um modelo de equipe no Microsoft Teams é uma definição da estrutura de uma equipe projetada em torno de uma necessidade de negócios ou projeto. Com modelos de equipe, você pode criar rapidamente e facilmente espaços de colaboração avançados com configurações, canais e aplicativos predefinidos. Os modelos de equipe podem ajudá-lo a implantar equipes consistentes em sua organização.

Com o Microsoft Graph, [você pode criar](/graph/api/resources/teamtemplate?view=graph-rest-beta) seus próprios modelos ou usar os modelos de equipe pré-criados incluídos no Teams para criar equipes. Neste artigo, você aprenderá sobre as propriedades que podem ser definidas em modelos e os modelos pré-criados que estão disponíveis apenas com o Microsoft Graph.

Este artigo é para você se você:

- Responsável por planejar, implantar e gerenciar várias equipes em sua organização<br>
- Um desenvolvedor que deseja criar programaticamente uma equipe com canais e aplicativos predefinidos

## <a name="team-template-capabilities"></a>Funcionalidades de modelo de equipe

A maioria das propriedades em uma equipe é incluída e tem suporte por modelos. Mas há algumas propriedades e recursos que não têm suporte no momento. Aqui está um resumo rápido do que está incluído e do que não está incluído nos modelos de equipe.

| **Propriedades da equipe compatíveis com modelos de equipe** | **Propriedades da equipe ainda não compatíveis com modelos de equipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações da equipe (por exemplo, membro, convidado, @ menções) | Arquivos e conteúdo |
| Canal favorito automático | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Adicionaremos mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique novamente as informações mais atualizadas sobre as propriedades com suporte.

## <a name="pre-built-templates"></a>Modelos pré-criados

Modelos de equipe pré-criados são modelos que criamos para setores específicos. Aqui estão os modelos pré-criados que estão disponíveis apenas com o Microsoft Graph.

| Tipo de modelo | TemplateId | Propriedades que vêm com este modelo |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Sem aplicativos e propriedades adicionais |
| Educação -<br>Equipe de Classe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Apps:<ul><li>Bloco de Anotações de Classe do OneNote (fixado na **guia** Geral) </li><li>Aplicativo atribuições (fixado na **guia** Geral)</li></ul> Propriedades da equipe:<ul><li>Visibilidade da equipe definida **como HiddenMembership** (não pode ser substituída)</li></ul> |
| Educação -<br>Equipe de Equipe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Apps:<ul><li>Bloco de Anotações de Equipe do OneNote (fixado na **guia** Geral)</li></ul> |
|Educação -<br>Equipe plc |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<ul><li>Bloco de Anotações plc do OneNote (fixado na **guia** Geral)</ul></li>|

> [!NOTE]
> Para obter uma lista de modelos pré-criados que você pode usar no cliente do Teams e com o Microsoft Graph, consulte Introdução aos modelos de equipe no [centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="related-articles"></a>Artigos relacionados

- [Introdução aos modelos de equipe no Centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar uma equipe](/graph/api/team-post?view=graph-rest-beta) (em versão prévia)
- [Nova equipe](/powershell/module/teams/New-Team?view=teams-ps)
