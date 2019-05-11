---
title: Serviço de usuário para CQD
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumo: Saiba mais sobre o serviço de usuário, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 631ccfefe7a4503f325c288ef1bf27d4366869e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915077"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="b6406-104">Serviço de usuário para CQD</span><span class="sxs-lookup"><span data-stu-id="b6406-104">User Service for CQD</span></span>
 
<span data-ttu-id="b6406-105">**Resumo:** Saiba mais sobre o serviço de usuário, que é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="b6406-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b6406-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b6406-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b6406-107">O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="b6406-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="b6406-108">Serviço do usuário</span><span class="sxs-lookup"><span data-stu-id="b6406-108">User Service</span></span>

<span data-ttu-id="b6406-109">API do repositório fornece um modelo de gerenciamento de usuário simplificada onde o provisionamento (criando novas contas de usuário) do usuário é automático e implícita.</span><span class="sxs-lookup"><span data-stu-id="b6406-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="b6406-110">Quando um usuário faz uma solicitação em relação a API do repositório pela primeira vez, o repositório cria um novo registro de usuário.</span><span class="sxs-lookup"><span data-stu-id="b6406-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="b6406-111">Painel de controle de qualidade também cria automaticamente um usuário de chamada dedicada itens para o novo usuário.</span><span class="sxs-lookup"><span data-stu-id="b6406-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="b6406-112">Os novos itens de usuário dedicado são clones completas dos itens do usuário do sistema.</span><span class="sxs-lookup"><span data-stu-id="b6406-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="b6406-113">Dessa forma, os usuários começam com suas próprias cópias de relatórios e consultas que eles podem iniciar imediatamente personalizando.</span><span class="sxs-lookup"><span data-stu-id="b6406-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b6406-114">Usando o painel de controle de qualidade de chamada, os usuários podem redefinir seus itens dedicados a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="b6406-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="b6406-115">**IDs de usuário especiais**</span><span class="sxs-lookup"><span data-stu-id="b6406-115">**Special User IDs**</span></span>
  
<span data-ttu-id="b6406-116">API do repositório inclui REST API URIs que espera um valor inteiro para especificar um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="b6406-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="b6406-117">Exemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="b6406-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="b6406-118">Aqui, {userId} deverão ser substituído por um valor inteiro, como 0, 1, etc.</span><span class="sxs-lookup"><span data-stu-id="b6406-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="b6406-119">Além disso, a API do repositório aceitará duas identificações de usuário especiais em {userId} em URIs.</span><span class="sxs-lookup"><span data-stu-id="b6406-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="b6406-120">*padrão* - representa o usuário que está atualmente interagindo com a API.</span><span class="sxs-lookup"><span data-stu-id="b6406-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="b6406-121">Isso permite aos aplicativos acessar o conteúdo do usuário atual sem manter o controle do valor de ID de usuário real.</span><span class="sxs-lookup"><span data-stu-id="b6406-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="b6406-122">Exemplo: ` https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="b6406-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="b6406-123">*sistema* - representa o usuário do sistema.</span><span class="sxs-lookup"><span data-stu-id="b6406-123">*system*  - represents the system user.</span></span> <span data-ttu-id="b6406-124">Isso permite aos aplicativos acessar o conteúdo do usuário do sistema sem saber o valor de ID de usuário real.</span><span class="sxs-lookup"><span data-stu-id="b6406-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="b6406-125">Exemplo: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="b6406-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="b6406-126">Salvo indicação contrária, as IDs de usuário especiais podem ser usado em {userId} em URIs.</span><span class="sxs-lookup"><span data-stu-id="b6406-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="b6406-127">As operações do REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b6406-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="b6406-128">**Operação**</span><span class="sxs-lookup"><span data-stu-id="b6406-128">**Operation**</span></span>|<span data-ttu-id="b6406-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b6406-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b6406-130">Obter usuários</span><span class="sxs-lookup"><span data-stu-id="b6406-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="b6406-131">Retorna uma lista de usuários no repositório.</span><span class="sxs-lookup"><span data-stu-id="b6406-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="b6406-132">Obter usuário</span><span class="sxs-lookup"><span data-stu-id="b6406-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="b6406-133">Retorna um registro de usuário.</span><span class="sxs-lookup"><span data-stu-id="b6406-133">Returns a user record.</span></span>  <br/> |
   

