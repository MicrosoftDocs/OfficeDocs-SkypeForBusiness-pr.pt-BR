---
title: Obter os Usuário
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumo: saiba mais sobre a operação Obter Usuário, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832411"
---
# <a name="get-user"></a><span data-ttu-id="8ae52-105">Obter os Usuário</span><span class="sxs-lookup"><span data-stu-id="8ae52-105">Get User</span></span>
 
<span data-ttu-id="8ae52-106">**Resumo:** Saiba mais sobre a operação Obter Usuário, que faz parte do Serviço de Usuário.</span><span class="sxs-lookup"><span data-stu-id="8ae52-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="8ae52-107">O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="8ae52-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="8ae52-108">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8ae52-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8ae52-109">A operação Obter Usuários faz parte do Serviço de Usuário na API de Repositório para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="8ae52-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="8ae52-110">Obter os Usuário</span><span class="sxs-lookup"><span data-stu-id="8ae52-110">Get User</span></span>

<span data-ttu-id="8ae52-111">Obter Usuário retorna um registro de usuário do repositório.</span><span class="sxs-lookup"><span data-stu-id="8ae52-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="8ae52-112">**Method**</span><span class="sxs-lookup"><span data-stu-id="8ae52-112">**Method**</span></span>|<span data-ttu-id="8ae52-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="8ae52-113">**Request URI**</span></span>|<span data-ttu-id="8ae52-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="8ae52-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ae52-115">OBTER</span><span class="sxs-lookup"><span data-stu-id="8ae52-115">GET</span></span>  <br/> |<span data-ttu-id="8ae52-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="8ae52-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="8ae52-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="8ae52-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8ae52-118">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8ae52-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8ae52-119">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="8ae52-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8ae52-120">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8ae52-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8ae52-121">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="8ae52-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8ae52-122">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="8ae52-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="8ae52-123">Se uma ID de usuário especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).</span><span class="sxs-lookup"><span data-stu-id="8ae52-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="8ae52-124">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="8ae52-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8ae52-125">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.</span><span class="sxs-lookup"><span data-stu-id="8ae52-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="8ae52-126">*userId*  - ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="8ae52-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="8ae52-127">*loginName*  - Identificação de usuário externo para usuários regulares.</span><span class="sxs-lookup"><span data-stu-id="8ae52-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="8ae52-128">Se a Autenticação do Windows for usada para autenticar usuários, esse pode ser um FQDN do usuário.</span><span class="sxs-lookup"><span data-stu-id="8ae52-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="8ae52-129">*defaultItemId*  - ID do Item padrão para este usuário.</span><span class="sxs-lookup"><span data-stu-id="8ae52-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="8ae52-130">O Item padrão é o item mais alto que está associado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="8ae52-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="8ae52-131">Todos os outros itens que este usuário possui podem ser navegados a partir do Item padrão.</span><span class="sxs-lookup"><span data-stu-id="8ae52-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ae52-132">Fornece o  `defaultItemId` valor da operação Obter Item para recuperar os detalhes do Item padrão.</span><span class="sxs-lookup"><span data-stu-id="8ae52-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

