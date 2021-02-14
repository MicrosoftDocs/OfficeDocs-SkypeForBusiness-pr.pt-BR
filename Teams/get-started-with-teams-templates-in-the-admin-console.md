---
title: Usar modelos do Teams no centro de administração
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar modelos do Teams para criar espaços de colaboração com canais para diferentes tópicos usando modelos pré-instalados.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ad35b874f3f11a7e71d61c63cb90a1945c7cc85
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662646"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>Começar a usar modelos do Teams no centro de administração

**Os modelos personalizados ainda não têm suporte para clientes EDU.**

> [!NOTE]
> Atualmente, os modelos do Teams não são suportados para a criação de canais privados. A criação de canal privado não está incluída nas definições de modelo.

Os modelos do Teams são definições predefinida da estrutura de uma equipe projetada em torno de uma necessidade comercial ou projeto. Use modelos predefinido ou crie seu próprio modelo. Os modelos do Teams permitem criar rapidamente espaços de colaboração com canais para diferentes tópicos e pré-instalar aplicativos para usar conteúdo e serviços essenciais. Os modelos do Teams fornecem uma estrutura de equipe predefinida que pode ajudá-lo a criar facilmente equipes consistentes em toda a organização. Atualmente, você pode criar uma equipe a partir de um modelo no Teams ou usando o [Microsoft Graph.](get-started-with-teams-templates.md)

Este artigo descreve as propriedades que podem ser definidas em modelos, quais são os tipos de modelo base e como você pode usar algumas solicitações de exemplo para criar uma equipe a partir de um modelo.

Este artigo é para você se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização

## <a name="teams-template-capabilities"></a>Recursos de modelo do Teams

A maioria das propriedades em uma equipe são incluídas e suportadas por modelos. Mas há algumas propriedades e recursos que não têm suporte no momento. A tabela a seguir fornece um resumo rápido do que está incluído e do que não está incluído nos modelos do Teams.

| **Propriedades da equipe com suporte por modelos do Teams** | **As propriedades da equipe ainda não são suportadas por modelos do Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo base | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações da equipe (por exemplo, membro, convidado, @ menções) | Arquivos e conteúdo |
| Autofavorite channel | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Adicionaremos mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique novamente as informações mais atualizadas sobre propriedades com suporte.

## <a name="what-are-base-template-types"></a>O que são tipos de modelo base

Os tipos de modelo base são modelos especiais que a Microsoft criou para setores específicos. Esses modelos base geralmente contêm aplicativos proprietários que não estão disponíveis na loja de aplicativos.

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais com propriedades adicionais que você gostaria de especificar. Alguns tipos de modelo base contêm propriedades que não podem ser substituídos.

