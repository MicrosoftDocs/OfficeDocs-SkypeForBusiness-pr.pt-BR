---
title: "Configurar permissões para o Who"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Orientações práticas para a implantação dos recursos de Cloud Voice no Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5afb795e98accc1e441572d5fc56da16cb4d75
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2018
---
<a name="configure-permissions-for-who"></a>Configurar permissões para o Who
=============================

Os usuários podem utilizar o aplicativo Who com o Microsoft Teams para ajudar a fazer perguntas e encontrar pessoas na organização com base naquilo em que estão trabalhando e com quem elas trabalham.

Para garantir que os usuários aproveitem o Who ao máximo, é necessário ativar as seguintes permissões de membros no Microsoft Graph.

- Calendars.Read

- Calendars.Read.Shared

- Mail.Read

- MailboxSettings.ReadWrite

- People.Read

- People.Read.All

- Sites.Read.All

- User.Read.All

Para obter mais informações sobre como gerenciar os escopos de permissões do Microsoft Graph, veja [Escopos de permissão](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).
 
Para obter mais informações sobre as permissões do Microsoft Graph, veja [Referência de permissões do Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).