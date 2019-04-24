---
title: Tabela de diálogos no Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.
ms.openlocfilehash: af7816c202f995e826567391bf32c5c32a2d0d94
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213652"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ddba6-103">Tabela de diálogos no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ddba6-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ddba6-104">A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="ddba6-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="ddba6-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ddba6-105">**Column**</span></span>|<span data-ttu-id="ddba6-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ddba6-106">**Data Type**</span></span>|<span data-ttu-id="ddba6-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="ddba6-107">**Key/Index**</span></span>|<span data-ttu-id="ddba6-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="ddba6-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ddba6-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="ddba6-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="ddba6-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ddba6-110">datetime</span></span>  <br/> |<span data-ttu-id="ddba6-111">Primária</span><span class="sxs-lookup"><span data-stu-id="ddba6-111">Primary</span></span>  <br/> |<span data-ttu-id="ddba6-112">Hora da solicitação de sessão; usado em conjunto com SessionIDSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ddba6-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="ddba6-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="ddba6-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="ddba6-114">int</span><span class="sxs-lookup"><span data-stu-id="ddba6-114">int</span></span>  <br/> |<span data-ttu-id="ddba6-115">Primária</span><span class="sxs-lookup"><span data-stu-id="ddba6-115">Primary</span></span>  <br/> |<span data-ttu-id="ddba6-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="ddba6-116">ID number to identify the session.</span></span> <span data-ttu-id="ddba6-117">Usado em conjunto com SessionIDTime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ddba6-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="ddba6-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="ddba6-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="ddba6-119">int</span><span class="sxs-lookup"><span data-stu-id="ddba6-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="ddba6-120">Soma de verificação de ExternalID.</span><span class="sxs-lookup"><span data-stu-id="ddba6-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="ddba6-121">Este campo é usado para aumentar a velocidade de pesquisas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ddba6-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="ddba6-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="ddba6-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="ddba6-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="ddba6-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="ddba6-124">ID de diálogo SIP, armazenado como um binário.</span><span class="sxs-lookup"><span data-stu-id="ddba6-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="ddba6-125">O formato do binário é:</span><span class="sxs-lookup"><span data-stu-id="ddba6-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="ddba6-126">diálogo; da marca; a marca</span><span class="sxs-lookup"><span data-stu-id="ddba6-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="ddba6-127">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="ddba6-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

