---
title: Tabela ContentTypes no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816081"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4e126-104">Tabela ContentTypes no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4e126-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4e126-105">A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e sessões de conferência.</span><span class="sxs-lookup"><span data-stu-id="4e126-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="4e126-106">Cada registro na tabela representa um tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4e126-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="4e126-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4e126-107">**Column**</span></span>|<span data-ttu-id="4e126-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4e126-108">**Data Type**</span></span>|<span data-ttu-id="4e126-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="4e126-109">**Key/Index**</span></span>|<span data-ttu-id="4e126-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4e126-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e126-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="4e126-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="4e126-112">int</span><span class="sxs-lookup"><span data-stu-id="4e126-112">int</span></span>  <br/> |<span data-ttu-id="4e126-113">Primário</span><span class="sxs-lookup"><span data-stu-id="4e126-113">Primary</span></span>  <br/> |<span data-ttu-id="4e126-114">Número exclusivo que identifica o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4e126-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="4e126-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="4e126-115">**ContentType**</span></span> <br/> |<span data-ttu-id="4e126-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4e126-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="4e126-117">Nome do tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4e126-117">Content type name.</span></span>  <br/> |
   

