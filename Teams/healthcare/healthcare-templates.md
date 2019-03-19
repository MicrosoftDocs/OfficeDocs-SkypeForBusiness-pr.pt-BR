---
title: Introdução aos modelos do Teams para Organizações de Assistência Médica
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introdução aos modelos do Teams para Organizações de Assistência Médica
ms.openlocfilehash: e5116ecf2ab9fa0bbad25222e69317c47cf0c892
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664696"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Introdução aos modelos do Teams para Organizações de Assistência Médica

Modelos de Teams da Microsoft permitem que você rapidamente e criar facilmente equipes, fornecendo um modelo predefinido de configurações, canais e pré-instaladas apps.

Para organizações de saúde, os modelos podem ser especialmente poderosos, como fornecem uma estrutura para os usuários a se tornar orientadas com como aproveitar melhor equipes efetivamente. Modelos também permitem que os administradores implantem equipes consistentes entre suas organizações. Este artigo é para você, se você é responsável pelo planejamento, implantação e gerenciamento de várias equipes em sua organização de saúde.

Estamos atualmente oferta dois primeira parte da área de saúde modelos que você pode aproveitar para uma variedade de situações. Para saber mais sobre a equipe modelos em geral, consulte [Introdução ao modelos de equipes](../get-started-with-teams-templates.md).

## <a name="ward-template"></a>Modelo do bairro

O modelo de bairro destina-se a comunicação e colaboração em um bairro, pod ou departamento. O modelo pode ser usado para facilitar o gerenciamento de pacientes, bem como as necessidades operacionais de um bairro. Por exemplo, comunicados bairro podem ser remetidos no canal *anúncios* e deslocamentos podem ser gerenciados em *pessoal*. Se você estiver procurando para simplificar suas operações bairro, esse modelo é para você.

|Tipo de modelo base |baseTemplateId |Canais de modelo de linha de base|
|:--- |:---|:---|
|Saúde - bairro | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Anúncios\* <br> Huddles\* <br> Arredonda\* <br> Criação da equipe\* <br> Treinamento\* |
|     | |         |

\*Auto-favorited

## <a name="hospital-template"></a>Modelo do hospital

O modelo de hospital destina-se a comunicação e a colaboração entre vários departamentos em um hospital, pods e alas. Incluído nesse modelo são vários canais operacionais incluindo *comunicados*, *Custodial*e *farmácia*, mas também fornecemos um script abaixo do qual estende o modelo com uma variedade de departamento adicional ou especialidade centralizadas no canais que você pode adicionar, excluir da ou editar de sua preferência. Por exemplo, se você tiver um departamento de *Endocrinology* , mas não é necessário um canal para *Ophthalmology*, o script pode ser adaptado para incluir um canal *Endocrinology* e remova o canal de *Ophthalmology* . Recomendamos que estas especialidade ou canais bairro-modelada não sejam favorited automático para evitar a saturação da notificação. Usuários geralmente Favoritos quaisquer canais que eles encontrem relevantes.

|Tipo de modelo base |baseTemplateId |Canais de modelo de linha de base|
|:--- |:---|:---|
|Saúde - Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Anúncios\* <br> Conformidade\* <br> Custódia <br> Recursos humanos <br> Farmácia |
| | |  |

\*Auto-favorited 

## <a name="how-to-use-first-party-templates"></a>Como usar modelos de terceiros primeiro

Para usar esses modelos, basta altere a propriedade 'template@odata.bind' no corpo da solicitação de 'padrão' para o TemplateIDs acima.  Para obter mais informações sobre como implantar os modelos de equipes, consulte o [artigo sobre a criação de uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)do Microsoft Graph.

### <a name="example-hospital-template-extension-script"></a>Exemplo: Script de extensão do modelo de Hospital

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
              "displayName": "Women’s Health",
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
