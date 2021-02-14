---
title: Começar a usar modelos do Teams usando o Microsoft Graph
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
description: Saiba como usar modelos do Teams no Microsoft Graph para criar espaços de colaboração com canais para diferentes tópicos e pré-instalar aplicativos para fornecer conteúdo e serviços.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 484b3ac3fd3545ce306dcb6e3d833bb523df5a86
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772192"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Começar a usar modelos do Teams usando o Microsoft Graph

> [!NOTE]
> Atualmente, os modelos do Teams não são suportados para a criação de canais privados. A criação de canal privado não está incluída nas definições de modelo.

Os modelos do Teams são definições predefinida da estrutura de uma equipe projetada em torno de uma necessidade comercial ou projeto. Você pode [criar seu próprio modelo no console de administração.](get-started-with-teams-templates-in-the-admin-console.md) Com o Microsoft Graph, você usa os modelos predefinido. Você pode usar modelos do Teams para criar rapidamente espaços de colaboração com canais para diferentes tópicos e pré-instalar aplicativos para utilizar conteúdo e serviços essenciais. Os modelos do Teams fornecem uma estrutura de equipe predefinida que pode ajudá-lo a criar facilmente equipes consistentes em toda a organização.

Neste artigo, explicaremos as propriedades que podem ser definidas em modelos, quais são os tipos de modelo base e como você pode usar algumas solicitações de exemplo para criar uma equipe a partir de um modelo.

Este artigo é para você se você:

- Responsável por planejar, implantar e gerenciar várias equipes em sua organização<br>
- Um desenvolvedor que deseja criar programaticamente uma equipe com canais e aplicativos predefinidos

## <a name="teams-template-capabilities"></a>Recursos de modelo do Teams

A maioria das propriedades em uma equipe são incluídas e suportadas por modelos. Mas há algumas propriedades e recursos que não têm suporte no momento. A tabela a seguir fornece um resumo rápido do que está incluído e do que não está incluído nos modelos do Teams.

| **Propriedades da equipe com suporte por modelos do Teams** | **As propriedades da equipe ainda não são suportadas por modelos do Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo base | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações da equipe (por exemplo, membro, convidado, @ menções) | Arquivos e conteúdo |
| Canal favorito automático | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Adicionaremos mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique novamente as informações mais atualizadas sobre propriedades com suporte.

## <a name="what-are-base-template-types"></a>O que são tipos de modelo base

Os tipos de modelo base são modelos especiais que a Microsoft criou para setores específicos. Esses modelos base geralmente contêm aplicativos proprietários que não estão disponíveis na loja. Além disso, os modelos base geralmente contêm propriedades da equipe que ainda não têm suporte individual em modelos do Teams. Saiba como usar os modelos [de equipe no Microsoft Graph.](get-started-with-teams-templates.md)

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais com propriedades adicionais que você gostaria de especificar. Alguns tipos de modelo base contêm propriedades que não podem ser substituídos.

Por padrão, o modelo base é definido como **Padrão,** que não contém nenhum aplicativo proprietário adicional ou propriedades especiais. Abaixo está a lista atual de tipos de modelo base disponíveis.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Não há propriedades e aplicativos adicionais |
| Educação -<br>Equipe de Classe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Apps:<ul><li>Bloco de Anotações de Classe do OneNote (fixado na **guia** Geral) </li><li>Aplicativo Tarefas (fixado na **guia** Geral)</li></ul> Propriedades da equipe:<ul><li>Visibilidade da equipe definida **como HiddenMembership** (não pode ser substituído)</li></ul> |
| Educação -<br>Equipe de Funcionários | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Apps:<ul><li>Bloco de Anotações de Equipe do OneNote (fixado na **guia** Geral)</li></ul> |
|Educação -<br>Equipe plc |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<ul><li>Bloco de Anotações PLC do OneNote (fixado na **guia** Geral)</ul></li>|
| Varejo –<br>Repositório | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canais:<ul><li>Shift handoff</li><li>Aprendizagem</li></ul>Propriedades da equipe<ul><li>Visibilidade da equipe definida como Pública</li></ul>Permissões de membro<ul><li>Impedir que membros de criar, atualizar ou remover canais</li><li>Impedir que membros adicionem ou removam aplicativos</li><li>Impedir que membros de criar, atualizar ou remover conectores</li></ul> |
| Varejo –<br>Colaboração do gerente | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canais:<ul><li>Aprendizagem</li><li>Operações</li></ul>Propriedades da equipe:<ul><li>Visibilidade da equipe definida como Particular</li></ul>Permissões de membro:<ul><li>Impedir que membros de criar, atualizar ou remover canais</li><li>Impedir que membros adicionem ou removam aplicativos</li><li>Impedir que membros de criar, atualizar ou remover conectores</li></ul>|
| Serviços de saúde -<br>Ward |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canais: <ul><li>Anúncios\*</li><li>Desaconsudores\*</li><li>Rodadas</li><li>Pessoal\*</li><li>Treinamento\*</li></ul>\*Canais favoritos automáticos |
|Serviços de saúde -<br>Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canais:<ul><li>Anúncios\*</li><li>Conformidade\*</li><li>Custódia</li><li>Recursos Humanos</li></li><li>Farmácia</li></ul>\*Canal favorito automático|
|||


