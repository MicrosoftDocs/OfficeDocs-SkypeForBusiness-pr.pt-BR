---
title: Introdução aos modelos do Microsoft Teams usando o Microsoft Graph
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
description: Saiba como usar modelos do teams no Microsoft Graph para criar espaços de colaboração com canais para diferentes tópicos e aplicativos pré-instalação para fornecer conteúdo e serviços.
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
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Introdução aos modelos do Microsoft Teams usando o Microsoft Graph

> [!NOTE]
> Atualmente, os modelos de equipe não dão suporte à criação de canais particulares. A criação do canal privado não está incluída nas definições do modelo.

Os modelos de equipe são definições predefinidas da estrutura de uma equipe projetada em torno de uma necessidade ou projeto comercial. Você pode [criar seu próprio modelo no console de administração](get-started-with-teams-templates-in-the-admin-console.md). Com o Microsoft Graph, você usa os modelos predefinidos. Você pode usar modelos de equipe para criar rapidamente espaços de colaboração avançados com canais para diferentes tópicos e aplicativos pré-instalar para extrair conteúdo e serviços de missão crítica. Os modelos de equipe fornecem uma estrutura de equipe predefinida que pode ajudá-lo a criar facilmente equipes consistentes em toda a sua organização.

Neste artigo, explicaremos as propriedades que podem ser definidas em modelos, quais tipos de modelo básico são e como você pode usar algumas solicitações de exemplos para criar uma equipe a partir de um modelo.

Este artigo é para você, se estiver:

- Responsável por planejar, implantar e gerenciar várias equipes em toda a organização<br>
- Um desenvolvedor que queira criar programaticamente uma equipe com canais e aplicativos predefinidos

## <a name="teams-template-capabilities"></a>Recursos de modelos de equipes

A maioria das propriedades em uma equipe é incluída e suportada pelos modelos. Mas há algumas propriedades e recursos que não têm suporte no momento. A tabela a seguir fornece um resumo rápido do que está incluído e o que não está incluído nos modelos do teams.

| **Propriedades da equipe com suporte nos modelos de equipe** | **Propriedades da equipe ainda não são compatíveis com os modelos do teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo base | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações da equipe (por exemplo, membro, convidado, @ menção) | Arquivos e conteúdo |
| Canal de favoritos automático | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Adicionaremos mais recursos de modelo em versões futuras do Microsoft Teams, portanto verifique as informações mais atualizadas sobre as propriedades com suporte.

## <a name="what-are-base-template-types"></a>O que são tipos de modelo base

Tipos de modelo básico são modelos especiais criados pela Microsoft para indústrias específicas. Esses modelos básicos geralmente contêm aplicativos proprietários que não estão disponíveis na loja. Além disso, os modelos básicos geralmente contêm propriedades de equipe que ainda não têm suporte individual nos modelos do teams. Saiba como usar os [modelos de equipe no Microsoft Graph](get-started-with-teams-templates.md).

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais por propriedades adicionais que gostaria de especificar. Alguns tipos de modelo básico contêm propriedades que não podem ser substituídas.

Por padrão, o modelo base é definido como **padrão** , que não contém nenhum aplicativo proprietário adicional ou propriedades especiais. Abaixo está a lista atual de tipos de modelo base disponíveis.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Sem aplicativos e propriedades adicionais |
| Treinamento<br>Equipe de classe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Aplicativo<ul><li>Bloco de anotações de classe do OneNote (fixado na guia **geral** ) </li><li>Aplicativo atribuições (fixadas na guia **geral** )</li></ul> Propriedades da equipe:<ul><li>Visibilidade da equipe definida como **HiddenMembership** (não pode ser substituída)</li></ul> |
| Treinamento<br>Equipe da equipe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Aplicativo<ul><li>Bloco de anotações de equipe do OneNote (fixado na guia **geral** )</li></ul> |
|Treinamento<br>Equipe de PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Aplicativo<ul><li>Bloco de anotações de PLC do OneNote (fixado na guia **geral** )</ul></li>|
| Varejo<br>Repositório | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canais<ul><li>Deslocar entrega</li><li>Aprendizagem</li></ul>Propriedades da equipe<ul><li>Visibilidade da equipe definida como Public</li></ul>Permissões de membro<ul><li>Impedir que os membros criem, atualizem ou removam canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros criem, atualizem ou removam conectores</li></ul> |
| Varejo<br>Colaboração do gerente | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canais<ul><li>Aprendizagem</li><li>Operações</li></ul>Propriedades da equipe:<ul><li>Visibilidade da equipe definida como particular</li></ul>Permissões de membro:<ul><li>Impedir que os membros criem, atualizem ou removam canais</li><li>Impedir que os membros adicionem ou removam aplicativos</li><li>Impedir que os membros criem, atualizem ou removam conectores</li></ul>|
| Intensivo<br>Flecha |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canais <ul><li>Comunicados\*</li><li>Huddles\*</li><li>Arredonda</li><li>Especificam\*</li><li>Treinamento\*</li></ul>\*Canais de favoritos automáticos |
|Intensivo<br>Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canais<ul><li>Comunicados\*</li><li>Conformidade\*</li><li>Custodial</li><li>Recursos humanos</li></li><li>Farmácia</li></ul>\*Canal de preferência automática|
|||


