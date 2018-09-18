---
title: Introdução ao modelos de equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Saiba como usar modelos de equipes para criar uma equipe com canais predefinidos.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7850ad245eebee96b6852e7f0cc57a35adcca9f7
ms.sourcegitcommit: 8a56ed2107dfa378864576d1e137ab0086f5da08
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "23996235"
---
# <a name="get-started-with-teams-templates"></a>Introdução ao modelos de equipes 

Modelos de equipe são pré-criados definições da estrutura de uma equipe Projetado levando em consideração uma necessidade comercial ou projeto. Você pode usar modelos de equipe para criar rapidamente os espaços de colaboração avançada com canais para tópicos diferentes e pré-instalação de aplicativos seja obtida dos planejamentos nos serviços e conteúdo de missão crítica. Os modelos de equipe fornecem uma estrutura de equipe predefinidas que pode ajudá-lo a criar facilmente equipes consistentes em toda a organização. 

Neste artigo, vamos explicar as propriedades que podem ser definidas nos modelos, qual modelo base tipos forem, e como você pode usar algumas solicitações para criar uma equipe a partir de um modelo de exemplo.
 
Este artigo é para você, se você estiver:

• Responsáveis por planejar, implantar e gerenciando várias equipes entre seu desenvolvedor de • uma organização procurando para criar uma equipe com canais e predefinidos aplicativos programaticamente

## <a name="team-template-capabilities"></a>Recursos do modelo de equipe

A maioria das propriedades em uma equipe são incluídas e suportado por modelos. No entanto, há algumas propriedades e recursos que não são suportados atualmente. A tabela a seguir fornece um resumo rápido o que está incluído e o que não está incluído nos modelos de equipes.

| **Propriedades da equipe compatíveis com os modelos de equipes** | **Propriedades da equipe ainda não é suportadas por modelos de equipes** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Tipo de modelo base | Associação de equipe |
| Nome da equipe | Imagem de equipe |
| Descrição da equipe | Configurações de canal (por exemplo, autofavorito e privacidade) |
| Visibilidade de equipe (pública ou privada) | Conectores |
| Configurações de equipe (por exemplo, o membro, o convidado, @ menções) | Arquivos e conteúdo |
| Autofavorito canal | |
| Aplicativo instalado | |
| Guias fixados | | 

> [!NOTE]
> Podemos vai ser adicionando mais recursos de modelo em versões futuras do Microsoft Teams, portanto, verifique novamente para obter as informações mais atualizadas sobre propriedades com suporte.

## <a name="what-are-base-template-types"></a>Quais são os tipos de modelo base?

Tipos de modelo base são modelos especiais que a Microsoft criou para setores específicos. Esses modelos base geralmente contêm proprietários aplicativos que não estão disponíveis nas propriedades do repositório e a equipe que ainda não suportadas individualmente nos modelos de equipes.

Depois que um tipo de modelo base é definido, você pode estender ou substituir esses modelos especiais com propriedades adicionais que você gostaria de especificar. No entanto, alguns tipos de modelo base contêm propriedades que não podem ser substituídas. 

Por padrão, o modelo base é definido para o **padrão** que não contenha nenhum apps proprietárias adicionais ou propriedades especiais. Abaixo é a lista atual de tipos de base modelos disponíveis.

| Tipo de modelo base | baseTemplateId | Aplicativos de proprietário do modelo base e propriedades especiais |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | Não há aplicativos adicionais e propriedades |
| Saúde - coordenação de atendimento médico | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | Aplicativos:<br/> -App os pacientes (fixado a guia **Geral** )<br/> <br/>Canais: <br/> -Comunicados<br/> -Diabetes<br/> -Cardiovascular<br/> -Registered enfermeiras |
| Saúde - huddle de processo | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | Canais:<br/> -Evitáveis mortes<br/> -Revisão mortality <br/> -Impedindo divide-se <br/> -Planos de sepsis |
| Educação - classe equipe<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | Aplicativos:<br/> -Bloco de anotações de classe OneNote (fixados a guia **Geral** ) <br/> -App atribuições (fixado a guia **Geral** ) <br/><br/> Propriedades da equipe <br/> -Visibilidade equipe definida como **HiddenMembership** (não pode ser substituída) |
| A equipe de educação - equipe<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | Aplicativos<br/> -Bloco de anotações da equipe OneNote (fixados a guia **Geral** ) |

Publicação de <sup>1</sup> em outubro de 2018 tardia

> [!NOTE]
> Serão adicionados mais modelo base digita em futuras versões do Microsoft Teams, para verificar novamente as informações mais atualizadas sobre suporte a propriedades.

## <a name="examples"></a>Exemplos 

Você pode iniciar a criação de uma equipe via modelo instalando o [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).

### <a name="create-a-team-from-a-template"></a>Crie uma equipe a partir de um modelo

#### <a name="requests"></a>Solicitações

**Solicitação para criar uma equipe com o modelo base standard**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

**Solicitação para criar uma equipe com um canal extra e invalidar membros excluam canais**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

**Solicitação para criar uma equipe com todas as propriedades com suporte**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
        }
    ],
 
     "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
      },
 
      "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
      },
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a>Resposta

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
}
~~~

### <a name="get-status"></a>Obter o status

#### <a name="request"></a>Solicitação

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a>Resposta

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a>Tópicos relacionados

- [Criar equipe](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (no modo de visualização)
- [Nova equipe](https://docs.microsoft.com/en-us/powershell/module/teams/New-Team?view=teams-ps)
- [Treinamento para o administrador do Microsoft Teams](itadmin-readiness.md)