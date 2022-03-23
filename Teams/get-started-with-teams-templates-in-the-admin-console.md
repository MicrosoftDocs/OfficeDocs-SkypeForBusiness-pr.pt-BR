---
title: Introdução aos modelos de equipe no Centro de administração do Teams
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
description: Saiba mais sobre modelos de equipe e como gerenciá-los no Microsoft Teams de administração.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 832d13955287d4166a575d213c04331b7e79e1bd
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711895"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Introdução aos modelos de equipe no Centro de administração do Teams

**A capacidade de criar modelos personalizados ainda não é suportada para clientes EDU.**

> [!NOTE]
> - Canais privados e compartilhados atualmente não são suportados em modelos de equipe. A criação de canal privado e compartilhado não está incluída nas definições de modelo.
>
> - Rótulos de sensibilidade não são suportados em modelos de equipe em GCC ambientes. A opção de rótulo de sensibilidade no fluxo Criar equipe a partir do modelo não será aplicada à equipe.

## <a name="overview"></a>Visão Geral

Um modelo de equipe no Microsoft Teams é uma definição da estrutura de uma equipe projetada em torno de uma necessidade de negócios ou projeto. Como administrador, você pode usar modelos para implantar facilmente equipes consistentes em sua organização. Com modelos, seus usuários podem criar rapidamente espaços de colaboração com configurações, canais e aplicativos predefinidos.

