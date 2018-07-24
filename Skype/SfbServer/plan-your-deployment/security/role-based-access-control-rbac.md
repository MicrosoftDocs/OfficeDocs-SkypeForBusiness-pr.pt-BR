---
title: Controle de acesso baseado em função (RBAC) para Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype para Business Server inclui grupos de controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança. Estes grupos são criados durante a preparação da floresta. Para obter detalhes sobre a preparação da floresta, consulte serviços de domínio do Active Directory para Skype for Business Server. Para obter detalhes sobre os grupos específicos criados pela preparação de floresta, consulte alterações feitas pela preparação de floresta no Skype para Business Server na documentação de implantação.
ms.openlocfilehash: b0029ec683bec29da187ecd23dd0c3230fc603a5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967688"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Controle de acesso baseado em função (RBAC) para Skype para Business Server
 
Skype para Business Server inclui grupos de controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança. Estes grupos são criados durante a preparação da floresta. Para obter detalhes sobre a preparação da floresta, consulte [Serviços de domínio do Active Directory para Skype para Business Server](active-directory-domain-services.md). Para obter detalhes sobre os grupos específicos criados pela preparação de floresta, consulte [alterações feitas pela preparação da floresta no Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) na documentação de implantação.
  
Com a RBAC, o privilégio administrativo é concedido através da atribuição de funções administrativas pré-definidas aos usuários, incluindo 11 funções pré-definidas que abrangem várias tarefas administrativas comuns. Cada função é associada uma lista específica de cmdlets do Shell de gerenciamento do Lync Server que os usuários daquela função podem ser executados. Você pode utilizar a RBAC para seguir o princípio do "menor privilégio", no qual os usuários somente recebem as habilidades administrativas que seus trabalhos exigem. 
  
Obter mais detalhes sobre as funções RBAC podem ser encontradas em:https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx
