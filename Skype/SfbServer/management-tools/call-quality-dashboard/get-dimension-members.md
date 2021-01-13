---
title: Obter os Membros da Dimensão
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumo: saiba mais sobre a operação Obter Membros da Dimensão. A operação Obter Membros da Dimensão faz parte da API de Dados do Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832631"
---
# <a name="get-dimension-members"></a><span data-ttu-id="806b5-105">Obter os Membros da Dimensão</span><span class="sxs-lookup"><span data-stu-id="806b5-105">Get Dimension Members</span></span>
 
<span data-ttu-id="806b5-106">**Resumo:** Saiba mais sobre a operação Obter Membros da Dimensão.</span><span class="sxs-lookup"><span data-stu-id="806b5-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="806b5-107">A operação Obter Membros da Dimensão faz parte da API de Dados do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="806b5-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="806b5-108">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="806b5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="806b5-109">A operação Obter Membros da Dimensão faz parte da API de Dados do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="806b5-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="806b5-110">Obter os Membros da Dimensão</span><span class="sxs-lookup"><span data-stu-id="806b5-110">Get Dimension Members</span></span>

<span data-ttu-id="806b5-111">A operação Obter Membros da Dimensão retorna a lista de membros de uma dimensão específica.</span><span class="sxs-lookup"><span data-stu-id="806b5-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="806b5-112">Ele também dá a capacidade de filtrar a lista de membros e obter um subconjunto, para reduzir o custo de transferência eletrônica.</span><span class="sxs-lookup"><span data-stu-id="806b5-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="806b5-113">**Method**</span><span class="sxs-lookup"><span data-stu-id="806b5-113">**Method**</span></span>|<span data-ttu-id="806b5-114">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="806b5-114">**Request URI**</span></span>|<span data-ttu-id="806b5-115">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="806b5-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="806b5-116">POSTAR</span><span class="sxs-lookup"><span data-stu-id="806b5-116">POST</span></span>  <br/> |<span data-ttu-id="806b5-117">https:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="806b5-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="806b5-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="806b5-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="806b5-119">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="806b5-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="806b5-120">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="806b5-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="806b5-121">**Corpo da** Solicitação - Contém o nome da dimensão para a que queremos os membros.</span><span class="sxs-lookup"><span data-stu-id="806b5-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="806b5-122">Além disso, o número máximo de membros retornados, ao lado de você pode especificar algumas filtragem para limitar os membros retornados.</span><span class="sxs-lookup"><span data-stu-id="806b5-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="806b5-123">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="806b5-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="806b5-124">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="806b5-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="806b5-125">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="806b5-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="806b5-126">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON em resposta a uma solicitação de "[StartDate]. [Month]".</span><span class="sxs-lookup"><span data-stu-id="806b5-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="806b5-127">A lista está mostrando apenas uma pequena parte da lista.</span><span class="sxs-lookup"><span data-stu-id="806b5-127">The list is only showing a small portion of the list.</span></span> 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
