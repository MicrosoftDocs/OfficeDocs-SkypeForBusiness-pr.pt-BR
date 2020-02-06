---
title: Serviço de usuário para CQD
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumo: Saiba mais sobre o serviço de usuário, que faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816650"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="19b49-104">Serviço de usuário para CQD</span><span class="sxs-lookup"><span data-stu-id="19b49-104">User Service for CQD</span></span>
 
<span data-ttu-id="19b49-105">**Resumo:** Saiba mais sobre o serviço de usuário, que faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="19b49-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="19b49-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19b49-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="19b49-107">O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="19b49-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="19b49-108">Serviço do usuário</span><span class="sxs-lookup"><span data-stu-id="19b49-108">User Service</span></span>

<span data-ttu-id="19b49-109">A API do repositório fornece um modelo simplificado de gerenciamento de usuários onde o provisionamento do usuário (criação de novas contas de usuário) é automático e implícito.</span><span class="sxs-lookup"><span data-stu-id="19b49-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="19b49-110">Quando um usuário faz uma solicitação em relação à API do repositório pela primeira vez, o repositório cria um novo registro de usuário.</span><span class="sxs-lookup"><span data-stu-id="19b49-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="19b49-111">O painel de qualidade de chamada também cria automaticamente itens dedicados do usuário para o novo usuário.</span><span class="sxs-lookup"><span data-stu-id="19b49-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="19b49-112">Os novos itens dedicados do usuário são clones completos dos itens do usuário do sistema.</span><span class="sxs-lookup"><span data-stu-id="19b49-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="19b49-113">Dessa forma, os usuários começam com suas próprias cópias de relatórios e consultas que podem iniciar a personalização imediatamente.</span><span class="sxs-lookup"><span data-stu-id="19b49-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="19b49-114">Usando o painel de qualidade da chamada, os usuários podem redefinir seus itens dedicados a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="19b49-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="19b49-115">**IDs de usuário especiais**</span><span class="sxs-lookup"><span data-stu-id="19b49-115">**Special User IDs**</span></span>
  
<span data-ttu-id="19b49-116">A API do repositório inclui URIs de API REST que esperam um valor inteiro para especificar um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="19b49-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="19b49-117">Exemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="19b49-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="19b49-118">Aqui, {userId} deve ser substituído por um valor inteiro, como 0, 1, etc.</span><span class="sxs-lookup"><span data-stu-id="19b49-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="19b49-119">Além disso, a API do repositório aceitará duas IDs de usuário especiais em {userId} em URIs.</span><span class="sxs-lookup"><span data-stu-id="19b49-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="19b49-120">*padrão* -representa o usuário que está interagindo com a API no momento.</span><span class="sxs-lookup"><span data-stu-id="19b49-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="19b49-121">Isso permite que os aplicativos acessem o conteúdo do usuário atual sem acompanhar o valor real da ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="19b49-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="19b49-122">Exemplo: `https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="19b49-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="19b49-123">*System* -representa o usuário do sistema.</span><span class="sxs-lookup"><span data-stu-id="19b49-123">*system*  - represents the system user.</span></span> <span data-ttu-id="19b49-124">Isso permite que os aplicativos acessem o conteúdo do usuário do sistema sem conhecer o valor real da ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="19b49-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="19b49-125">Exemplo: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="19b49-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="19b49-126">A menos que indicado de outra forma, as IDs de usuário especiais podem ser usadas em {userId} em URIs.</span><span class="sxs-lookup"><span data-stu-id="19b49-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="19b49-127">As operações REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="19b49-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="19b49-128">**Operação**</span><span class="sxs-lookup"><span data-stu-id="19b49-128">**Operation**</span></span>|<span data-ttu-id="19b49-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="19b49-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="19b49-130">Obter usuários</span><span class="sxs-lookup"><span data-stu-id="19b49-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="19b49-131">Retorna uma lista de usuários no repositório.</span><span class="sxs-lookup"><span data-stu-id="19b49-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="19b49-132">Obter usuário</span><span class="sxs-lookup"><span data-stu-id="19b49-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="19b49-133">Retorna um registro de usuário.</span><span class="sxs-lookup"><span data-stu-id="19b49-133">Returns a user record.</span></span>  <br/> |
   

