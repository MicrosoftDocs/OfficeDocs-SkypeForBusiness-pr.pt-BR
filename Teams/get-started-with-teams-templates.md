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
- tier2
- highpri
description: Saiba mais sobre os modelos de equipe que estão disponíveis apenas com o Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4560e5845b2f9beabc8227d79bebc889c9d42c37
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131120"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Introdução aos modelos de equipe usando o Microsoft Graph

> [!NOTE]
> Atualmente, os modelos de equipe não dão suporte à criação de canais privados. A criação de canal privado não está incluída nas definições de modelo.

Um modelo de equipe no Microsoft Teams é uma definição da estrutura de uma equipe projetada em torno de uma necessidade ou projeto de negócios. Com modelos de equipe, você pode criar rapidamente e facilmente espaços de colaboração avançados com configurações, canais e aplicativos predefinidos. Modelos de equipe podem ajudá-lo a implantar equipes consistentes em sua organização.

Com o Microsoft Graph, você pode [criar seus próprios modelos](/graph/api/resources/teamtemplate?view=graph-rest-beta) ou usar os modelos de equipe pré-criados que estão incluídos no Teams para criar equipes. Neste artigo, você aprenderá sobre as propriedades que podem ser definidas em modelos e os modelos pré-criados que estão disponíveis apenas com o Microsoft Graph.

Este artigo é para você se você estiver:

- Responsável por planejar, implantar e gerenciar várias equipes em toda a sua organização<br>
- Um desenvolvedor que deseja criar programaticamente uma equipe com canais e aplicativos predefinidos

## <a name="team-template-capabilities"></a>Recursos de modelo de equipe

A maioria das propriedades em uma equipe é incluída e suportada por modelos. Mas há algumas propriedades e recursos que não têm suporte no momento. Aqui está um resumo rápido do que está incluído e o que não está incluído nos modelos de equipe.

| **Propriedades da equipe com suporte por modelos de equipe** | **As propriedades da equipe ainda não têm suporte por modelos de equipe** |
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
> Adicionaremos mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique as informações mais atualizadas sobre propriedades com suporte.

## <a name="pre-built-templates"></a>Modelos pré-criados

Modelos de equipe pré-criados são modelos que criamos para setores específicos. Aqui estão os modelos pré-criados que estão disponíveis apenas com o Microsoft Graph.

| Tipo de modelo | TemplateId | Propriedades que vêm com este modelo |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Nenhum aplicativo e propriedades adicionais |
| Educação-<br>Equipe de Classe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Apps:<ul><li>Bloco de Anotações de Classe do OneNote (fixado na guia **Geral** ) </li><li>Aplicativo de atribuições (fixado na guia **Geral** )</li></ul> Propriedades da equipe:<ul><li>Visibilidade da equipe definida como **HiddenMembership** (não pode ser substituída)</li></ul> |
| Educação-<br>Equipe da equipe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Apps:<ul><li>Notebook do OneNote Staff (fixado na guia **Geral** )</li></ul> |
|Educação-<br>Equipe PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<ul><li>Notebook do OneNote PLC (fixado na guia **Geral** )</ul></li>|

> [!NOTE]
> Para obter uma lista de modelos pré-criados que você pode usar no cliente do Teams e com o Microsoft Graph, confira [Introdução aos modelos de equipe no centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="related-articles"></a>Artigos relacionados

- [Introdução aos modelos de equipe no Centro de administração do Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar uma equipe](/graph/api/team-post?view=graph-rest-beta) (em versão prévia)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