Use os modelos a seguir para criar equipes tanto no cliente do Teams quanto no Microsoft Graph.


| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adotar o Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canais: <ul><li>Geral</li> <li>Anúncios</li> <li>Canto dos campeões</li> <li>Formulários de equipe</li></ul> Apps: <ul><li>Wiki</li>  <li>Calendário</li> |
| Gerenciar um projeto |`com.microsoft.teams.template.`<br>`ManageAProject`| Canais: <ul><li>Geral</li> <li>Anúncios</li> <li>Recursos</li> <li>Planejamento</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gerenciar um evento|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canais: <ul><li>Geral</li> <li>Anúncios</li> <li>Orçamento</li> <li>Conteúdo</li><li>Logística</li> <li>Planejamento</li> <li> Marketing e relações públicas</li></ul> Apps:<ul><li>Wiki</li><li>Site</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Funcionários de integração|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canais: <ul><li>Geral</li> <li>Anúncios</li> <li>Chat de funcionários</li> <li>Treinamento</li></ul>Apps:<ul><li>Wiki</li><li>Comunidades</li></ul>|
|Organizar o help desk| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canais:<ul><li>Geral</li><li>Anúncios</li><li>Perguntas frequentes</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Colaborar no atendimento ao paciente| `healthcareWard `| Canais:<ul><li>Geral</li><li>Anúncios</li><li>Desaconsudores</li><li>Rodadas</li><li>Pessoal</li><li>Treinamento</li></ul> Apps: <ul><li>Wiki</li>|
| Colaborar em uma situação ou uma situação de crise globais |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canais: <ul><li>Geral<li>Anúncios</li><li>Notícias do mundo</li><li>Continuidade de negócios</li><li>Trabalho remoto</li><li>Comunicados internos</li><li>Comunicados externos</li><li>Reclamações de clientes</li><li>Kudos</li><li>Atualização executiva</li></ul>Apps: <ul><li>Elogios</li><li>Wiki</li><li>Site</li></ul>|
|Colaborar em uma ramificação bancária| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canais: <ul><li>Geral<li>Anúncios</li><li>Desaconsudores</li><li>Reuniões de clientes</li><li>Coaching</li><li>Desenvolvimento de habilidades</li><li>Processamento de empréstimos</li><li>Reclamações de clientes</li><li>Kudos</li><li>Coisas divertidas</li><li>Conformidade</li></ul>|
|Coordenar resposta a incidentes| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canais: <ul><li>Geral<li>Anúncios</li><li>Logística</li><li>Planejamento</li><li>Recuperação</li><li>Urgente</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital| `healthcareHospita`L |Canais: <ul><li>Geral<li>Anúncios</li><li>Conformidade</li><li>Custódia</li><li>Recursos humanos</li><li>Farmácia</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Organizar uma loja| `retailStore` |Canais: <ul><li>Geral<li>Shift handoff</li><li>Aprendizagem</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Qualidade e segurança |`com.microsoft.teams.`<br>`template.QualitySafety`|Canais: <ul><li>Geral<li>Anúncios</li><li>Linha 1</li><li>Linha 2</li><li>Linha 3</li><li>Segurança</li><li>Treinamento</li><li>Manutenção</li><li>Coisas divertidas</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Varejo – colaboração de gerente| `retailManagerCollaboration` |Canais: <ul><li>Geral<li>Operações</li><li>Aprendizagem</li></ul> Apps: <ul><li>Wiki</li></ul>|
||||

Consulte [Começar a usar modelos do Teams no Centro de administração](get-started-with-teams-templates-in-the-admin-console.md) para obter mais detalhes.

## <a name="related-topics"></a>Tópicos relacionados

- [Começar a usar modelos do Teams no console de administração](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (na visualização)
- [Nova equipe](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Treinamento de administrador para o Microsoft Teams](itadmin-readiness.md)