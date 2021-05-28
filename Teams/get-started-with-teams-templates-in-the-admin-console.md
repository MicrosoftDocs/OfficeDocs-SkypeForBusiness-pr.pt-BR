---
title: Usar modelos de equipe no centro de administração
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
description: Saiba como usar modelos de equipe para criar espaços de colaboração com canais para diferentes tópicos usando modelos pré-instalados.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 773b97197a4f233dea9a404d87e669239b3969f6
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684448"
---
# <a name="get-started-with-team-templates-in-the-admin-center"></a>Começar a usar modelos de equipe no centro de administração

**A capacidade de criar modelos personalizados ainda não é suportada para clientes EDU.**

> [!NOTE]
> Canais privados e rótulos de sensibilidade atualmente não são suportados em modelos de equipe. A criação de canal privado não está incluída nas definições de modelo. A opção rótulo de sensibilidade em **Criar equipe a partir do fluxo de** modelos não será aplicada à equipe.

Modelos de equipe são definições pré-criadas da estrutura de uma equipe projetada em torno de uma necessidade de negócios ou projeto. Use modelos pré-construídos ou crie seu próprio modelo. Os modelos de equipe permitem que você crie rapidamente espaços de colaboração com canais para diferentes tópicos e pré-instalar aplicativos para puxar conteúdo e serviços críticos de missão. Os modelos de equipe fornecem uma estrutura de equipe predefinida que pode ajudá-lo a criar facilmente equipes consistentes em toda a organização. Atualmente, você pode criar uma equipe a partir de um modelo em Teams ou usando o [Microsoft Graph](get-started-with-teams-templates.md).

Este artigo descreve os seguintes recursos:

- As propriedades que podem ser definidas em modelos.
- Os tipos de modelo base.
- Como você pode usar algumas solicitações de exemplo para criar uma equipe a partir de um modelo.

Este artigo é para você se você for responsável por planejar, implantar e gerenciar várias equipes em toda a sua organização

## <a name="team-template-capabilities"></a>Recursos de modelo de equipe

A maioria das propriedades em uma equipe são incluídas e suportadas por modelos. No momento, há algumas propriedades e recursos que não são suportados. A tabela a seguir fornece um resumo rápido do que está incluído e o que não está incluído nos modelos de equipe.

| **Propriedades de equipe suportadas por modelos de equipe** | **Propriedades de equipe ainda não suportadas por modelos de equipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo base | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações de equipe (por exemplo, membro, convidado, @ menções) | Arquivos e conteúdo |
| Canal Autofavorite | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Vamos adicionar mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique se há informações mais atualizadas sobre propriedades com suporte.

## <a name="what-are-base-template-types"></a>O que são tipos de modelo base

Os tipos de modelo base são modelos especiais criados pela Microsoft para setores específicos. Esses modelos base geralmente contêm aplicativos proprietários que não estão disponíveis no armazenamento de aplicativos.

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais com mais propriedades que você gostaria de especificar. Alguns tipos de modelo base contêm propriedades que não podem ser substituídos.

> [!NOTE]
> Modelos de base pré-definidos fornecidos Microsoft Teams podem ser duplicados, mas não editados.

| Tipo de modelo base | baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adotar Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Canto campeões</li> <li>Formulários de equipe</li></ul> Apps: <ul><li>Wiki</li>  <li>Calendário</li> |
| Gerenciar um projeto |`com.microsoft.teams.template.ManageAProject`| Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Recursos</li> <li>Planejamento</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>Listas</li>  </ul> |
| Gerenciar um evento|`com.microsoft.teams.template.ManageAnEvent` | Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Orçamento</li> <li>Conteúdo</li><li>Logística</li> <li>Planejamento</li> <li> Marketing e PR</li></ul> Apps:<ul><li>Wiki</li><li>Site</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li> <li>Ideias dos funcionários</li> <li>Repórter de Problemas</li></ul> |
|Funcionários de integração|`com.microsoft.teams.template.OnboardEmployees` | Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Chat de funcionários</li> <li>Treinamento</li></ul>Apps:<ul><li>Wiki</li><li>Comunidades</li><li>Planner</li><li>Ideias dos funcionários</li></ul>|
|Organizar o help desk| `com.microsoft.teams.template.OrganizeHelpDesk`|Canais:<ul><li>Geral</li><li>Comunicados</li><li>Perguntas frequentes</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>Elogio</li><li>Repórter de Problemas</li></ul> |
| Atendimento ao paciente| `healthcareWard`| Canais:<ul><li>Geral</li><li>Comunicados</li><li>Insuidades</li><li>Rodadas</li><li>Estrelada</li><li>Treinamento</li></ul> Apps: <ul><li>Wiki</li><li>Listas  </li><li>Aprovações</li></ul>|
| Colaborar em uma crise global ou evento |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canais: <ul><li>Geral<li>Comunicados</li><li>Notícias do mundo</li><li>Continuidade de negócios</li><li>Trabalho remoto</li><li>Comunicados internos</li><li>Comunicados externos</li><li>Solicitação de aprovações</li><li>Reclamações de clientes</li><li>Kudos</li><li>Atualização executiva</li></ul>Apps: <ul><li>Elogio</li><li>Wiki</li><li>Site</li><li>Planner</li><li>Repórter de Problemas</li></ul>|
|Filial bancária| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canais: <ul><li>Geral<li>Comunicados</li><li>Insuidades</li><li>Reuniões do cliente</li><li>Solicitação de Aprovações </li><li>Coaching</li><li>Desenvolvimento de habilidades</li><li>Processamento de empréstimos</li><li>Reclamações de clientes</li><li>Kudos</li><li>Material divertido</li><li>Conformidade</li></ul>Apps:<ul><li>Elogio </li><li>Repórter de Problemas</li></ul>|
|Resposta a incidentes| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canais: <ul><li>Geral<li>Comunicados</li><li>Logística</li><li>Planejamento</li><li>Recuperação</li><li>Urgente</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li> <li>Aprovações</li> <li>Inspeção</li> </ul>|
|Hospital| `healthcareHospital` |Canais: <ul><li>Geral</li><li>Comunicados</li><li>Conformidade</li><li>Custódia</li><li>Recursos humanos</li><li>Farmácia</li></ul> Apps: <ul><li>Wiki</li><li>Listas  </li></ul>|
|Organizar uma store| `retailStore` |Canais: <ul><li>Geral<li>Mudança de entrega</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Wiki</li><li>Planner</li></ul>|
|Qualidade e segurança |`com.microsoft.teams.template.QualitySafety`|Canais: <ul><li>Geral<li>Comunicados</li><li>Linha 1</li><li>Linha 2</li><li>Linha 3</li><li>Segurança</li><li>Treinamento</li><li>Manutenção</li><li>Material divertido</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li> <li>Repórter de Problemas</li> <li>Inspeção</li> </ul>|
|Varejo para gerentes| `retailManagerCollaboration` |Canais: <ul><li>Geral<li>Operações</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Wiki</li><li>Planner</li></ul>|
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

Confira [Limites e especificações de Teams](limits-specifications-teams.md) para obter mais informações.

## <a name="manage-templates-in-powershell"></a>Gerenciar modelos no PowerShell

Use os cmdlts a seguir para gerenciar seus modelos no PowerShell.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps) 
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps) 
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-topics"></a>Tópicos relacionados

- [Criar um modelo de equipe personalizado](create-a-team-template.md)
- [Criar um modelo de equipe a partir de um modelo de equipe existente](create-template-from-existing-template.md)
- [Criar um modelo de uma equipe existente](create-template-from-existing-team.md)