Use os modelos a seguir para criar equipes no cliente do Teams e no Microsoft Graph.


| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adotar o Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canais <ul><li>Geral</li> <li>Comunicados</li> <li>Canto dos Campeões</li> <li>Formulários de equipe</li></ul> Aplicativo <ul><li>Wiki</li>  <li>Calendário</li> |
| Gerenciar um projeto |`com.microsoft.teams.template.`<br>`ManageAProject`| Canais <ul><li>Geral</li> <li>Comunicados</li> <li>Recursos</li> <li>Planejamento</li></ul> Aplicativo<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gerenciar um evento|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canais <ul><li>Geral</li> <li>Comunicados</li> <li>Orçamento</li> <li>Conteúdo</li><li>Logística</li> <li>Planejamento</li> <li> Marketing e PR</li></ul> Aplicativo<ul><li>Wiki</li><li>Site</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Funcionários onboard|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canais <ul><li>Geral</li> <li>Comunicados</li> <li>Chat de funcionários</li> <li>Treinamento</li></ul>Aplicativo<ul><li>Wiki</li><li>Às</li></ul>|
|Organizar o Help Desk| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canais<ul><li>Geral</li><li>Comunicados</li><li>Perguntas frequentes</li></ul>Aplicativo<ul><li>Wiki</li><li>OneNote</li></ul> |
| Colabore no atendimento ao paciente| `healthcareWard `| Canais<ul><li>Geral</li><li>Comunicados</li><li>Huddles</li><li>Arredonda</li><li>Especificam</li><li>Treinamento</li></ul> Aplicativo <ul><li>Wiki</li>|
| Colaborar em uma crise global ou em um evento |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canais <ul><li>Geral<li>Comunicados</li><li>Notícias do mundo</li><li>Continuidade de negócios</li><li>Trabalho remoto</li><li>Comms internas</li><li>Comentários externos</li><li>Reclamações do cliente</li><li>Parabéns</li><li>Atualização executiva</li></ul>Aplicativo <ul><li>Elogia</li><li>Wiki</li><li>Site</li></ul>|
|Colaborar dentro de um Branch bancário| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canais <ul><li>Geral<li>Comunicados</li><li>Huddles</li><li>Reuniões do cliente</li><li>Treina</li><li>Desenvolvimento de habilidades</li><li>Processamento de empréstimos</li><li>Reclamações do cliente</li><li>Parabéns</li><li>Coisas divertidas</li><li>Conformidade</li></ul>|
|Coordenar resposta a incidentes| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canais <ul><li>Geral<li>Comunicados</li><li>Logística</li><li>Planejamento</li><li>Automatiza</li><li>Urgente</li></ul> Aplicativo <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital| `healthcareHospita`t |Canais <ul><li>Geral<li>Comunicados</li><li>Conformidade</li><li>Custodial</li><li>Recursos humanos</li><li>Farmácia</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
|Organizar uma loja| `retailStore` |Canais <ul><li>Geral<li>Deslocar entrega</li><li>Aprendizagem</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
|Qualidade e segurança |`com.microsoft.teams.`<br>`template.QualitySafety`|Canais <ul><li>Geral<li>Comunicados</li><li>Linha 1</li><li>Linha 2</li><li>Linha 3</li><li>Segurança</li><li>Treinamento</li><li>Manutenção</li><li>Coisas divertidas</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
|Colaboração do gerente de varejo| `retailManagerCollaboration` |Canais <ul><li>Geral<li>Operações</li><li>Aprendizagem</li></ul> Aplicativo <ul><li>Wiki</li></ul>|
||||

Para obter mais detalhes, consulte [introdução aos modelos de equipe no centro de administração](get-started-with-teams-templates-in-the-admin-console.md) .

## <a name="related-topics"></a>Tópicos relacionados

- [Introdução aos modelos do Microsoft Teams no console de administração](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (na visualização)
- [New-Team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Treinamento de administrador para o Microsoft Teams](itadmin-readiness.md)