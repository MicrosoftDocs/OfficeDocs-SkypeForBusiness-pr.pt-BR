---
title: "Configurar permissões para o Who"
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Orientações práticas para a implantação dos recursos de Cloud Voice no Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 629a732b178f6702f5ba308c6d0effe069019091
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
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

Para obter mais informações sobre como gerenciar os escopos de permissões do Microsoft Graph, veja [Escopos de permissão](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).
 
Para obter mais informações sobre as permissões do Microsoft Graph, veja [Referência de permissões do Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).