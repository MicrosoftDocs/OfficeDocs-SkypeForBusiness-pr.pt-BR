---
title: Serviço de item para o painel de controle de qualidade de chamada (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumo: Saiba mais sobre o serviço de Item, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 5e5198afd95d6c9e1de517054053b724a54b1105
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532595"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="501da-104">Serviço de item para o painel de controle de qualidade de chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="501da-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="501da-105">**Resumo:** Saiba mais sobre o serviço de Item, que é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="501da-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="501da-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="501da-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="501da-107">O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="501da-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="501da-108">Serviço de item</span><span class="sxs-lookup"><span data-stu-id="501da-108">Item Service</span></span>

<span data-ttu-id="501da-109">API do repositório oferece um serviço de gerenciamento de conteúdo simples, conhecido como serviço de item, que pode ser usado para armazenar qualquer conteúdo definido pelo aplicativo para usuários.</span><span class="sxs-lookup"><span data-stu-id="501da-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="501da-110">O conteúdo do sistema é pertencentes ao usuário do sistema e compartilhado por todos os usuários com acesso somente leitura.</span><span class="sxs-lookup"><span data-stu-id="501da-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="501da-111">Conteúdo de usuário dedicada pertencentes a usuários regulares e somente os proprietários podem modificar ou excluí-los, mas todos os usuários ainda têm acesso somente leitura a eles.</span><span class="sxs-lookup"><span data-stu-id="501da-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="501da-112">Esta documentação de API abrange operações somente leitura da API do repositório.</span><span class="sxs-lookup"><span data-stu-id="501da-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="501da-113">Painel de controle de qualidade de chamada salva relatórios e consultas como itens do banco de dados do repositório.</span><span class="sxs-lookup"><span data-stu-id="501da-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="501da-114">Um Item pode ter itens sub-recurso opcionais e painel de controle de qualidade de chamada organiza relatórios e consultas em uma estrutura hierárquica usando o recurso de subitens.</span><span class="sxs-lookup"><span data-stu-id="501da-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="501da-115">O serviço de item inclui os seguintes conceitos:</span><span class="sxs-lookup"><span data-stu-id="501da-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="501da-116">**Item** - o elemento básico de repositório.</span><span class="sxs-lookup"><span data-stu-id="501da-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="501da-117">Cada Item pertence ao usuário exatamente uma.</span><span class="sxs-lookup"><span data-stu-id="501da-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="501da-118">**Item de suba** mecânica organizacional básica do repositório.</span><span class="sxs-lookup"><span data-stu-id="501da-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="501da-119">O item pode ter zero, um ou mais itens de subordinados.</span><span class="sxs-lookup"><span data-stu-id="501da-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="501da-120">**Item ancestrais** - a lista de itens, o Item superior, que é o padrão de Item do usuário, levando a um determinado Item tem início.</span><span class="sxs-lookup"><span data-stu-id="501da-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="501da-121">**Item de conteúdo** - o conteúdo de aplicativo específico armazenado em itens.</span><span class="sxs-lookup"><span data-stu-id="501da-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="501da-122">Painel de controle de qualidade de chamada salva as representações de JSON de relatórios e consultas no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="501da-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="501da-123">As operações do REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="501da-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="501da-124">**Operação**</span><span class="sxs-lookup"><span data-stu-id="501da-124">**Operation**</span></span>|<span data-ttu-id="501da-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="501da-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="501da-126">Obter itens</span><span class="sxs-lookup"><span data-stu-id="501da-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="501da-127">Obter itens retorna todos os itens no repositório.</span><span class="sxs-lookup"><span data-stu-id="501da-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="501da-128">Obtenha Item</span><span class="sxs-lookup"><span data-stu-id="501da-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="501da-129">Obtenha o Item Retorna um Item específico.</span><span class="sxs-lookup"><span data-stu-id="501da-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="501da-130">Obter itens sub-recurso</span><span class="sxs-lookup"><span data-stu-id="501da-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="501da-131">Obter itens sub-recurso retorna subitens de um Item específico.</span><span class="sxs-lookup"><span data-stu-id="501da-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="501da-132">Obter ancestrais do Item</span><span class="sxs-lookup"><span data-stu-id="501da-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="501da-133">Get Item ancestrais retorna ancestrais de um Item específico.</span><span class="sxs-lookup"><span data-stu-id="501da-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="501da-134">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="501da-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="501da-135">Atualize um item específico no repositório.</span><span class="sxs-lookup"><span data-stu-id="501da-135">Update a specific item in the repository.</span></span>  <br/> |
   

