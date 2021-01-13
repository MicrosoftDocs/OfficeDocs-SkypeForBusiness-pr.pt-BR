---
title: Serviço de Item para Painel de Qualidade de Chamada (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumo: saiba mais sobre o Serviço de Item, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827701"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="c52bf-104">Serviço de Item para Painel de Qualidade de Chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="c52bf-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="c52bf-105">**Resumo:** Saiba mais sobre o Serviço de Item, que faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="c52bf-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c52bf-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c52bf-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c52bf-107">O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="c52bf-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="c52bf-108">Serviço de Itens</span><span class="sxs-lookup"><span data-stu-id="c52bf-108">Item Service</span></span>

<span data-ttu-id="c52bf-109">A API de repositório oferece um serviço de gerenciamento de conteúdo simples, conhecido como serviço de item, que pode ser usado para armazenar qualquer conteúdo definido pelo aplicativo para os usuários.</span><span class="sxs-lookup"><span data-stu-id="c52bf-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="c52bf-110">O conteúdo do sistema é de propriedade do usuário do sistema e compartilhado por todos os usuários com acesso somente leitura.</span><span class="sxs-lookup"><span data-stu-id="c52bf-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="c52bf-111">O conteúdo dedicado do usuário pertence a usuários regulares e somente os proprietários podem modificá-los ou excluí-los, mas todos os usuários ainda têm acesso somente leitura a eles.</span><span class="sxs-lookup"><span data-stu-id="c52bf-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c52bf-112">Esta documentação da API abrange operações somente leitura da API de Repositório.</span><span class="sxs-lookup"><span data-stu-id="c52bf-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="c52bf-113">O Painel de Qualidade da Chamada salva Relatórios e Consultas como Itens no banco de dados de repositório.</span><span class="sxs-lookup"><span data-stu-id="c52bf-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="c52bf-114">Um Item pode ter sub-itens opcionais, e o Painel de Qualidade de Chamada organiza relatórios e consultas em uma estrutura hierárquica usando o recurso sub-itens.</span><span class="sxs-lookup"><span data-stu-id="c52bf-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="c52bf-115">O serviço de item inclui os seguintes conceitos:</span><span class="sxs-lookup"><span data-stu-id="c52bf-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="c52bf-116">**Item** - o elemento básico do repositório.</span><span class="sxs-lookup"><span data-stu-id="c52bf-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="c52bf-117">Cada item pertence a exatamente um usuário.</span><span class="sxs-lookup"><span data-stu-id="c52bf-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="c52bf-118">**Sub-Item** - a mecânica organizacional básica do repositório.</span><span class="sxs-lookup"><span data-stu-id="c52bf-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="c52bf-119">O item pode ter zero, um ou mais itens subordinados.</span><span class="sxs-lookup"><span data-stu-id="c52bf-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="c52bf-120">**Item Ancestrales** - a lista de itens, começando do item mais alto, que é o item padrão do usuário, levando a um determinado Item.</span><span class="sxs-lookup"><span data-stu-id="c52bf-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="c52bf-121">**Conteúdo do Item** - o conteúdo específico do aplicativo armazenado em Itens.</span><span class="sxs-lookup"><span data-stu-id="c52bf-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="c52bf-122">O Painel de Qualidade da Chamada salva representações JSON de Relatórios e Consultas no Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c52bf-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="c52bf-123">As operações REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c52bf-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="c52bf-124">**Operação**</span><span class="sxs-lookup"><span data-stu-id="c52bf-124">**Operation**</span></span>|<span data-ttu-id="c52bf-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c52bf-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c52bf-126">Obter itens</span><span class="sxs-lookup"><span data-stu-id="c52bf-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="c52bf-127">Obter itens retorna todos os itens no repositório.</span><span class="sxs-lookup"><span data-stu-id="c52bf-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="c52bf-128">Obter item</span><span class="sxs-lookup"><span data-stu-id="c52bf-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="c52bf-129">Get Item retorna um Item específico.</span><span class="sxs-lookup"><span data-stu-id="c52bf-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="c52bf-130">Obter subitens</span><span class="sxs-lookup"><span data-stu-id="c52bf-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="c52bf-131">Get Sub-Items retorna sub-itens de um item específico.</span><span class="sxs-lookup"><span data-stu-id="c52bf-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="c52bf-132">Obter o Item Predecessor</span><span class="sxs-lookup"><span data-stu-id="c52bf-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="c52bf-133">Get Item Ancestors retorna ancestrais de um item específico.</span><span class="sxs-lookup"><span data-stu-id="c52bf-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="c52bf-134">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="c52bf-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="c52bf-135">Atualize um item específico no repositório.</span><span class="sxs-lookup"><span data-stu-id="c52bf-135">Update a specific item in the repository.</span></span>  <br/> |
   

