---
title: Modelos para organizações de saúde
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Use modelos do Microsoft Teams com o Microsoft Graph para criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX
ms.openlocfilehash: e288bc68c8160fb80d4e56a6477437e0a79fea0a
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260333"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Começar a usar modelos do Teams para organizações de saúde

Os modelos do Microsoft Teams permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Para organizações de saúde, os modelos podem ser especialmente poderosos, pois fornecem estrutura para os usuários se orientarem sobre como usar o Teams de forma eficaz. Os modelos também permitem que os administradores implantem equipes consistentes em suas organizações. Este artigo é para você se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização de saúde.

Atualmente, oferecemos dois modelos de serviços de saúde de primeira mão que você pode usar para várias situações. Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar os modelos do Teams.](../../get-started-with-teams-templates.md)

## <a name="ward-template"></a>Modelo de modelo de

O modelo de modelo de modelo de modelo é destinado à comunicação e à colaboração dentro de uma nave, um vagem ou um departamento. O modelo pode ser usado para facilitar o gerenciamento de pacientes, bem como as necessidades operacionais de um paciente. Por exemplo, os comunicados de reunião podem ser postados no canal *Comunicados* e os turnos podem ser gerenciados *na Equipe.* Se você está tentando simplificar suas operações de resgate, então este modelo é para você.

|Tipo de Modelo Base |baseTemplateId |Canais de modelo de linha de base|
|:--- |:---|:---|
|Saúde – Ltda | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Anúncios\* <br> Desaconsudores\* <br> Rodadas\* <br> Pessoal\* <br> Treinamento\* |
|     | |         |

\* Favoritos automáticos

## <a name="hospital-template"></a>Modelo de hospital

O modelo de hospital é destinado à comunicação e à colaboração entre vários nós, vagens e departamentos dentro de um hospital. Incluídos neste modelo, há vários canais operacionais, incluindo *Comunicados,* Pré-operatórios e Desmados, mas também fornecemos um script abaixo que estende o modelo com uma variedade de departamentos adicionais ou canais centrados em especial que você pode adicionar, excluir ou editar ao seu gosto. Por exemplo, se você tiver um departamento de Endocrinologia, mas não precisar de um canal para *Oftalmologia,* o script poderá ser adaptado para incluir um canal *de Endocrinologia* e remover o canal  *oftalmologia.* Recomendamos que esses canais especializados ou modelados por ela não sejam favoritos automaticamente para evitar saturação da notificação. Os usuários geralmente favoritam todos os canais que eles acham relevantes.

|Tipo de Modelo Base |baseTemplateId |Canais de modelo de linha de base|
|:--- |:---|:---|
|Saúde – Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Anúncios\* <br> Conformidade\* <br> Custódia <br> Recursos Humanos <br> Farmácia |
| | |  |

\* Favoritos automáticos 

## <a name="how-to-use-first-party-templates"></a>Como usar modelos de primeira

Para usar esses modelos, basta alterar a propriedade "template@odata.bind" no corpo da solicitação de 'padrão' para os TemplateIDs acima.  Para obter mais informações sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph sobre como [criar uma Equipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Os canais no modelo serão criados automaticamente na guia Geral.

### <a name="example-hospital-template-extension-script"></a>Exemplo: Script de extensão de modelo de hospital

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

## <a name="related-topics"></a>Tópicos relacionados

[Introdução aos modelos do Teams](../../get-started-with-teams-templates.md)

[Introdução ao Teams para Organizações de Saúde](teams-in-hc.md)

[Começar a usar modelos do Teams no console de administração](../../get-started-with-teams-templates-in-the-admin-console.md)