Você pode gerenciar modelos de equipe no Microsoft Teams de administração ou usando o PowerShell. Você pode usar os modelos pré-construídos que fornecemos e também pode [criar seus próprios modelos personalizados](#create-your-own-team-templates). Você também pode [aplicar políticas de modelo](#apply-team-template-policies) para controlar quais modelos estão disponíveis para seus usuários em Teams.

Este artigo fornece uma visão geral de como trabalhar com modelos de equipe no centro de Teams de administração. Você aprenderá sobre as propriedades com suporte em modelos, os modelos pré-construídos que fornecemos, os limites de tamanho do modelo, como criar e gerenciar modelos e muito mais.

> [!NOTE]
> Os usuários podem criar equipes a partir de modelos de equipe [pré-construídos ou personalizados](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) no Teams app. Os desenvolvedores também podem criar equipes programaticamente a partir de modelos de equipe pré-construídos usando o Microsoft Graph. Para saber mais, confira [Começar a usar modelos de equipe usando o Microsoft Graph](get-started-with-teams-templates.md).

## <a name="team-template-capabilities"></a>Recursos de modelo de equipe

A maioria das propriedades em uma equipe são incluídas e suportadas por modelos de equipe. No momento, há algumas propriedades e recursos que não são suportados. Aqui está um resumo do que está incluído e o que não está incluído nos modelos de equipe.

| **Propriedades de equipe suportadas por modelos de equipe** | **Propriedades de equipe ainda não suportadas por modelos de equipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações de equipe (por exemplo, membro, convidado, @ menções) | Arquivos e conteúdo |
| Canal Autofavorite | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Vamos adicionar mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique se há informações mais atualizadas sobre propriedades com suporte.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Modelos de equipe pré-construídos no Teams de administração

Aqui estão os modelos de equipe pré-construídos que estão disponíveis no Teams de administração. Modelos pré-criados são modelos que criamos para setores específicos. Para exibir esses modelos, na navegação à esquerda do centro de administração Teams, vá **para Teams** >  **Modelos doTeam**.

Você pode duplicar modelos pré-construídos, mas não editá-los. Se você quiser alterar as propriedades em um modelo pré-criado, poderá criar um novo modelo a partir de um existente e adicionar ou remover as propriedades que você deseja. Lembre-se de que determinadas propriedades em alguns modelos não podem ser alteradas.

| Tipo de modelo | TemplateId | Propriedades que vêm com este modelo |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adotar Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Canto campeões</li> <li>Formulários de equipe</li><li>Calendário</li></ul> Apps: <ul><li>Wiki</li>  <li>Calendário do canal</li> <li>Marcos</li><li>Boletins</li></ul>|
| Gerenciar um projeto |`com.microsoft.teams.template.ManageAProject`| Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Recursos</li> <li>Planejamento</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li><li>Tarefas</li><li>Listas</li><li>Power Automate</li></ul> |
| Gerenciar um evento|`com.microsoft.teams.template.ManageAnEvent` | Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Orçamento</li> <li>Conteúdo</li><li>Logística</li> <li>Planejamento</li> <li> Marketing e PR</li></ul> Apps:<ul><li>Wiki</li><li>Site</li> <li>YouTube</li> <li>Tarefas</li> <li>OneNote</li> <li>Ideias dos funcionários</li> <li>Relator de Problemas</li><li>Power Automate</li><li>Boletins</li><li>Marcos</li></ul> |
|Funcionários de integração|`com.microsoft.teams.template.OnboardEmployees` | Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Chat de funcionários</li> <li>Treinamento</li></ul>Apps:<ul><li>Wiki</li><li>Comunidades</li><li>Tarefas</li><li>Ideias dos funcionários</li><li>Power Automate</li><li>Boletins</li><li>Marcos</li></ul>|
|Organizar o help desk| `com.microsoft.teams.template.OrganizeHelpDesk`|Canais:<ul><li>Geral</li><li>Comunicados</li><li>Perguntas frequentes</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li><li>Tarefas </li><li>Elogio</li><li>Relator de Problemas</li><li>Power Automate</li><li>Boletins</li></ul> |
| Cuidados com o paciente| `com.microsoft.teams.template.healthcareWard`| Canais:<ul><li>Geral</li><li>Comunicados</li><li>Insuidades</li><li>Rodadas</li><li>Estrelada</li><li>Treinamento</li></ul> Apps: <ul><li>Wiki</li><li>Listas  </li><li>Aprovações</li><li>Boletins</li><li>Inspeção</li></ul>|
| Comunicação de crise |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canais: <ul><li>Geral<li>Comunicados</li><li>Notícias do mundo</li><li>Comunicados internos</li><li>Comunicados externos</li><li>Pedido de aprovação</li><li>Escalonamentos de clientes</li><li>Atualização executiva</li><li>Planejamento</li><li>Logística</li></ul>Apps: <ul><li>Site</li><li>Tarefas</li><li>Relator de Problemas</li><li>Aprovações</li><li>Boletins</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|Filial bancária| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canais: <ul><li>Geral<li>Comunicados</li><li>Insuidades</li><li>Reuniões com clientes</li><li>Solicitação de Aprovações </li><li>Treinamento</li><li>Desenvolvimento de Habilidades</li><li>Processamento de empréstimos</li><li>Reclamações do cliente</li><li>Parabéns</li><li>Diversão</li><li>Conformidade</li></ul>Aplicativos:<ul><li>Elogio </li><li>Relator de Problemas</li><li>Wiki</li><li>Calendário</li><li>Aprovações</li><li>Boletins</li><li>Ideias</li></ul>|
|Resposta a incidentes| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canais: <ul><li>Geral<li>Comunicados</li><li>Logística</li><li>Planejamento</li><li>Recuperação</li><li>Urgente</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Tarefas</li> <li>Aprovações</li> <li>Inspeção</li> <li>Power Automate</li><li>Boletins</li><li>Marcos</li></ul>|
|Hospital| `com.microsoft.teams.template.healthcareHospital` |Canais: <ul><li>Geral</li><li>Comunicados</li><li>Conformidade</li><li>Custódia</li><li>Recursos humanos</li><li>Farmácia</li></ul> Apps: <ul><li>Wiki</li><li>Listas</li><li>Tarefas</li><li>Aprovações</li><li>Turnos</li><li>Boletins</li><li>Inspeção</li><li>Ideias</li></ul>|
|Organizar uma store| `com.microsoft.teams.template.retailStore` |Canais: <ul><li>Geral<li>Mudança de entrega</li><li>Preparação da loja</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Wiki</li><li>Tarefas</li><li>Turnos</li><li>Inspeção</li></ul>|
|Varejo para gerentes| `com.microsoft.teams.template.retailManagerCollaboration` |Canais: <ul><li>Geral<li>Operações</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Wiki</li><li>Tarefas</li><li>Inspeção</li></ul>|
|Qualidade e segurança |`com.microsoft.teams.template.QualitySafety`|Canais: <ul><li>Geral<li>Comunicados</li><li>Liderança</li><li>Manutenção</li><li>Linha de produção 1</li><li>Linha de produção 2</li><li>Linha de produção 3</li><li>Saúde e Segurança</li><li>Treinamento</li><li>Diversão</li></ul> Apps: <ul><li>Wiki</li><li>Tarefas</li> <li>Relator de Problemas</li> <li>Inspeção</li> </ul>|
|Gerenciar voluntários| `com.microsoft.teams.template.ManageVolunteers` |Canais: <ul><li>Geral<li>Comunicados</li><li>Relatórios</li><li>Gerenciamento Voluntário</li><li>Oportunidades de Compromisso</li><li>Integração do Voluntário</li></ul> Apps: <ul><li>Site</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Tarefas</li><li>SharePoint</li><li>OneNote</li></ul>|
||||

### <a name="team-templates-by-category-and-industry"></a>Modelos de equipe por categoria e setor

Para obter mais informações sobre maneiras de usar os modelos pré-construídos em seu setor, consulte:

- [Modelos de equipe financeira](financial-teams-templates-in-the-admin-console.md)
- [Modelos gerais de equipe](general-teams-templates-in-the-admin-console.md)
- [Modelos de equipe do governo](government-teams-templates-in-the-admin-console.md)
- [Modelos de equipe de saúde](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Fabricação de modelos de equipe](manufacturing-teams-templates-in-the-admin-console.md)
- [Modelos de equipe sem fins lucrativos](team-templates-nonprofit.md)
- [Modelos de equipe de varejo](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>Limites de tamanho do modelo de equipe

Os modelos são limitados a um número específico de canais, guias e aplicativos.

 > [!Note]
 > Você pode adicionar mais canais, guias e aplicativos à equipe depois que ele é criado a partir de um modelo.

|Recurso | Limite|
|-|-|
|Canais por modelo | 15 |
|Guias por canal em um modelo | 20 |
|Aplicativos por modelo | 50|
|||

Para obter mais informações, [consulte Limites e especificações de Teams](limits-specifications-teams.md).

## <a name="manage-team-templates"></a>Gerenciar modelos de equipe

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Gerenciar modelos de equipe no Centro de administração do Teams

#### <a name="view-team-templates"></a>Exibir modelos de equipe

Para exibir modelos de equipe, na navegação à esquerda do centro de administração Teams,  >  vá para Teams **Modelos doTeam**. Selecione um modelo para ver mais detalhes, incluindo os canais e aplicativos que ele contém.

#### <a name="create-your-own-team-templates"></a>Criar seus próprios modelos de equipe

Você pode criar seus próprios modelos personalizados do zero, de uma equipe existente e de um modelo existente. Para saber mais, veja:

- [Criar um modelo de equipe personalizado](create-a-team-template.md)
- [Criar um modelo de uma equipe existente](create-template-from-existing-team.md)
- [Criar um modelo de equipe a partir de um modelo de equipe existente](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Aplicar políticas de modelo de equipe

Para controlar os modelos que os usuários veem no Teams para criar equipes[, você](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b) pode definir políticas de modelos e atribuí-las a usuários e grupos em sua organização. Para saber mais, confira [Gerenciar modelos de equipe no Teams de administração](templates-policies.md).

### <a name="manage-team-templates-using-powershell"></a>Gerenciar modelos de equipe usando o PowerShell

Use os cmdlets a seguir para gerenciar seus modelos no PowerShell.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate)

## <a name="related-articles"></a>Artigos relacionados

- [Criar uma equipe a partir de um modelo](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introdução aos modelos de equipe usando Microsoft Graph](get-started-with-teams-templates.md)
- [Clonar uma equipe](/graph/api/team-clone)
