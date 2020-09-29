---
title: Modelos para organizações de assistência médica
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Use os modelos do Microsoft Teams para criar equipes rápida e facilmente fornecendo um modelo predefinido de configurações, canais e aplicativos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2ef6bd4bf358a90654e7fda643effbfcc34b3c2
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294428"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations-using-microsoft-graph"></a>Introdução aos modelos do teams para organizações de assistência médica usando o Microsoft Graph

Os modelos do Microsoft Teams permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Para organizações de assistência médica, os modelos podem ser eficientes, pois fornecem estrutura para que os usuários se orientem com o modo de usar o Teams de forma eficaz. Os modelos também permitem que os administradores implantem equipes consistentes em suas organizações. Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização de assistência médica.

Atualmente, oferecemos dois modelos de saúde de primeira mão que você pode usar para várias situações. Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](../../get-started-with-teams-templates.md)do Microsoft Teams.

## <a name="ward-template"></a>Modelo de versões anteriores

O modelo para a era destinado à comunicação e à colaboração em um departamento, um pod ou um departamento. O modelo pode ser usado para facilitar o gerenciamento de pacientes, bem como as necessidades operacionais de uma vez. Por exemplo, os comunicados para o fim podem ser publicados no canal de *anúncios* e os turnos podem ser gerenciados na *equipe*. Se você pretende simplificar as operações de sua era para você, este modelo é para você.

|Tipo de modelo base |baseTemplateId |Canais de modelo de linha de base|
|:--- |:---|:---|
|Saúde para a frente | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Comunicados\* <br> Huddles\* <br> Arredonda\* <br> Especificam\* <br> Treinamento\* |
|     | |         |

\* Favoritos automaticamente

## <a name="hospital-template"></a>Modelo do hospital

O modelo hospital destina-se à comunicação e colaboração entre vários departamentos, pods e departamentos em um hospital. Neste modelo, há vários canais operacionais, incluindo *anúncios*, *custodial*e *Farmácias*, mas também fornecemos um script abaixo que estende o modelo com uma variedade de canais complementares de departamento ou especialidade que você pode adicionar, excluir ou editar de preferência. Por exemplo, se você tiver um departamento *Endocrinology* , mas não precisa de um canal para *ophthalmology*, o script poderá ser adaptado para incluir um canal de *Endocrinology* e remover o canal de *ophthalmology* . Recomendamos que esses canais de especialidade ou modelo não sejam favoritos automaticamente para evitar a saturação da notificação. Os usuários geralmente têm favorito todos os canais que encontrarem relevantes.

|Tipo de modelo base |baseTemplateId |Canais de modelo de linha de base|
|:--- |:---|:---|
|Assistência médica – hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Comunicados\* <br> Conformidade\* <br> Custodial <br> Recursos humanos <br> Farmácia |
| | |  |

\* Favoritos automaticamente 

## <a name="how-to-use-first-party-templates"></a>Como usar modelos de primeira empresa

Para usar esses modelos, basta alterar a propriedade ' template@odata. BIND ' no corpo da solicitação de ' Standard ' para a TemplateIDs acima.  Para obter mais informações sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph sobre como [criar uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Os canais no modelo serão automaticamente criados na guia geral.

### <a name="example-hospital-template-extension-script"></a>Exemplo: script de extensão de modelo hospital

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

[Introdução aos modelos do Microsoft Teams no console de administração](../../get-started-with-teams-templates-in-the-admin-console.md)
