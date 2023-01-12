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
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Aprenda a gerenciar e usar os modelos de equipe de serviços de saúde no Centro de administração do Teams e com o Microsoft Graph para criar equipes de forma rápida e fácil para sua organização de saúde.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 17f5ce2774dd163f5f244bea0e685623f64ed59f
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778961"
---
# <a name="use-healthcare-team-templates"></a>Usar modelos de equipe de cuidados de saúde

Os modelos de equipe no Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo uma estrutura de equipe predefinida de configurações, canais e aplicativos pré-instalados.

Para organizações de serviços de saúde, os modelos de equipe podem ser especialmente poderosos, pois ajudam você a implantar rapidamente equipes consistentes na sua organização. Os modelos também ajudam a equipe a se orientar sobre como usar o Teams de maneira eficaz.

O Teams inclui modelos projetados especificamente para organizações de serviços de saúde. Use esses modelos pré-criados para criar rapidamente equipes para a equipe se comunicar e colaborar no atendimento ao paciente ou nas necessidades operacionais. Neste artigo, apresentamos cada um desses modelos e recomendamos como usá-los.

A maneira como você gerencia e trabalha com modelos de equipe depende se você é um administrador ou desenvolvedor.

|Se você estiver: | Em seguida, você: |
| ---- | --------- |
| Um administrador ou profissional de IT |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Um desenvolvedor | [Use o Microsoft Graph](#use-team-templates-with-microsoft-graph) para criar equipes a partir dos  modelos de equipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gerenciar modelos de equipe no Centro de administração do Teams

Como administrador, você pode gerenciar os modelos de equipe no Centro de administração do Microsoft Teams. Aqui, você pode exibir os detalhes sobre cada modelo. Você também pode [criar e atribuir políticas de modelos](../../templates-policies.md) para sua equipe controlar quais modelos são vistos no Teams para a [criação de equipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Para saber mais sobre modelos de equipe em geral, consulte [Introdução aos modelos de equipe no Centro de administração do Teams](../../get-started-with-teams-templates-in-the-admin-console.md).

Atualmente, oferecemos os modelos de equipe de serviços de saúde pré-criados a seguir. Para exibi-los, no painel de navegação esquerdo do Centro de administração do Teams, acesse **Teams** > **Modelos do Teams**.

### <a name="patient-care"></a>Atendimento ao Paciente

Simplifique a comunicação e a colaboração dos serviços de saúde dentro de um departamento, um ou mais. Use este modelo para facilitar o gerenciamento de pacientes e as necessidades operacionais de uma enfermaria. Por exemplo, poste anúncios da enfermaria no canal *Anúncios* e gerencie os turnos no canal *Recrutamento*.

>[!div class="mx-tdBreakAll"]
>| Tipo de modelo |TemplateId| Propriedades que vêm com este modelo |
>| ------------------ |---|----------------------------------------------------- |
>| Atendimento ao Paciente |`healthcareWard` | Canais:<ul><li>Geral</li><li>Comunicados</li><li>Insuidades</li><li>Rodadas</li><li>Estrelada</li><li>Treinamento</li></ul> Apps: <ul><li>Aprovações</li><li>Boletins</li><li>Inspeção</li><li>Listas</li><li>Turnos</li><li>Tarefas por Planejador e Para Fazer</li><li>Wiki</li></ul>|

### <a name="hospital"></a>Hospital

Simplifique a comunicação e a colaboração entre vários funcionários, funcionários e departamentos dentro de um hospital. Este modelo inclui um conjunto de canais para operações hospitalares e pode ser estendido para personalização posterior.

>[!div class="mx-tdBreakAll"]
>| Tipo de modelo |TemplateId | Propriedades que vêm com este modelo |
>| ------------------|-- |----------------------------------------------------- |
>|Hospital|`healthcareHospital`|Canais: <ul><li>Geral</li><li>Comunicados</li><li>Conformidade</li></li><li>Custódia</li><li>Recursos Humanos</li><li>Farmácia</li></ul>  Apps: <ul><li>Aprovações</li><li>Boletins</li><li>Ideias dos funcionários</li><li>Inspeção</li><li>Listas</li><li>Turnos</li><li>Tarefas por Planejador e Para Fazer</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Usar os modelos do Teams com o Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview), and [teamsTemplate resource type](/graph/api/resources/teamstemplate).

Aqui estão os modelos de equipe de serviços de saúde pré-criados.

### <a name="patient-care"></a>Atendimento ao Paciente

Este modelo destina-se à comunicação e colaboração dentro de uma enfermaria, pod ou departamento. Use este modelo para facilitar o gerenciamento de pacientes e as necessidades operacionais de uma enfermaria. Por exemplo, comunicados completos podem ser postados no canal *Comunicados* e turnos podem ser gerenciados no *Equipe*. Se você estiver tentando simplificar suas operações normais, este modelo é para você.

>[!div class="mx-tdBreakAll"]
>|Tipo de Modelo |TemplateId |Canais de modelo|
>|:--- |:---|:---|
>|Serviços de saúde – Enfermaria | `https://graph.microsoft.com/beta/teamsTemplates('healthcareWard')`   | Geral<br>Comunicados&sup2; <br> Huddles&sup2; <br> Turnos&sup2; <br> Recrutamento&sup2; <br> Treinamento&sup2; |

&sup2;Canais marcados como favorito automaticamente

### <a name="hospital"></a>Hospital

Este modelo destina-se à comunicação e colaboração entre várias enfermarias, pods e departamentos dentro de um hospital. Ele inclui vários canais operacionais, como *Comunicados*, *Custódia* e *Farmácia*. Também fornecemos um script que você pode usar para estender o modelo com mais departamentos ou canais especializados. Você pode editá-lo para se ajustar às suas necessidades.

Por exemplo, se você tiver um departamento de *Endocrinologia* , mas não precisar de um canal para *Oftalmologia*, poderá adaptar o script para incluir um canal de *Endocrinologia* e remover o canal *oftalmologia* . Recomendamos que esses canais especializados ou modelados não sejam favoritos automaticamente para evitar saturação da notificação. Os usuários geralmente favoritam os canais que acham relevantes.

>[!div class="mx-tdBreakAll"]
>|Tipo de modelo |TemplateId |Canais de modelo|
>|:--- |:---|:---|
>|Serviços de saúde – Hospital | `https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')`   | Geral<br>Comunicados&sup2; <br> Conformidade&sup2; <br> Custódia <br> Recursos Humanos <br> Farmácia |

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