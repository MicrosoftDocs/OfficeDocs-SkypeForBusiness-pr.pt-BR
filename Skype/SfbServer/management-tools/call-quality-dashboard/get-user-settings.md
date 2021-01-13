---
title: Obter Configurações de Usuário
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumo: saiba mais sobre a operação Obter Configurações do Usuário, que faz parte do Serviço de Configurações do Usuário. O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832471"
---
# <a name="get-user-settings"></a><span data-ttu-id="17224-105">Obter Configurações de Usuário</span><span class="sxs-lookup"><span data-stu-id="17224-105">Get User Settings</span></span>
 
<span data-ttu-id="17224-106">**Resumo:** Saiba mais sobre a operação Obter Configurações do Usuário, que faz parte do Serviço de Configurações do Usuário.</span><span class="sxs-lookup"><span data-stu-id="17224-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="17224-107">O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="17224-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="17224-108">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="17224-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="17224-109">A operação Obter Configurações do Usuário faz parte do Serviço de Configurações do Usuário na API de Repositório do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="17224-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="17224-110">Obter Configurações de Usuário</span><span class="sxs-lookup"><span data-stu-id="17224-110">Get User Settings</span></span>

<span data-ttu-id="17224-111">Obter configurações do usuário retorna uma lista de configurações para um usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="17224-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="17224-112">**Method**</span><span class="sxs-lookup"><span data-stu-id="17224-112">**Method**</span></span>|<span data-ttu-id="17224-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="17224-113">**Request URI**</span></span>|<span data-ttu-id="17224-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="17224-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="17224-115">OBTER</span><span class="sxs-lookup"><span data-stu-id="17224-115">GET</span></span>  <br/> |<span data-ttu-id="17224-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="17224-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="17224-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="17224-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="17224-118">**Parâmetros de URI**</span><span class="sxs-lookup"><span data-stu-id="17224-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="17224-119">*efetivo*  - Opcional.</span><span class="sxs-lookup"><span data-stu-id="17224-119">*effective*  - Optional.</span></span> <span data-ttu-id="17224-120">Esse parâmetro só se aplica quando o padrão de ID de usuário especial é usado.</span><span class="sxs-lookup"><span data-stu-id="17224-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="17224-121">Em outros casos, ele será ignorado.</span><span class="sxs-lookup"><span data-stu-id="17224-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="17224-122">`True` retorna configurações efetivas do usuário `false` e retorna apenas as configurações do usuário (padrão).</span><span class="sxs-lookup"><span data-stu-id="17224-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="17224-123">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="17224-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="17224-124">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="17224-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="17224-125">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="17224-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="17224-126">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="17224-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="17224-127">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="17224-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="17224-128">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.</span><span class="sxs-lookup"><span data-stu-id="17224-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
