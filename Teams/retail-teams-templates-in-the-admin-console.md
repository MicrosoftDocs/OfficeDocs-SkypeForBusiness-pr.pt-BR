---
title: Usar modelos de varejo do teams no centro de administração
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar os modelos do teams para criar estruturas de equipe projetadas para as necessidades do revendedor fornecendo configurações, canais e aplicativos pré-instalados predefinidos usando o centro de administração.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40e21687aa3d14b0cb9d51d4ba5f856eada3c538
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424561"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>Usar modelos de varejo do teams no centro de administração

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Os modelos de equipe permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Os modelos de equipe têm definições predefinidas de estruturas de equipe projetadas com base nas necessidades do revendedor. Você pode usar modelos do teams para criar rapidamente os tipos de equipes que funcionam bem para varejistas e implantá-las em toda a organização. Você também pode estender os modelos de equipe para criar equipes que sejam adequadas às suas necessidades organizacionais específicas.

Neste artigo, apresentaremos cada um dos modelos de equipe e como recomendamos usá-los.

Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização de varejo. Presumimos que você já tenha implantado o serviço do Microsoft Teams em sua organização. Se você ainda não distribuiu o Microsoft Teams, comece lendo o guia [como implantar o Microsoft Teams](How-to-roll-out-teams.md).

Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](get-started-with-teams-templates-in-the-admin-console.md)do Microsoft Teams.

## <a name="organize-a-store"></a>Organizar uma loja

Reúna seus funcionários de varejo em uma experiência central para gerenciar tarefas, compartilhar documentos e solucionar problemas com o cliente. Integre aplicativos adicionais para simplificar o início da mudança & processos finais.

| Tipo de modelo base |baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------|-- |----------------------------------------------------- |
|Organizar uma loja| `retailStore`|Canais <ul><li>Geral<li>Deslocar entrega</li><li>Aprendizagem</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>Colaboração do gerente

O modelo de colaboração do gerente é ideal para criar uma equipe para um conjunto de gerentes colaborar em lojas/regiões etc. Por exemplo, se a sua organização tiver regiões, você pode criar uma equipe de colaboração do gerente para a região da Califórnia e incluir todos os gerentes da loja nessa região, bem como o gerente regional dessa região.

| Tipo de modelo base| baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------|- |----------------------------------------------------- |
|Colaboração do gerente de varejo|`retailManagerCollaboration` |Canais <ul><li>Geral<li>Operações</li><li>Aprendizagem</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
||||
