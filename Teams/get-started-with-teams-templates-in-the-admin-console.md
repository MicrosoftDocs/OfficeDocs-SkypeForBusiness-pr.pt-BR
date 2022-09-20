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
- m365-frontline
description: Saiba mais sobre modelos de equipe e como gerenciá-los no Centro de administração do Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41267db383d39c40ee18a67ee96538f205df52e4
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837551"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Introdução aos modelos de equipe no Centro de administração do Teams

**Ainda não há suporte para a capacidade de criar modelos personalizados para clientes EDU.**

> [!NOTE]
> - Atualmente, não há suporte para canais privados e compartilhados em modelos de equipe. A criação de canal privado e compartilhado não está incluída nas definições de modelo.
>
> - Não há suporte para rótulos de confidencialidade em modelos de equipe em ambientes GCC. A opção de rótulo de confidencialidade na equipe Criar do fluxo de modelo não será aplicada à equipe.

## <a name="overview"></a>Visão geral

Um modelo de equipe no Microsoft Teams é uma definição da estrutura de uma equipe projetada em torno de uma necessidade de negócios ou projeto. Como administrador, você pode usar modelos para implantar facilmente equipes consistentes em sua organização. Com modelos, os usuários podem criar rapidamente espaços de colaboração avançados com configurações, canais e aplicativos predefinidos.

