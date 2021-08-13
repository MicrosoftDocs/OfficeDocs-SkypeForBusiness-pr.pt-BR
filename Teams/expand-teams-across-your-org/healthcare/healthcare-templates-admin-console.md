---
title: Criar uma equipe usando modelos de saúde
author: cichur
ms.author: v-cichur
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
description: Use modelos de equipe no centro de administração ou com o Microsoft Graph para criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 050ddd4e9efabe3433257f0497081758767e1cfa38c16aa1102ff17554ce3391
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336251"
---
# <a name="use-a-healthcare-team-templates"></a>Usar modelos de equipe de saúde

Os modelos permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Para organizações de saúde, os modelos podem ser especialmente poderosos, pois fornecem estrutura para que os usuários se orientem com como usar efetivamente Microsoft Teams. Os modelos também permitem que os administradores implantem equipes consistentes em suas organizações. Este artigo é para você, se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização de assistência médica.

Escolha um método para criar equipes com os modelos de saúde da equipe:

| Quem | Método a ser usado: |
| ---- | --------- |
| Administradores e profissionais de TI | [Use o Teams de administração](#use-the-team-templates-in-the-admin-center) para criar equipes com base nos modelos de equipe de saúde.|
| Os desenvolvedores e integradores de sistemas | [Use o microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) para criar uma equipe com base nos modelos de equipe de saúde. |

## <a name="use-the-team-templates-in-the-admin-center"></a>Usar os modelos de equipe no centro de administração

Microsoft Teams os administradores podem usar o Teams de administração para criar equipes com os modelos de equipe. Atualmente, oferecemos dois modelos de assistência médica de terceiros que você pode usar para diversas situações. Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar modelos de equipe no centro de administração](../../get-started-with-teams-templates-in-the-admin-console.md).

### <a name="collaborate-on-patient-care"></a>Colabore no atendimento aos pacientes

 Simplifique a comunicação e a colaboração dos serviços de saúde dentro de um departamento, um ou mais. O modelo pode ser usado para facilitar o gerenciamento dos pacientes e as necessidades operacionais de um paciente.

| Tipo de modelo base |baseTemplateId| Propriedades que vêm com este modelo base |
| ------------------ |---|----------------------------------------------------- |
| Colabore no atendimento aos pacientes |`healthcareWard` | Canais:<ul><li>Geral</li><li>Comunicados</li><li>Insuidades</li><li>Rodadas</li><li>Estrelada</li><li>Treinamento</li></ul> Apps: <ul><li>Wiki</li><li>Listas</li></ul>|
||||

### <a name="hospital"></a>Hospital

Simplifique a comunicação e a colaboração entre vários funcionários, funcionários e departamentos dentro de um hospital. Esse modelo inclui um conjunto de canais base para operações hospital e pode ser autoprofundado para incluir especialidades, ad-hoc.

| Tipo de modelo base |baseTemplateId | Propriedades que vêm com este modelo base |
| ------------------|-- |----------------------------------------------------- |
|Hospital|`healthcareHospital`|Canais: <ul><li>Geral</li><li>Comunicados</li><li>Conformidade</li><li>Custódia</li><li>Recursos humanos</li><li>Farmácia</li></ul> Apps: <ul><li>Wiki</li><li>Listas </li></ul>|
||||


## <a name="use-the-team-templates-with-the-microsoft-graph"></a>Use os modelos de equipe com o microsoft Graph

Os desenvolvedores podem usar o microsoft Graph para criar equipes com os modelos de equipe. Atualmente, oferecemos dois modelos de assistência médica de terceiros que você pode usar para diversas situações. Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar modelos de equipe.](../../get-started-with-teams-templates.md) E para obter informações sobre modelos de equipe e o microsoft Graph, [consulte Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) visão geral da API e tipo de recurso [teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="ward-template"></a>Modelo de modelo de modelo

O modelo de design é destinado à comunicação e à colaboração dentro de um departamento, duas ou mais áreas. O modelo pode ser usado para facilitar o gerenciamento dos pacientes, bem como para as necessidades operacionais de um paciente. Por exemplo, comunicados completos podem ser postados no canal *Comunicados* e turnos podem ser gerenciados no *Equipe*. Se você estiver tentando simplificar suas operações normais, este modelo é para você.

|Tipo de Modelo Base |baseTemplateId |Canais de modelo de linha de base|
|:--- |:---|:---|
|Assistência médica – Assist. | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Anúncios\* <br> Insuidades\* <br> Rodadas\* <br> Pessoal\* <br> Treinamento\* |
|     | |         |

\* Favoritos automáticos

### <a name="hospital-template"></a>Modelo de hospital

O modelo hospital é destinado à comunicação e colaboração entre vários funcionários, funcionários e departamentos em um hospital. Incluídos neste modelo estão vários canais operacionais, incluindo *Anúncios*, *Custódia* e *Farmácia*, mas também fornecemos um script abaixo que estende o modelo com uma variedade de departamentos adicionais ou canais centrados em especialidades que você pode adicionar, excluir ou editar seu gosto. Por exemplo, se você tem um departamento de *Endocrinologia*, mas não precisa de um canal para *Oftalmologia*, o script pode ser adaptado para incluir um canal de *Endocrinologia* e remover o canal de *Oftalmologia*. Recomendamos que esses canais especializados ou modelados não sejam favoritos automaticamente para evitar saturação da notificação. Os usuários geralmente favoritam os canais que acham relevantes.

|Tipo de Modelo Base |baseTemplateId |Canais de modelo de linha de base|
|:--- |:---|:---|
|Assistência médica – Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Anúncios\* <br> Conformidade\* <br> Custódia <br> Recursos Humanos <br> Farmácia |
| | |  |

\* Favoritos automáticos 

### <a name="how-to-use-first-party-templates"></a>Como usar modelos de terceiros

Para usar esses modelos, basta alterar a propriedade "template@odata.bind" no corpo da solicitação de "padrão" para as TemplateIDs acima.  Para obter mais informações sobre como implantar modelos de equipe, consulte o artigo do Microsoft Graph sobre como [criar uma equipe.](/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Os canais no modelo serão criados automaticamente na guia Geral.

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

### <a name="related-topics"></a>Tópicos relacionados

[Começar a usar modelos de equipe](../../get-started-with-teams-templates.md)

[Começar com a equipe para organizações de saúde](teams-in-hc.md)