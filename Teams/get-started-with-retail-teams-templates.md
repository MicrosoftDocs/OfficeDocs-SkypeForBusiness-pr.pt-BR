---
title: Introdução aos modelos do Teams no varejo
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar modelos de equipes para criar as estruturas de equipe projetadas para atender às necessidades do revendedor.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e463061dca0633480124bbe91fb2e8e6f9f926f6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245742"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Introdução aos modelos do Teams no varejo 

Modelos de equipes permitem que você rapidamente e criar facilmente equipes, fornecendo um modelo predefinido de configurações, canais e pré-instaladas apps.

Modelos de equipes têm pré-criados definições de estruturas de equipe projetadas levando em consideração as necessidades do revendedor. Você pode usar modelos de equipes para criar rapidamente os tipos de equipes que funcionam bem para varejistas e implantação-los em sua organização. Você também pode estender os modelos de equipes para criar equipes que são adaptadas às suas necessidades organizacionais específicas.

Neste artigo, apresentaremos cada um dos modelos de equipes e como é recomendável usá-los.

Este artigo é para você, se você é responsável pelo planejamento, implantação e gerenciamento de várias equipes em toda a organização de varejo.

Para saber mais sobre a equipe modelos em geral, consultem [Introdução ao modelos de equipes](get-started-with-teams-templates.md).

## <a name="store-template"></a>Modelo do repositório

O modelo do repositório é ideal para a criação de uma equipe para representar um local do repositório de varejo individuais. Usando o modelo do repositório, você pode criar uma equipe para cada local do repositório de varejo em sua organização.

| Tipo de modelo base | baseTemplateId | Propriedades que acompanham este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo- <br>Repositório | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canais <ul><li>Desloca da entrega\*</li><li>Aprendizado\*</li></ul>\*Canais de auto-favorited<br><br>Propriedades da equipe <ul><li>Visibilidade da equipe pública</li></ul> <br>Permissões de membro <ul><li>Não é possível criar/atualizar/excluir canais </li><li>Não é possível adicionar/remover aplicativos </li><li>Não é possível criar/atualizar/remover guias</li><li>Não é possível criar/atualizar/remover conectores</li><ul>|
||||

Recomendado maneiras para personalizar o modelo de repositório para a sua organização:

- Se sua organização tiver departamentos dentro de cada loja, adicione um canal para cada departamento. Isso irá facilitar a comunicação e colaboração dentro do departamento.

- Se sua organização tiver quaisquer sites internos (por exemplo, um site do SharePoint), considere a possibilidade de fixação-las como guias no canal equipe relevante. Consulte [guia de Introdução com modelos de equipes](get-started-with-teams-templates.md) para obter instruções.

## <a name="manager-collaboration-template"></a>Modelo do Gerenciador de colaboração

O modelo de colaboração do Gerenciador está outro precisa de um dos modelos de equipes projetados levando em consideração revendedor. O modelo de colaboração Manager é ideal para a criação de uma equipe para um conjunto de gerentes para colaborar nas repositórios/regiões, etc. Por exemplo, se sua organização tiver regiões, você pode criar uma equipe de colaboração do gerente para a região da Califórnia e incluem todos os gerentes de armazenamento na região, bem como o gerente regional para essa região.

| Tipo de modelo base | baseTemplateId | Propriedades que acompanham este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Varejo- <br>Repositório | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canais <ul><li>Operações\*</li><li>Aprendizado\*</li></ul>\*Canais de auto-favorited<br><br>Propriedades da equipe <ul><li>Visibilidade da equipe definida como privado</li></ul> <br>Permissões de membro <ul><li>Pode criar/atualizar/excluir canais </li><li>Pode adicionar/remover aplicativos </li><li>Pode criar/atualizar/remover guias</li><li>Pode criar/atualizar/remover conectores</li><ul>|
||||

Recomendado maneiras para personalizar o modelo do Gerenciador de colaboração para sua organização:

- Se sua organização tiver quaisquer sites internos (por exemplo, um site do SharePoint) que são relevantes para gerentes, considere a possibilidade de fixação-las como guias em um canal de equipe relevante (consulte a documentação [aqui](get-started-with-teams-templates.md) para obter instruções).