> [!NOTE]
> Os modelos de base predefinido fornecidos no Microsoft Teams podem ser duplicados, mas não editados.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adotar o Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canais: <ul><li>Geral</li> <li>Anúncios</li> <li>Canto dos campeões</li> <li>Formulários de equipe</li></ul> Apps: <ul><li>Wiki</li>  <li>Calendário</li> |
| Gerenciar um projeto |`com.microsoft.teams.template.ManageAProject`| Canais: <ul><li>Geral</li> <li>Anúncios</li> <li>Recursos</li> <li>Planejamento</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>Listas</li>  </ul> |
| Gerenciar um evento|`com.microsoft.teams.template.ManageAnEvent` | Canais: <ul><li>Geral</li> <li>Anúncios</li> <li>Orçamento</li> <li>Conteúdo</li><li>Logística</li> <li>Planejamento</li> <li> Marketing e relações públicas</li></ul> Apps:<ul><li>Wiki</li><li>Site</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Funcionários de integração|`com.microsoft.teams.template.OnboardEmployees` | Canais: <ul><li>Geral</li> <li>Anúncios</li> <li>Chat de funcionários</li> <li>Treinamento</li></ul>Apps:<ul><li>Wiki</li><li>Comunidades</li><li>Planner</li></ul>|
|Organizar o help desk| `com.microsoft.teams.template.OrganizeHelpDesk`|Canais:<ul><li>Geral</li><li>Anúncios</li><li>Perguntas frequentes</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>Elogios</li></ul> |
| Colaborar no atendimento ao paciente| `healthcareWard`| Canais:<ul><li>Geral</li><li>Anúncios</li><li>Desaconsudores</li><li>Rodadas</li><li>Pessoal</li><li>Treinamento</li></ul> Apps: <ul><li>Wiki</li><li>Listas  </li></ul>|
| Colaborar em uma situação ou uma situação de crise globais |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canais: <ul><li>Geral<li>Anúncios</li><li>Notícias do mundo</li><li>Continuidade de negócios</li><li>Trabalho remoto</li><li>Comunicados internos</li><li>Comunicados externos</li><li>Solicitação de aprovação</li><li>Reclamações de clientes</li><li>Kudos</li><li>Atualização executiva</li></ul>Apps: <ul><li>Elogios</li><li>Wiki</li><li>Site</li><li>Planner</li></ul>|
|Colaborar em uma ramificação bancária| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canais: <ul><li>Geral<li>Anúncios</li><li>Desaconsudores</li><li>Reuniões de clientes</li><li>Solicitação de Aprovações </li><li>Coaching</li><li>Desenvolvimento de habilidades</li><li>Processamento de empréstimos</li><li>Reclamações de clientes</li><li>Kudos</li><li>Coisas divertidas</li><li>Conformidade</li></ul>Apps:<ul><li>Elogios </li></ul>|
|Coordenar resposta a incidentes| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canais: <ul><li>Geral<li>Anúncios</li><li>Logística</li><li>Planejamento</li><li>Recuperação</li><li>Urgente</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Hospital| `healthcareHospital` |Canais: <ul><li>Geral</li><li>Anúncios</li><li>Conformidade</li><li>Custódia</li><li>Recursos humanos</li><li>Farmácia</li></ul> Apps: <ul><li>Wiki</li><li>Listas  </li></ul>|
|Organizar uma loja| `retailStore` |Canais: <ul><li>Geral<li>Shift handoff</li><li>Aprendizagem</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li></ul>|
|Qualidade e segurança |`com.microsoft.teams.template.QualitySafety`|Canais: <ul><li>Geral<li>Anúncios</li><li>Linha 1</li><li>Linha 2</li><li>Linha 3</li><li>Segurança</li><li>Treinamento</li><li>Manutenção</li><li>Coisas divertidas</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li></ul>|
|Varejo – colaboração de gerente| `retailManagerCollaboration` |Canais: <ul><li>Geral<li>Operações</li><li>Aprendizagem</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li></ul>|
||||

Para obter mais informações sobre as categorias de modelo, consulte as seguintes categorias:

- [Modelos financeiros](financial-teams-templates-in-the-admin-console.md)
- [Modelos gerais](general-teams-templates-in-the-admin-console.md)
- [Modelos governamentais](government-teams-templates-in-the-admin-console.md)
- [Modelos de saúde](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modelos de fabricação](manufacturing-teams-templates-in-the-admin-console.md)
- [Modelos de varejo](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Limites de tamanho do modelo

Os modelos são limitados a um número específico de canais, guias e aplicativos.

 > [!Note]
 > Você pode adicionar mais canais, guias e aplicativos à equipe depois que ele foi criado a partir de um modelo.

|Recurso | Limite|
|-|-|
|Canais por modelo | 15 |
|Guias por canal em um modelo | 20 |
|Aplicativos por modelo | 50|
|||

Consulte [Limites e especificações do Teams](limits-specifications-teams.md) para obter mais informações.

## <a name="related-topics"></a>Tópicos relacionados

- [Criar um modelo de equipe personalizado](create-a-team-template.md)
- [Criar um modelo de equipe a partir de um modelo de equipe existente](create-template-from-existing-template.md)
- [Criar um modelo a partir de uma equipe existente](create-template-from-existing-team.md)
