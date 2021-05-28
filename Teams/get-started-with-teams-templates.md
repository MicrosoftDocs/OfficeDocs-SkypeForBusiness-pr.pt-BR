---
title: Começar a usar modelos de equipe usando o Microsoft Graph
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar modelos de equipe no Microsoft Graph criar espaços de colaboração com canais para diferentes tópicos e pré-instalar aplicativos para fornecer conteúdo e serviços.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fdee4dc55d0922796e66ece87b535b953ecf1580
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684538"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Começar a usar modelos de equipe usando o Microsoft Graph

> [!NOTE]
> Atualmente, os modelos de equipe não suportam a criação de canais privados. A criação de canal privado não está incluída nas definições de modelo.

Modelos de equipe são definições pré-criadas da estrutura de uma equipe projetada em torno de uma necessidade de negócios ou projeto. Você pode [criar seu próprio modelo no console de administração.](get-started-with-teams-templates-in-the-admin-console.md) Com o Microsoft Graph, você usa os modelos pré-construídos. Você pode usar modelos de equipe para criar rapidamente espaços de colaboração com canais para diferentes tópicos e pré-instalar aplicativos para puxar conteúdo e serviços críticos de missão. Os modelos de equipe fornecem uma estrutura de equipe predefinida que pode ajudá-lo a criar facilmente equipes consistentes em toda a organização.

Neste artigo, explicaremos as propriedades que podem ser definidas em modelos, quais são os tipos de modelo base e como você pode usar algumas solicitações de exemplo para criar uma equipe a partir de um modelo.

Este artigo é para você se você:

- Responsável pelo planejamento, implantação e gerenciamento de várias equipes em sua organização<br>
- Um desenvolvedor que deseja criar programaticamente uma equipe com canais e aplicativos predefinidos

## <a name="team-template-capabilities"></a>Recursos de modelo de equipe

A maioria das propriedades em uma equipe são incluídas e suportadas por modelos. No momento, há algumas propriedades e recursos que não são suportados. A tabela a seguir fornece um resumo rápido do que está incluído e o que não está incluído nos modelos de equipe.

| **Propriedades de equipe suportadas por modelos de equipe** | **Propriedades de equipe ainda não suportadas por modelos de equipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo base | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações de equipe (por exemplo, membro, convidado, @ menções) | Arquivos e conteúdo |
| Canal favorito automático | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Vamos adicionar mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique se há informações mais atualizadas sobre propriedades com suporte.

## <a name="what-are-base-template-types"></a>O que são tipos de modelo base

Os tipos de modelo base são modelos especiais criados pela Microsoft para setores específicos. Esses modelos base geralmente contêm aplicativos proprietários que não estão disponíveis na loja. Além disso, os modelos base geralmente contêm propriedades de equipe que ainda não são suportadas individualmente em modelos de equipe. Saiba como usar os modelos [de equipe no Microsoft Graph](get-started-with-teams-templates.md).

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais com propriedades adicionais que você gostaria de especificar. Alguns tipos de modelo base contêm propriedades que não podem ser substituídos.

Por padrão, o modelo base é definido como **Standard**, que não contém nenhum aplicativo proprietário adicional ou propriedades especiais. Abaixo está a lista atual de tipos de modelo base disponíveis.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Sem aplicativos e propriedades adicionais |
| Educação -<br>Equipe de Classe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Apps:<ul><li>OneNote Bloco de Anotações de Classe (fixado na **guia Geral)** </li><li>Aplicativo assignments (fixado na **guia Geral)**</li></ul> Propriedades de equipe:<ul><li>Visibilidade de equipe definida como **HiddenMembership** (não pode ser substituído)</li></ul> |
| Educação -<br>Equipe de Equipe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Apps:<ul><li>OneNote Bloco de Anotações de Equipe (fixado na **guia Geral)**</li></ul> |
|Educação -<br>Equipe DO PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<ul><li>OneNote Bloco de anotações PLC (fixado na **guia Geral)**</ul></li>|
| Varejo -<br>Loja | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canais:<ul><li>Mudança de entrega</li><li>Aprendizado</li></ul>Propriedades de equipe<ul><li>Visibilidade da equipe definida como Pública</li></ul>Permissões de membro<ul><li>Impedir que os membros criar, atualizar ou remover canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros criar, atualizar ou remover conectores</li></ul> |
| Varejo -<br>Colaboração do gerente | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canais:<ul><li>Aprendizado</li><li>Operações</li></ul>Propriedades de equipe:<ul><li>Visibilidade da equipe definida como Privada</li></ul>Permissões de membro:<ul><li>Impedir que os membros criar, atualizar ou remover canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros criar, atualizar ou remover conectores</li></ul>|
| Assistência médica -<br>Ward |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canais: <ul><li>Anúncios\*</li><li>Insuidades\*</li><li>Rodadas</li><li>Pessoal\*</li><li>Treinamento\*</li></ul>\*Canais favoritos automáticos |
|Assistência médica -<br>Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canais:<ul><li>Anúncios\*</li><li>Conformidade\*</li><li>Custódia</li><li>Recursos Humanos</li></li><li>Farmácia</li></ul>\*Canal favorito automático|
|||


