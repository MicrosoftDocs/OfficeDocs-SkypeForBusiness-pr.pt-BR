---
title: Criar uma equipe usando modelos de assistência médica do Teams
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
description: Use modelos do Microsoft Teams no centro de administração ou com o Microsoft Graph para criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260303"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Criar uma equipe usando modelos de assistência médica do Teams

Os modelos do Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.

Para organizações de saúde, os modelos podem ser especialmente eficientes, à medida que fornecem uma estrutura para que os usuários se orientem com como usar as Equipes com eficácia. Os modelos também permitem que os administradores implantem equipes consistentes em suas organizações. Este artigo é para você, se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização de assistência médica.

Escolha um método para criar equipes com os modelos de assistência médica do Teams:

| Quem | Método a ser usado: |
| ---- | --------- |
| Administradores e profissionais de TI | [Use o centro de administração de equipes](#use-the-teams-templates-in-the-teams-admin-center) para criar equipes com base nos modelos de equipes de assistência médica.|
| Os desenvolvedores e integradores de sistemas | [Use o Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) para criar equipes com base nos modelos de equipes de assistência médica. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Usar os modelos do Teams no Centro de administração do Teams

Os administradores do Microsoft Teams podem usar o Centro de administração do Teams para criar equipes com os modelos do Teams. Atualmente, oferecemos dois modelos de assistência médica de terceiros que você pode usar para diversas situações. Para saber mais sobre modelos de equipe em geral, confira [Começar a usar os modelos do Teams no centro de administração](../../get-started-with-teams-templates-in-the-admin-console.md).

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


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Usar os modelos do Teams com o Microsoft Graph

Os desenvolvedores podem usar o Microsoft Graph para criar equipes com os modelos do Teams. Atualmente, oferecemos dois modelos de assistência médica de terceiros que você pode usar para diversas situações. Para saber mais sobre modelos de equipe em geral, confira [a1/10 sobre modelos do Teams](../../get-started-with-teams-templates.md). E para saber mais sobre modelos do Teams e o Microsoft Graph, confira [visão geral da API do Microsoft Teams](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) e [de recursos de equipesTemplate](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).

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

Para usar esses modelos, basta alterar a propriedade "template@odata.bind" no corpo da solicitação de "padrão" para as TemplateIDs acima.  Para saber mais sobre como implantar modelos do Teams, confira o artigo do Microsoft Graph sobre como [criar um Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

[Introdução aos modelos do Teams](../../get-started-with-teams-templates.md)

[Introdução ao Teams para Organizações de Saúde](teams-in-hc.md)
