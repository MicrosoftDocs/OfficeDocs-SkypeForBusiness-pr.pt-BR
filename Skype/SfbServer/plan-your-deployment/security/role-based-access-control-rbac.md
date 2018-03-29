---
title: Controle de acesso baseado em função (RBAC) do Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype para Business Server 2015 inclui grupos de controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança. Estes grupos são criados durante a preparação da floresta. Para obter detalhes sobre a preparação da floresta, consulte serviços de domínio do Active Directory para Skype for Business Server 2015. Para obter detalhes sobre os grupos específicos criados pela preparação de floresta, consulte alterações feitas pela preparação de floresta no Skype para Business Server na documentação de implantação.
ms.openlocfilehash: f637ef752bb122cb73220d66fd8aa19c16fb358e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server-2015"></a><span data-ttu-id="451b3-106">Controle de acesso baseado em função (RBAC) do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="451b3-106">Role-based access control (RBAC) for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="451b3-107">Skype para Business Server 2015 inclui grupos de controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="451b3-107">Skype for Business Server 2015 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="451b3-108">Estes grupos são criados durante a preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="451b3-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="451b3-109">Para obter detalhes sobre a preparação da floresta, consulte [Serviços de domínio do Active Directory para Skype para Business Server 2015](active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="451b3-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server 2015](active-directory-domain-services.md).</span></span> <span data-ttu-id="451b3-110">Para obter detalhes sobre os grupos específicos criados pela preparação de floresta, consulte [alterações feitas pela preparação da floresta no Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="451b3-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="451b3-111">Com a RBAC, o privilégio administrativo é concedido através da atribuição de funções administrativas pré-definidas aos usuários, incluindo 11 funções pré-definidas que abrangem várias tarefas administrativas comuns.</span><span class="sxs-lookup"><span data-stu-id="451b3-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="451b3-112">Cada função é associada uma lista específica de cmdlets do Shell de gerenciamento do Lync Server que os usuários daquela função podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="451b3-112">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="451b3-113">Você pode utilizar a RBAC para seguir o princípio do "menor privilégio", no qual os usuários somente recebem as habilidades administrativas que seus trabalhos exigem.</span><span class="sxs-lookup"><span data-stu-id="451b3-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  

