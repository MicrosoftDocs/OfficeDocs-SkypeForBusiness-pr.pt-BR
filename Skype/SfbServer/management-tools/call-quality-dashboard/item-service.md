---
title: Painel de serviço de item para o painel de qualidade da chamada (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumo: Saiba mais sobre o serviço de item, que faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274608"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="07581-104">Painel de serviço de item para o painel de qualidade da chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="07581-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="07581-105">**Resumo:** Saiba mais sobre o serviço de item, que faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="07581-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="07581-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="07581-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="07581-107">O serviço de item faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="07581-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="07581-108">Serviço de itens</span><span class="sxs-lookup"><span data-stu-id="07581-108">Item Service</span></span>

<span data-ttu-id="07581-109">A API do repositório oferece um serviço de gerenciamento de conteúdo simples, conhecido como serviço de item, que pode ser usado para armazenar qualquer conteúdo definido pelo aplicativo para os usuários.</span><span class="sxs-lookup"><span data-stu-id="07581-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="07581-110">O conteúdo do sistema é de Propriedade do usuário do sistema e compartilhado por todos os usuários com acesso somente leitura.</span><span class="sxs-lookup"><span data-stu-id="07581-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="07581-111">O conteúdo do usuário exclusivo pertence a usuários regulares, e somente os proprietários podem modificá-los ou excluí-los, mas todos os usuários ainda têm acesso somente leitura a eles.</span><span class="sxs-lookup"><span data-stu-id="07581-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07581-112">Esta documentação de API aborda operações somente leitura da API do repositório.</span><span class="sxs-lookup"><span data-stu-id="07581-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="07581-113">O painel de qualidade de chamada salva relatórios e consultas como itens no banco de dados do repositório.</span><span class="sxs-lookup"><span data-stu-id="07581-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="07581-114">Um item pode ter subitens opcionais, e o painel de qualidade da chamada organiza relatórios e consultas em uma estrutura hierárquica usando o recurso de subitens.</span><span class="sxs-lookup"><span data-stu-id="07581-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="07581-115">O serviço de item inclui os seguintes conceitos:</span><span class="sxs-lookup"><span data-stu-id="07581-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="07581-116">**Item** -o elemento básico do repositório.</span><span class="sxs-lookup"><span data-stu-id="07581-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="07581-117">Cada item pertence a exatamente um usuário.</span><span class="sxs-lookup"><span data-stu-id="07581-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="07581-118">**Subitem** -a mecânica organizacional básica do repositório.</span><span class="sxs-lookup"><span data-stu-id="07581-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="07581-119">O item pode ter zero, um ou mais itens subordinados.</span><span class="sxs-lookup"><span data-stu-id="07581-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="07581-120">**Item ancestrais** -a lista de itens, a partir do item mais superior, que é o item padrão do usuário, que leva a um determinado item.</span><span class="sxs-lookup"><span data-stu-id="07581-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="07581-121">**Conteúdo do item** – o conteúdo específico do aplicativo armazenado em itens.</span><span class="sxs-lookup"><span data-stu-id="07581-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="07581-122">Painel de qualidade de chamada salva representações JSON de relatórios e consultas no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="07581-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="07581-123">As operações REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="07581-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="07581-124">**Operação**</span><span class="sxs-lookup"><span data-stu-id="07581-124">**Operation**</span></span>|<span data-ttu-id="07581-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="07581-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="07581-126">Obter itens</span><span class="sxs-lookup"><span data-stu-id="07581-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="07581-127">Obter itens retorna todos os itens no repositório.</span><span class="sxs-lookup"><span data-stu-id="07581-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="07581-128">Obter item</span><span class="sxs-lookup"><span data-stu-id="07581-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="07581-129">Obter item retorna um item específico.</span><span class="sxs-lookup"><span data-stu-id="07581-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="07581-130">Obter subitens</span><span class="sxs-lookup"><span data-stu-id="07581-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="07581-131">Obter subitens retorna os subitens de um item específico.</span><span class="sxs-lookup"><span data-stu-id="07581-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="07581-132">Obter o Item Predecessor</span><span class="sxs-lookup"><span data-stu-id="07581-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="07581-133">Obter item ancestrais retorna os ancestrais de um item específico.</span><span class="sxs-lookup"><span data-stu-id="07581-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="07581-134">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="07581-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="07581-135">Atualize um item específico no repositório.</span><span class="sxs-lookup"><span data-stu-id="07581-135">Update a specific item in the repository.</span></span>  <br/> |
   

