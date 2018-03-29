---
title: Serviço de item para o painel de controle de qualidade de chamada (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumo: Saiba mais sobre o serviço de Item, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 218fdb4f2c4b3d73fb4e7f78b5679b66eecf34cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="92368-104">Serviço de item para o painel de controle de qualidade de chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="92368-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="92368-105">**Resumo:** Saiba mais sobre o serviço de Item, que é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="92368-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="92368-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="92368-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="92368-107">O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="92368-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="92368-108">Serviço de item</span><span class="sxs-lookup"><span data-stu-id="92368-108">Item Service</span></span>

<span data-ttu-id="92368-109">API do repositório oferece um serviço de gerenciamento de conteúdo simples, conhecido como serviço de item, que pode ser usado para armazenar qualquer conteúdo definido pelo aplicativo para usuários.</span><span class="sxs-lookup"><span data-stu-id="92368-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="92368-110">O conteúdo do sistema é pertencentes ao usuário do sistema e compartilhado por todos os usuários com acesso somente leitura.</span><span class="sxs-lookup"><span data-stu-id="92368-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="92368-111">Conteúdo de usuário dedicada pertencentes a usuários regulares e somente os proprietários podem modificar ou excluí-los, mas todos os usuários ainda têm acesso somente leitura a eles.</span><span class="sxs-lookup"><span data-stu-id="92368-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="92368-112">Esta documentação de API abrange operações somente leitura da API do repositório.</span><span class="sxs-lookup"><span data-stu-id="92368-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="92368-113">Painel de controle de qualidade de chamada salva relatórios e consultas como itens do banco de dados do repositório.</span><span class="sxs-lookup"><span data-stu-id="92368-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="92368-114">Um Item pode ter itens sub-recurso opcionais e painel de controle de qualidade de chamada organiza relatórios e consultas em uma estrutura hierárquica usando o recurso de subitens.</span><span class="sxs-lookup"><span data-stu-id="92368-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="92368-115">O serviço de item inclui os seguintes conceitos:</span><span class="sxs-lookup"><span data-stu-id="92368-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="92368-116">**Item** - o elemento básico de repositório.</span><span class="sxs-lookup"><span data-stu-id="92368-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="92368-117">Cada Item pertence ao usuário exatamente uma.</span><span class="sxs-lookup"><span data-stu-id="92368-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="92368-118">**Item de suba** mecânica organizacional básica do repositório.</span><span class="sxs-lookup"><span data-stu-id="92368-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="92368-119">O item pode ter zero, um ou mais itens de subordinados.</span><span class="sxs-lookup"><span data-stu-id="92368-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="92368-120">**Item ancestrais** - a lista de itens, o Item superior, que é o padrão de Item do usuário, levando a um determinado Item tem início.</span><span class="sxs-lookup"><span data-stu-id="92368-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="92368-121">**Item de conteúdo** - o conteúdo de aplicativo específico armazenado em itens.</span><span class="sxs-lookup"><span data-stu-id="92368-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="92368-122">Painel de controle de qualidade de chamada salva as representações de JSON de relatórios e consultas no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="92368-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="92368-123">As operações do REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="92368-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="92368-124">**Operação**</span><span class="sxs-lookup"><span data-stu-id="92368-124">**Operation**</span></span>|<span data-ttu-id="92368-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="92368-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="92368-126">Obter itens</span><span class="sxs-lookup"><span data-stu-id="92368-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="92368-127">Obter itens retorna todos os itens no repositório.</span><span class="sxs-lookup"><span data-stu-id="92368-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="92368-128">Obtenha Item</span><span class="sxs-lookup"><span data-stu-id="92368-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="92368-129">Obtenha o Item Retorna um Item específico.</span><span class="sxs-lookup"><span data-stu-id="92368-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="92368-130">Obter itens sub-recurso</span><span class="sxs-lookup"><span data-stu-id="92368-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="92368-131">Obter itens sub-recurso retorna subitens de um Item específico.</span><span class="sxs-lookup"><span data-stu-id="92368-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="92368-132">Obter ancestrais do Item</span><span class="sxs-lookup"><span data-stu-id="92368-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="92368-133">Get Item ancestrais retorna ancestrais de um Item específico.</span><span class="sxs-lookup"><span data-stu-id="92368-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="92368-134">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="92368-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="92368-135">Atualize um item específico no repositório.</span><span class="sxs-lookup"><span data-stu-id="92368-135">Update a specific item in the repository.</span></span>  <br/> |
   

