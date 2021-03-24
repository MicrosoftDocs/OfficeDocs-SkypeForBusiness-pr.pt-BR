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
description: O Skype for Business Server inclui Role-Based grupos de Controle de Acesso (RBAC) para permitir que você delegar tarefas administrativas enquanto mantém altos padrões de segurança. Esses grupos são criados durante a preparação da floresta. Para obter detalhes sobre a preparação da floresta, consulte Serviços de Domínio do Active Directory para Skype for Business Server. Para obter detalhes sobre os grupos específicos criados pela preparação da floresta, consulte Alterações feitas pela preparação da floresta no Skype for Business Server na documentação de implantação.
ms.openlocfilehash: e02123721433e2af0ca3576ac71dd5a49a0ad9a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104207"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Controle de acesso baseado em função (RBAC) para Skype for Business Server
 
O Skype for Business Server inclui Role-Based grupos de Controle de Acesso (RBAC) para permitir que você delegar tarefas administrativas enquanto mantém altos padrões de segurança. Esses grupos são criados durante a preparação da floresta. Para obter detalhes sobre a preparação da floresta, consulte [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md). Para obter detalhes sobre os grupos específicos criados pela preparação da floresta, consulte Alterações feitas pela preparação da floresta no [Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) na documentação de implantação.
  
Com o RBAC, o privilégio administrativo é concedido atribuindo usuários a funções administrativas predefinidas, incluindo as 11 funções predefinidas que abrangem várias tarefas administrativas comuns. Cada função está associada a uma lista específica de cmdlets do Shell de Gerenciamento do Skype for Business Server que os usuários nessa função têm permissão para executar. Você pode usar o RBAC para seguir o princípio do "privilégio mínimo", onde os usuários recebem apenas as habilidades administrativas necessárias para seu trabalho. 
  
Mais detalhes sobre funções RBAC podem ser encontrados em [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).