Você pode gerenciar modelos de equipe no centro de administração do Microsoft Teams ou usando o PowerShell. Você pode usar os modelos pré-criados que fornecemos e também pode [criar seus próprios modelos personalizados](#create-your-own-team-templates). Você também pode [aplicar políticas de modelo](#apply-team-template-policies) para controlar quais modelos estão disponíveis para seus usuários no Teams.

Este artigo fornece uma visão geral de como trabalhar com modelos de equipe no centro de administração do Teams. Você aprenderá sobre as propriedades com suporte em modelos, os modelos predefinidos que fornecemos, os limites de tamanho do modelo, como criar e gerenciar modelos e muito mais.

> [!NOTE]
> Os usuários podem [criar equipes com base em modelos de equipe predefinido ou personalizados](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) no aplicativo Teams. Os desenvolvedores também podem criar equipes programaticamente com base em modelos de equipe pré-criados ou personalizados usando o Microsoft Graph. Para saber mais, confira [Introdução aos modelos de equipe usando o Microsoft Graph](get-started-with-teams-templates.md).

## <a name="team-template-capabilities"></a>Funcionalidades de modelo de equipe

A maioria das propriedades em uma equipe é incluída e tem suporte por modelos de equipe. Mas há algumas propriedades e recursos que não têm suporte no momento. Aqui está um resumo do que está incluído e o que não está incluído nos modelos de equipe.

| **Propriedades da equipe compatíveis com modelos de equipe** | **Propriedades da equipe ainda não compatíveis com modelos de equipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo | Associação da equipe |
| Nome da equipe | Imagem da equipe |
| Descrição da equipe | Configurações de canal |
| Visibilidade da equipe (pública ou privada) | Conectores |
| Configurações da equipe (por exemplo, membro, convidado, @ menções) | Arquivos e conteúdo |
| Canal de autofavorite | |
| Aplicativo instalado | |
| Guias fixadas | |

> [!NOTE]
> Adicionaremos mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique novamente as informações mais atualizadas sobre as propriedades com suporte.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Modelos de equipe pré-criados no centro de administração do Teams

Aqui estão os modelos de equipe pré-criados que estão disponíveis no centro de administração do Teams. Modelos pré-criados são modelos que criamos para setores específicos. Para exibir esses modelos, no painel de navegação esquerdo do Centro de administração do Teams, acesse os modelos **de Equipe do** **Teams** > .

Você pode duplicar modelos pré-criados, mas não pode editá-los. Se você quiser alterar as propriedades em um modelo predefinido, poderá criar um novo modelo com base em um existente e, em seguida, adicionar ou remover as propriedades desejadas. Tenha em mente que determinadas propriedades em alguns modelos não podem ser alteradas.

> [!NOTE]
> Um asterisco (*) indica que o modelo é um *modelo conectado do Microsoft 365*. Quando os usuários criam uma equipe usando o modelo, o modelo conectado do SharePoint é aplicado ao site e à equipe. Componentes do SharePoint, como páginas, listas e integrações do Power Platform, são adicionados e fixados automaticamente como guias ao canal Geral da equipe. Os usuários podem editar essas páginas e listas diretamente no Teams.
>
> Para saber mais sobre modelos do SharePoint, consulte [Aplicar e personalizar modelos de site do SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

>[!div class="mx-tdBreakAll"]
>| Tipo de modelo | TemplateId | Propriedades que vêm com este modelo |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Gerenciar um projeto* |`com.microsoft.teams.template.ManageAProject`| Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Recursos</li> <li>Planejamento</li></ul> Apps:<ul><li>Aprovações</li><li>Boletins</li><li>Listas<ul><li>Rastreador de projeto</li><li>Rastreador de problemas</li></ul></li><li>Marcos</li><li>OneNote</li><li>Power Automate</li><li>Páginas do SharePoint<ul><li>Nosso site</li></ul></li><li>Tarefas por Planner e Tarefas Pendentes</li><li>Wiki</li></ul> |
| Gerenciar um evento*|`com.microsoft.teams.template.ManageAnEvent` | Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Orçamento</li> <li>Conteúdo</li><li>Logística</li> <li>Planejamento</li> <li> Marketing e PR</li></ul> Apps:<ul><li>Aprovações</li><li>Boletins</li> <li>Ideias dos funcionários</li><li>Listas<ul><li>Agendador de conteúdo</li></ul></li><li>Marcos</li> <li>OneNote</li> <li>Power Automate</li> <li>Páginas do SharePoint<ul><li>Nosso site</li><li>Sobre nosso evento</li></ul><li>Tarefas por Planner e Tarefas Pendentes</li><li>Wiki</li> |
|Integrar funcionários*|`com.microsoft.teams.template.OnboardEmployees` | Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Chat de funcionários</li> <li>Treinamento</li></ul>Apps:<ul><li>Boletins</li><li>Ideias dos funcionários</li><li>Listas<ul><li>Lista de verificação de integração</li></ul></li><li>Marcos</li><li>Power Automate</li> <li>Páginas do SharePoint<ul><li>Introdução</li><li>Treinamento</li></ul><li>Tarefas por Planner e Tarefas Pendentes</li><li>Engajar do Viva</li><li>Wiki</li></ul>|
| Adotar Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canais: <ul><li>Geral</li> <li>Comunicados</li> <li>Canto dos Campeões</li> <li>Formulários de Equipe</li><li>Calendário</li></ul> Apps: <ul><li>Wiki</li>  <li>Calendário do canal</li> <li>Marcos</li><li>Boletins</li></ul>
|Organizar o Suporte Ajuda*| `com.microsoft.teams.template.OrganizeHelpDesk`|Canais:<ul><li>Geral</li><li>Comunicados</li><li>Perguntas frequentes</li></ul>Apps:<ul><li>Relatório de problemas</li><li>Listas<ul><li>Dispositivos</li><li>Bilhetes</li></ul></li><li>OneNote</li><li>Power Automate</li><li>Páginas do SharePoint<ul><li>Nosso site</li><li>Perguntas frequentes</li></ul></li><li>Tarefas por Planner e Tarefas Pendentes</li><li>Wiki</li></ul> |
|Resposta a incidentes| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canais: <ul><li>Geral<li>Comunicados</li><li>Logística</li><li>Planejamento</li><li>Recuperação</li><li>Urgente</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Tarefas</li> <li>Aprovações</li> <li>Inspeção</li> <li>Power Automate</li><li>Boletins</li><li>Marcos</li></ul>|
| Crisis Communications* |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canais: <ul><li>Geral<li>Comunicados</li><li>Atualização executiva</li><li>Planejamento</li><li>Logística</li></ul>Apps: <ul><li>Aprovações</li><li>Relatório de problemas</li><li>Listas<ul><li>Agendador de conteúdo</li><li>Plano de projeto</li></ul></li><li>OneNote</li><li>Power Automate</li><li>Páginas do SharePoint<ul><li>Nosso site</li><li>Atualização mais recente</li></ul><li>Tarefas por Planner e Tarefas Pendentes</li>|
| Gerenciar uma Loja*| `com.microsoft.teams.template.retailStore` |Canais: <ul><li>Geral<li>Shift Handoff</li><li>Preparação da Loja</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Aprovações</li><li>Inspeção</li><li>Listas<ul><li>Lista de inventário</li></ul></li><li>Páginas do SharePoint<ul><li>Nossa loja</li></ul></li><li>Turnos</li><li>Tarefas por Planner e Tarefas Pendentes</li><li>Wiki</li></ul>|
|Filial Bancária| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canais: <ul><li>Geral<li>Comunicados</li><li>Insuidades</li><li>Reuniões com clientes</li><li>Solicitação de Aprovações </li><li>Treinamento</li><li>Desenvolvimento de habilidades</li><li>Processamento de empréstimos</li><li>Reclamações do cliente</li><li>Parabéns</li><li>Coisas divertidas</li><li>Conformidade</li></ul>Aplicativos:<ul><li>Elogio </li><li>Relator de Problemas</li><li>Wiki</li><li>Calendário</li><li>Aprovações</li><li>Boletins</li><li>Ideias</li></ul>|
| Atendimento ao Paciente| `com.microsoft.teams.template.healthcareWard`| Canais:<ul><li>Geral</li><li>Comunicados</li><li>Insuidades</li><li>Rodadas</li><li>Estrelada</li><li>Treinamento</li></ul> Apps: <ul><li>Wiki</li><li>Listas  </li><li>Aprovações</li><li>Boletins</li><li>Inspeção</li></ul>|
|Hospital| `com.microsoft.teams.template.healthcareHospital` |Canais: <ul><li>Geral</li><li>Comunicados</li><li>Conformidade</li><li>Custódia</li><li>Recursos Humanos</li><li>Farmácia</li></ul> Apps: <ul><li>Wiki</li><li>Listas</li><li>Tarefas</li><li>Aprovações</li><li>Turnos</li><li>Boletins</li><li>Inspeção</li><li>Ideias</li></ul>|
|Qualidade e segurança |`com.microsoft.teams.template.QualitySafety`|Canais: <ul><li>Geral<li>Comunicados</li><li>Liderança</li><li>Manutenção</li><li>Linha de Produção 1</li><li>Linha de Produção 2</li><li>Linha de Produção 3</li><li>Saúde e Segurança</li><li>Treinamento</li><li>Coisas divertidas</li></ul> Apps: <ul><li>Wiki</li><li>Tarefas</li> <li>Relator de Problemas</li> <li>Inspeção</li> </ul>|
|Varejo para gerentes*| `com.microsoft.teams.template.retailManagerCollaboration` |Canais: <ul><li>Geral<li>Operações</li><li>Aprendizado</li></ul> Aplicativos: <ul><li>Aprovações</li><li>Inspeção</li><li>Páginas do SharePoint<ul><li>Nossa loja</li></ul></li><li>Tarefas por Planner e Tarefas Pendentes</li><li>Wiki</li></ul>|
|Gerenciar voluntários| `com.microsoft.teams.template.ManageVolunteers` |Canais: <ul><li>Geral<li>Comunicados</li><li>Relatórios</li><li>Gerenciamento Voluntário</li><li>Oportunidades de Compromisso</li><li>Integração do Voluntário</li></ul> Apps: <ul><li>Site</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Tarefas</li><li>SharePoint</li><li>OneNote</li></ul>|

### <a name="team-templates-by-category-and-industry"></a>Modelos de equipe por categoria e setor

Para obter mais informações sobre maneiras de usar os modelos pré-criados em seu setor, consulte:

- [Modelos gerais de equipe](general-teams-templates-in-the-admin-console.md)
- [Modelos de equipe financeira](financial-teams-templates-in-the-admin-console.md)
- [Modelos de equipe do governo](government-teams-templates-in-the-admin-console.md)
- [Modelos da equipe de saúde](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modelos de equipe de fabricação](manufacturing-teams-templates-in-the-admin-console.md)
- [Modelos de equipe sem fins lucrativos](team-templates-nonprofit.md)
- [Modelos de equipe de varejo](get-started-with-retail-teams-templates.md)

## <a name="team-template-size-limits"></a>Limites de tamanho do modelo de equipe

Os modelos são limitados a um número específico de canais, guias e aplicativos.

 > [!Note]
 > Você pode adicionar mais canais, guias e aplicativos à equipe depois que ele é criado com base em um modelo.

|Recurso | Limite|
|-|-|
|Canais por modelo | 15 |
|Guias por canal em um modelo | 20 |
|Aplicativos por modelo | 50|

Para obter mais informações, [consulte Limites e especificações do Teams](limits-specifications-teams.md).

## <a name="manage-team-templates"></a>Gerenciar modelos de equipe

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Gerenciar modelos de equipe no Centro de administração do Teams

#### <a name="view-team-templates"></a>Exibir modelos de equipe

Para exibir modelos de equipe, no painel de navegação esquerdo do Centro de administração do Teams, acesse os modelos **de Equipe do** **Teams** > . Selecione um modelo para ver mais detalhes, incluindo os canais e aplicativos que ele contém.

#### <a name="create-your-own-team-templates"></a>Criar seus próprios modelos de equipe

Você pode criar seus próprios modelos personalizados do zero, de uma equipe existente e de um modelo existente. Para saber mais, veja:

- [Criar um modelo de equipe personalizado](create-a-team-template.md)
- [Criar um modelo de uma equipe existente](create-template-from-existing-team.md)
- [Criar um modelo de equipe com base em um modelo de equipe existente](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Aplicar políticas de modelo de equipe

Para controlar os modelos que os usuários veem no Teams para criar equipes [, você](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b) pode definir políticas de modelos e atribuí-las a usuários e grupos em sua organização. Para saber mais, confira [Gerenciar modelos de equipe no centro de administração do Teams](templates-policies.md).

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
- [Visão geral da integração do Teams e do SharePoint](/sharepoint/teams-connected-sites)
