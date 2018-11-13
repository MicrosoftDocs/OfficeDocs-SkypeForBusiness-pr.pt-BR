---
title: Obtenha os membros de dimensão
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumo: Saiba mais sobre a operação obter membros da dimensão. A operação obter membros da dimensão é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 6d3f5f30ccb3b79aabe9faa37f7c960b846ef0cd
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295959"
---
# <a name="get-dimension-members"></a><span data-ttu-id="15181-105">Obtenha os membros de dimensão</span><span class="sxs-lookup"><span data-stu-id="15181-105">Get Dimension Members</span></span>
 
<span data-ttu-id="15181-106">**Resumo:** Saiba mais sobre a operação obter membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="15181-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="15181-107">A operação obter membros da dimensão é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="15181-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="15181-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="15181-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="15181-109">A operação obter membros da dimensão é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="15181-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="15181-110">Obtenha os membros de dimensão</span><span class="sxs-lookup"><span data-stu-id="15181-110">Get Dimension Members</span></span>

<span data-ttu-id="15181-111">Operação de membros da dimensão Get retorna a lista de membros de uma dimensão específica.</span><span class="sxs-lookup"><span data-stu-id="15181-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="15181-112">Ele também dá a capacidade de filtrar a lista de membro e obtenha um subconjunto, para reduzir o custo de transferência de transmissão.</span><span class="sxs-lookup"><span data-stu-id="15181-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="15181-113">**Método**</span><span class="sxs-lookup"><span data-stu-id="15181-113">**Method**</span></span>|<span data-ttu-id="15181-114">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="15181-114">**Request URI**</span></span>|<span data-ttu-id="15181-115">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="15181-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15181-116">Postar</span><span class="sxs-lookup"><span data-stu-id="15181-116">POST</span></span>  <br/> |<span data-ttu-id="15181-117">https://\<portal\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="15181-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="15181-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="15181-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="15181-119">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="15181-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="15181-120">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="15181-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15181-121">**Corpo da solicitação** - contém o nome da dimensão que queremos que os membros de.</span><span class="sxs-lookup"><span data-stu-id="15181-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="15181-122">Também número máximo de membros retornados, ao lado do você pode especificar algumas filtragem para limitar os membros retornados.</span><span class="sxs-lookup"><span data-stu-id="15181-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="15181-123">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="15181-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="15181-124">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="15181-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="15181-125">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="15181-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15181-126">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON em resposta a uma solicitação para "[StartDate]. [Mês] "dimensão.</span><span class="sxs-lookup"><span data-stu-id="15181-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15181-127">A lista está mostrando apenas uma pequena parte da lista.</span><span class="sxs-lookup"><span data-stu-id="15181-127">The list is only showing a small portion of the list.</span></span> 
  
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