---
title: Usar modelos de equipe de cuidados de saúde
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Aprenda a gerenciar e usar os modelos de equipe de serviços de saúde no Centro de administração do Teams e com o Microsoft Graph para criar equipes de forma rápida e fácil para sua organização de saúde.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4f3aa9d42ef86dde75acf8cbd559b6e50059a428
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396912"
---
# <a name="use-healthcare-team-templates"></a>Usar modelos de equipe de cuidados de saúde

Os modelos de equipe no Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo uma estrutura de equipe predefinida de configurações, canais e aplicativos pré-instalados.

Para organizações de serviços de saúde, os modelos de equipe podem ser especialmente poderosos, pois ajudam você a implantar rapidamente equipes consistentes na sua organização. Os modelos também ajudam a equipe a se orientar sobre como usar o Teams de maneira eficaz.

O Teams inclui modelos projetados especificamente para organizações de serviços de saúde. Use esses modelos pré-criados para criar rapidamente equipes para a equipe se comunicar e colaborar no atendimento ao paciente ou nas necessidades operacionais. Neste artigo, apresentamos cada um desses modelos e recomendamos como usá-los.

A maneira como você gerencia e trabalha com modelos de equipe depende se você é um administrador ou desenvolvedor.

|Se você estiver: | Em seguida, você: |
| ---- | --------- |
| Um administrador ou profissional de IT |[Gerencie modelos de equipe no centro de administração do Teams](#manage-team-templates-in-the-teams-admin-center). Exiba modelos de equipe e aplique políticas de modelos para controlar quais modelos sua equipe pode usar no Teams para criar equipes. |
| Um desenvolvedor | [Use o Microsoft Graph](#use-team-templates-with-microsoft-graph) para criar equipes a partir dos  modelos de equipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gerenciar modelos de equipe no Centro de administração do Teams

Como administrador, você pode gerenciar os modelos de equipe no Centro de administração do Microsoft Teams. Aqui, você pode exibir os detalhes sobre cada modelo. Você também pode [criar e atribuir políticas de modelos](../../templates-policies.md) para sua equipe controlar quais modelos são vistos no Teams para a [criação de equipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Para saber mais sobre modelos de equipe em geral, consulte [Introdução aos modelos de equipe no Centro de administração do Teams](../../get-started-with-teams-templates-in-the-admin-console.md).

Atualmente, oferecemos os modelos de equipe de serviços de saúde pré-criados a seguir. Para exibi-los, no painel de navegação esquerdo do Centro de administração do Teams, acesse **Teams** > **Modelos do Teams**.
### <a name="patient-care"></a>Cuidados com o paciente

 Este modelo destina-se à comunicação e colaboração dentro de uma enfermaria, pod ou departamento. Você pode usar este modelo para facilitar o gerenciamento de pacientes e as necessidades operacionais de uma enfermaria. Por exemplo, poste anúncios da enfermaria no canal *Anúncios* e gerencie os turnos no canal *Recrutamento*.

| Tipo de modelo |TemplateId| Propriedades que vêm com este modelo |
| ------------------ |---|----------------------------------------------------- |
| Cuidados com o paciente |`healthcareWard` | Canais:<ul><li>Geral</li><li>Comunicados<ul><li>Boletins&sup1;</li></ul></li><li>Huddles<ul><li>Listas (Lista de pacientes)&sup1;</li></ul></li><li>Rodadas<ul><li>Inspeção&sup1;</li></ul></li><li>Estrelada</li><li>Treinamento</li></ul> Apps: <ul><li>Wiki</li><li>Listas</li><li>Tarefas</li><li>Aprovações</li><li>Turnos</li><li>Boletins</li><li>Inspeção</li></ul>|
||||

&sup1;Aplicativo adicionado ao canal como uma guia.
### <a name="hospital"></a>Hospital

Este modelo destina-se à comunicação e colaboração entre várias enfermarias, pods e departamentos dentro de um hospital. Este modelo inclui um conjunto de canais para operações hospitalares e pode ser estendido para personalização posterior.

| Tipo de modelo |TemplateId | Propriedades que vêm com este modelo |
| ------------------|-- |----------------------------------------------------- |
|Hospital|`healthcareHospital`|Canais: <ul><li>Geral<ul><li>Listas&sup1;</li></ul></li><li>Comunicados<ul><li>Boletins&sup1;</li></ul></li><li>Conformidade</li><ul><li>Inspeção&sup1;</li></ul></li><li>Custódia</li><li>Recursos humanos<ul><li>Ideias&sup1;</li></ul></li><li>Farmácia</li></ul> Apps: <ul><li>Wiki</li><li>Tarefas</li><li>Listas</li><li>Aprovações</li><li>Turnos</li><li>Boletins</li><li>Inspeção</li><li>Ideias</li></ul>|
||||

&sup1;Aplicativo adicionado ao canal como uma guia.
## <a name="use-team-templates-with-microsoft-graph"></a>Usar os modelos do Teams com o Microsoft Graph

Os desenvolvedores podem usar o Microsoft Graph para criar equipes a partir de modelos de equipe pré-criados. Para saber mais sobre como usar modelos de equipe com o Microsoft Graph, consulte [ Introdução aos modelos de equipe usando Microsoft Graph](../../get-started-with-teams-templates.md), [Visão geral da API do Microsoft Teams](/graph/teams-concept-overview) e [tipo de recurso teamsTemplate](/graph/api/resources/teamstemplate).

Aqui estão os modelos de equipe de serviços de saúde pré-criados.
### <a name="ward"></a>Enfermaria

O modelo da enfermaria é destinado à comunicação e colaboração dentro de uma enfermaria, pod ou departamento. O modelo pode ser usado para facilitar o gerenciamento de pacientes e as necessidades operacionais de uma enfermaria. Por exemplo, comunicados completos podem ser postados no canal *Comunicados* e turnos podem ser gerenciados no *Equipe*. Se você estiver tentando simplificar suas operações normais, este modelo é para você.

|Tipo de Modelo |TemplateId |Canais de modelo|
|:--- |:---|:---|
|Serviços de saúde – Enfermaria | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Geral<br>Comunicados&sup2; <br> Huddles&sup2; <br> Turnos&sup2; <br> Recrutamento&sup2; <br> Treinamento&sup2; |
|     | |         |

&sup2;Canais marcados como favorito automaticamente

### <a name="hospital"></a>Hospital

O modelo de hospital destina-se à comunicação e colaboração entre várias enfermarias, pods e departamentos dentro de um hospital. Este modelo inclui vários canais operacionais, como *Anúncios*, *Custódia* e *Farmácia*. Também fornecemos um script que você pode usar para estender o modelo para departamentos adicionais ou canais especializados. Você pode editá-lo para se ajustar às suas necessidades.

Por exemplo, se você tem um departamento de *Endocrinologia*, mas não precisa de um canal para *Oftalmologia*, o script pode ser adaptado para incluir um canal de *Endocrinologia* e remover o canal de *Oftalmologia*. Recomendamos que esses canais especializados ou modelados não sejam favoritos automaticamente para evitar saturação da notificação. Os usuários geralmente favoritam os canais que acham relevantes.

|Tipo de modelo |TemplateId |Canais de modelo|
|:--- |:---|:---|
|Serviços de saúde – Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Geral<br>Comunicados&sup2; <br> Conformidade&sup2; <br> Custódia <br> Recursos Humanos <br> Farmácia |
| | |  |

&sup2;Canais marcados como favorito automaticamente

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Como usar modelos de equipe com o Microsoft Graph

Para usar esses modelos, altere a propriedade 'template@odata.bind' no corpo da solicitação de 'padrão' para as TemplateIds acima. Para obter mais informações sobre como implantar modelos de equipe, consulte o artigo do Microsoft Graph sobre como [criar uma equipe](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Os canais no modelo serão criados automaticamente na guia **Geral**.

#### <a name="example-hospital-template-extension-script"></a>Exemplo: Script de extensão de modelo de hospital

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-articles"></a>Artigos relacionados

- [Criar uma equipe a partir de um modelo](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Introdução aos modelos de equipe no Centro de administração do Teams](../../get-started-with-teams-templates-in-the-admin-console.md)
- [Introdução aos modelos de equipe usando o Microsoft Graph](../../get-started-with-teams-templates.md)
- [Introdução ao Teams para Organizações de Saúde](/microsoft-365/frontline/teams-in-hc?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)