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
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="eed0f-106">Controle de acesso baseado em função (RBAC) para Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eed0f-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="eed0f-107">O Skype for Business Server inclui Role-Based grupos de Controle de Acesso (RBAC) para permitir que você delegar tarefas administrativas enquanto mantém altos padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="eed0f-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="eed0f-108">Esses grupos são criados durante a preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="eed0f-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="eed0f-109">Para obter detalhes sobre a preparação da floresta, consulte [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="eed0f-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="eed0f-110">Para obter detalhes sobre os grupos específicos criados pela preparação da floresta, consulte Alterações feitas pela preparação da floresta no [Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="eed0f-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="eed0f-111">Com o RBAC, o privilégio administrativo é concedido atribuindo usuários a funções administrativas predefinidas, incluindo as 11 funções predefinidas que abrangem várias tarefas administrativas comuns.</span><span class="sxs-lookup"><span data-stu-id="eed0f-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="eed0f-112">Cada função está associada a uma lista específica de cmdlets do Shell de Gerenciamento do Skype for Business Server que os usuários nessa função têm permissão para executar.</span><span class="sxs-lookup"><span data-stu-id="eed0f-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="eed0f-113">Você pode usar o RBAC para seguir o princípio do "privilégio mínimo", onde os usuários recebem apenas as habilidades administrativas necessárias para seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="eed0f-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="eed0f-114">Mais detalhes sobre funções RBAC podem ser encontrados em [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="eed0f-114">More details on RBAC roles can be found at [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>