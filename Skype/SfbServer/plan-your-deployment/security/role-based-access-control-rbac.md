---
title: Controle de acesso baseado em função (RBAC) para Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: O Skype for Business Server inclui Role-Based controle de acesso (RBAC) para permitir que você delegar tarefas administrativas enquanto mantém altos padrões de segurança. Esses grupos são criados durante a preparação da floresta. Para obter detalhes sobre a preparação da floresta, consulte Active Directory Domain Services for Skype for Business Server. Para obter detalhes sobre os grupos específicos criados pela preparação da floresta, consulte Changes made by forest preparation in Skype for Business Server in the Deployment documentation.
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832101"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Controle de acesso baseado em função (RBAC) para Skype for Business Server
 
O Skype for Business Server inclui Role-Based controle de acesso (RBAC) para permitir que você delegar tarefas administrativas enquanto mantém altos padrões de segurança. Esses grupos são criados durante a preparação da floresta. Para obter detalhes sobre a preparação da floresta, [consulte Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md). Para obter detalhes sobre os grupos específicos criados pela preparação da floresta, consulte [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.
  
Com o RBAC, o privilégio administrativo é concedido atribuindo usuários a funções administrativas predefinidas, incluindo as 11 funções predefinidas que abrangem várias tarefas administrativas comuns. Cada função é associada a uma lista específica de cmdlets do Shell de Gerenciamento do Skype for Business Server que os usuários nessa função têm permissão para executar. Você pode usar o RBAC para seguir o princípio do "privilégio mínimo", onde os usuários recebem apenas as habilidades administrativas necessárias para seu trabalho. 
  
Mais detalhes sobre as funções do RBAC podem ser encontrados no [Planejamento de controle de acesso baseado em função.](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)
