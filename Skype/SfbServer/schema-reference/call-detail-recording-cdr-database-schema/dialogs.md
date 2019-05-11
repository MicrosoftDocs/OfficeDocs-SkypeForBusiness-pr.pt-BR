---
title: Tabela de diálogos no Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.
ms.openlocfilehash: 379956a2c77c60a53e702913d81b25b41dc2fc23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901126"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="77851-103">Tabela de diálogos no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="77851-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="77851-104">A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="77851-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="77851-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="77851-105">**Column**</span></span>|<span data-ttu-id="77851-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="77851-106">**Data Type**</span></span>|<span data-ttu-id="77851-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="77851-107">**Key/Index**</span></span>|<span data-ttu-id="77851-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="77851-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="77851-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="77851-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="77851-110">datetime</span><span class="sxs-lookup"><span data-stu-id="77851-110">datetime</span></span>  <br/> |<span data-ttu-id="77851-111">Primária</span><span class="sxs-lookup"><span data-stu-id="77851-111">Primary</span></span>  <br/> |<span data-ttu-id="77851-112">Hora da solicitação de sessão; usado em conjunto com SessionIDSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="77851-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="77851-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="77851-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="77851-114">int</span><span class="sxs-lookup"><span data-stu-id="77851-114">int</span></span>  <br/> |<span data-ttu-id="77851-115">Primária</span><span class="sxs-lookup"><span data-stu-id="77851-115">Primary</span></span>  <br/> |<span data-ttu-id="77851-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="77851-116">ID number to identify the session.</span></span> <span data-ttu-id="77851-117">Usado em conjunto com SessionIDTime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="77851-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="77851-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="77851-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="77851-119">int</span><span class="sxs-lookup"><span data-stu-id="77851-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="77851-120">Soma de verificação de ExternalID.</span><span class="sxs-lookup"><span data-stu-id="77851-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="77851-121">Este campo é usado para aumentar a velocidade de pesquisas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="77851-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="77851-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="77851-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="77851-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="77851-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="77851-124">ID de diálogo SIP, armazenado como um binário.</span><span class="sxs-lookup"><span data-stu-id="77851-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="77851-125">O formato do binário é:</span><span class="sxs-lookup"><span data-stu-id="77851-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="77851-126">diálogo; da marca; a marca</span><span class="sxs-lookup"><span data-stu-id="77851-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="77851-127">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="77851-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

