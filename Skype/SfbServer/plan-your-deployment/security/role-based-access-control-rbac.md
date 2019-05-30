---
title: Controle de acesso baseado em função (RBAC) para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: O Skype for Business Server inclui grupos de controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança. Estes grupos são criados durante a preparação da floresta. Para obter detalhes sobre a preparação da floresta, consulte serviços de domínio do Active Directory para o Skype for Business Server. Para obter detalhes sobre os grupos específicos criados pela preparação da floresta, consulte alterações feitas pela preparação da floresta no Skype for Business Server na documentação de implantação.
ms.openlocfilehash: a2c15766fd1b031247a5eb0f299e689bf075eb07
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548482"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Controle de acesso baseado em função (RBAC) para o Skype for Business Server
 
O Skype for Business Server inclui grupos de controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança. Estes grupos são criados durante a preparação da floresta. Para obter detalhes sobre a preparação da floresta, consulte [serviços de domínio do Active Directory para o Skype for Business Server](active-directory-domain-services.md). Para obter detalhes sobre os grupos específicos criados pela preparação da floresta, consulte [alterações feitas pela preparação da floresta no Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) na documentação de implantação.
  
Com a RBAC, o privilégio administrativo é concedido através da atribuição de funções administrativas pré-definidas aos usuários, incluindo 11 funções pré-definidas que abrangem várias tarefas administrativas comuns. Cada função é associada a uma lista específica de cmdlets do Shell de gerenciamento do Lync Server que os usuários da função têm permissão para executar. Você pode utilizar a RBAC para seguir o princípio do "menor privilégio", no qual os usuários somente recebem as habilidades administrativas que seus trabalhos exigem. 
  
Mais detalhes sobre as funções RBAC podem ser encontrados no [planejamento do controle de acesso baseado em função](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).
