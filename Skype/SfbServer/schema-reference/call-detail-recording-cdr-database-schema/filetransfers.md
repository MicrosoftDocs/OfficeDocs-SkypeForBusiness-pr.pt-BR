---
title: Exibir FileTransfers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: O modo de exibição FileTransfer armazena informações sobre sessões de transferência de arquivo ponto a ponto. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213085"
---
# <a name="filetransfers-view"></a><span data-ttu-id="c3299-104">Exibir FileTransfers</span><span class="sxs-lookup"><span data-stu-id="c3299-104">FileTransfers view</span></span>
 
<span data-ttu-id="c3299-105">O modo de exibição FileTransfer armazena informações sobre sessões de transferência de arquivo ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="c3299-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="c3299-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3299-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3299-107">O modo de exibição do FileTransfers contém todas as colunas no [SessionDetails view](sessiondetails-0.md) além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="c3299-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="c3299-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c3299-108">**Column**</span></span>|<span data-ttu-id="c3299-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c3299-109">**Data Type**</span></span>|<span data-ttu-id="c3299-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="c3299-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3299-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="c3299-111">**FileName**</span></span> <br/> |<span data-ttu-id="c3299-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c3299-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c3299-113">Nome do arquivo transferido.</span><span class="sxs-lookup"><span data-stu-id="c3299-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="c3299-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="c3299-114">**Cookie**</span></span> <br/> |<span data-ttu-id="c3299-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="c3299-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="c3299-116">Usado para identificar cada mensagem de acompanhamento como sendo associado a este.</span><span class="sxs-lookup"><span data-stu-id="c3299-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="c3299-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="c3299-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="c3299-118">Identificador exclusivo</span><span class="sxs-lookup"><span data-stu-id="c3299-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="c3299-119">Identificador exclusivo para distinguir entre transferências de arquivo envolvendo o mesmo nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c3299-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="c3299-120">**Aceitar**</span><span class="sxs-lookup"><span data-stu-id="c3299-120">**Accept**</span></span> <br/> |<span data-ttu-id="c3299-121">bit</span><span class="sxs-lookup"><span data-stu-id="c3299-121">bit</span></span>  <br/> |<span data-ttu-id="c3299-122">Pode ser TRUE ou nulo.</span><span class="sxs-lookup"><span data-stu-id="c3299-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="c3299-123">Se for TRUE, em seguida, rejeitar e Cancelar será NULL.</span><span class="sxs-lookup"><span data-stu-id="c3299-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="c3299-124">**Rejeitar**</span><span class="sxs-lookup"><span data-stu-id="c3299-124">**Reject**</span></span> <br/> |<span data-ttu-id="c3299-125">bit</span><span class="sxs-lookup"><span data-stu-id="c3299-125">bit</span></span>  <br/> |<span data-ttu-id="c3299-126">Pode ser TRUE ou nulo.</span><span class="sxs-lookup"><span data-stu-id="c3299-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="c3299-127">Se for TRUE, em seguida, aceitar e Cancelar será NULL.</span><span class="sxs-lookup"><span data-stu-id="c3299-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="c3299-128">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="c3299-128">**Cancel**</span></span> <br/> |<span data-ttu-id="c3299-129">bit</span><span class="sxs-lookup"><span data-stu-id="c3299-129">bit</span></span>  <br/> |<span data-ttu-id="c3299-130">Pode ser TRUE ou nulo.</span><span class="sxs-lookup"><span data-stu-id="c3299-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="c3299-131">Se for TRUE, em seguida, aceitar e rejeitar será NULL.</span><span class="sxs-lookup"><span data-stu-id="c3299-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