Use os modelos a seguir para criar equipes no cliente Teams, bem como no Microsoft Graph.


| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adotar Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Canto campeões</li> <li>Formulários de equipe</li></ul> Apps: <ul><li>Wiki</li>  <li>Calendário</li> |
| Gerenciar um projeto |`com.microsoft.teams.template.`<br>`ManageAProject`| Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Recursos</li> <li>Planejamento</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gerenciar um evento|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Orçamento</li> <li>Conteúdo</li><li>Logística</li> <li>Planejamento</li> <li> Marketing e PR</li></ul> Apps:<ul><li>Wiki</li><li>Site</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Funcionários de integração|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Chat de funcionários</li> <li>Treinamento</li></ul>Apps:<ul><li>Wiki</li><li>Comunidades</li></ul>|
|Organizar o help desk| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canais:<ul><li>Geral</li><li>Comunicados</li><li>Perguntas frequentes</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Colabore no atendimento aos pacientes| `healthcareWard `| Canais:<ul><li>Geral</li><li>Comunicados</li><li>Insuidades</li><li>Rodadas</li><li>Estrelada</li><li>Treinamento</li></ul> Apps: <ul><li>Wiki</li>|
| Colaborar em uma crise global ou evento |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canais: <ul><li>Geral<li>Comunicados</li><li>Notícias do mundo</li><li>Continuidade de negócios</li><li>Trabalho remoto</li><li>Comunicados internos</li><li>Comunicados externos</li><li>Reclamações de clientes</li><li>Kudos</li><li>Atualização executiva</li></ul>Apps: <ul><li>Elogio</li><li>Wiki</li><li>Site</li></ul>|
|Colaborar em uma filial bancária| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canais: <ul><li>Geral<li>Comunicados</li><li>Insuidades</li><li>Reuniões do cliente</li><li>Coaching</li><li>Desenvolvimento de habilidades</li><li>Processamento de empréstimos</li><li>Reclamações de clientes</li><li>Kudos</li><li>Material divertido</li><li>Conformidade</li></ul>|
|Coordenar a resposta a incidentes| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canais: <ul><li>Geral<li>Comunicados</li><li>Logística</li><li>Planejamento</li><li>Recuperação</li><li>Urgente</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital| `healthcareHospita`l |Canais: <ul><li>Geral<li>Comunicados</li><li>Conformidade</li><li>Custódia</li><li>Recursos humanos</li><li>Farmácia</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Organizar uma store| `retailStore` |Canais: <ul><li>Geral<li>Mudança de entrega</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Wiki</li></ul>|
|Qualidade e segurança |`com.microsoft.teams.`<br>`template.QualitySafety`|Canais: <ul><li>Geral<li>Comunicados</li><li>Linha 1</li><li>Linha 2</li><li>Linha 3</li><li>Segurança</li><li>Treinamento</li><li>Manutenção</li><li>Material divertido</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Varejo - colaboração do gerente| `retailManagerCollaboration` |Canais: <ul><li>Geral<li>Operações</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Wiki</li></ul>|
||||

Confira [Começar a usar modelos de equipe no Centro de administração](get-started-with-teams-templates-in-the-admin-console.md) para obter mais detalhes.

## <a name="related-topics"></a>Tópicos relacionados

- [Começar a usar modelos de equipe no console de administração](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar uma equipe](/graph/api/team-post?view=graph-rest-beta) (em visualização)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
- [Treinamento de administrador para o Microsoft Teams](itadmin-readiness.md)