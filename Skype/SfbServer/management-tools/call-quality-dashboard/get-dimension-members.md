---
title: Obtenha os Membros da Dimensão
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumo: Saiba mais sobre a operação obter membros da dimensão. A operação obter membros da dimensão faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: c457e7f3b42aaeb11c35180bc4c1ae6ee42b914e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274748"
---
# <a name="get-dimension-members"></a><span data-ttu-id="15843-105">Obtenha os Membros da Dimensão</span><span class="sxs-lookup"><span data-stu-id="15843-105">Get Dimension Members</span></span>
 
<span data-ttu-id="15843-106">**Resumo:** Saiba mais sobre a operação obter membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="15843-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="15843-107">A operação obter membros da dimensão faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="15843-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="15843-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="15843-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="15843-109">A operação obter membros da dimensão faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="15843-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="15843-110">Obtenha os Membros da Dimensão</span><span class="sxs-lookup"><span data-stu-id="15843-110">Get Dimension Members</span></span>

<span data-ttu-id="15843-111">A operação obter membros da dimensão retorna a lista de membros de uma dimensão específica.</span><span class="sxs-lookup"><span data-stu-id="15843-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="15843-112">Ele também permite filtrar a lista de membros e obter um subconjunto para reduzir o custo de transferência de fio.</span><span class="sxs-lookup"><span data-stu-id="15843-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="15843-113">**Forma**</span><span class="sxs-lookup"><span data-stu-id="15843-113">**Method**</span></span>|<span data-ttu-id="15843-114">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="15843-114">**Request URI**</span></span>|<span data-ttu-id="15843-115">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="15843-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15843-116">Postar</span><span class="sxs-lookup"><span data-stu-id="15843-116">POST</span></span>  <br/> |<span data-ttu-id="15843-117">https://\<do\>portal de/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="15843-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="15843-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="15843-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="15843-119">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="15843-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="15843-120">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="15843-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15843-121">**Corpo da solicitação** -contém o nome da dimensão para a qual queremos os membros.</span><span class="sxs-lookup"><span data-stu-id="15843-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="15843-122">Também número máximo de membros retornados, ao lado de você pode especificar alguns filtros para limitar os membros retornados.</span><span class="sxs-lookup"><span data-stu-id="15843-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="15843-123">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="15843-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="15843-124">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="15843-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="15843-125">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="15843-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15843-126">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON em resposta a uma solicitação de "[StartDate]. [Mês] "dimensão.</span><span class="sxs-lookup"><span data-stu-id="15843-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15843-127">A lista está mostrando apenas uma pequena parte da lista.</span><span class="sxs-lookup"><span data-stu-id="15843-127">The list is only showing a small portion of the list.</span></span> 
  
```
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
