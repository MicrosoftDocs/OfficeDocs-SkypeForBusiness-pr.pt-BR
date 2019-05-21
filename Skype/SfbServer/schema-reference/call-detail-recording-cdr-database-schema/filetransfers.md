---
title: Modo de exibição de transferência de fileviews
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: O modo de transferência de arquivo armazena informações sobre sessões de transferência de arquivos ponto a ponto. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296235"
---
# <a name="filetransfers-view"></a><span data-ttu-id="266f1-104">Modo de exibição de transferência de fileviews</span><span class="sxs-lookup"><span data-stu-id="266f1-104">FileTransfers view</span></span>
 
<span data-ttu-id="266f1-105">O modo de transferência de arquivo armazena informações sobre sessões de transferência de arquivos ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="266f1-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="266f1-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="266f1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="266f1-107">O modo de exibição filetransfers contém todas as colunas na [exibição SessionDetails](sessiondetails-0.md) , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="266f1-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="266f1-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="266f1-108">**Column**</span></span>|<span data-ttu-id="266f1-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="266f1-109">**Data Type**</span></span>|<span data-ttu-id="266f1-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="266f1-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="266f1-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="266f1-111">**FileName**</span></span> <br/> |<span data-ttu-id="266f1-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="266f1-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="266f1-113">Nome do arquivo transferido.</span><span class="sxs-lookup"><span data-stu-id="266f1-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="266f1-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="266f1-114">**Cookie**</span></span> <br/> |<span data-ttu-id="266f1-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="266f1-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="266f1-116">Usado para identificar todas as mensagens de acompanhamento como associadas a esta.</span><span class="sxs-lookup"><span data-stu-id="266f1-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="266f1-117">**Fileidentity**</span><span class="sxs-lookup"><span data-stu-id="266f1-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="266f1-118">identificador</span><span class="sxs-lookup"><span data-stu-id="266f1-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="266f1-119">Identificador exclusivo para distinguir entre as transferências de arquivo que envolvem o mesmo nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="266f1-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="266f1-120">**Aceite**</span><span class="sxs-lookup"><span data-stu-id="266f1-120">**Accept**</span></span> <br/> |<span data-ttu-id="266f1-121">bit</span><span class="sxs-lookup"><span data-stu-id="266f1-121">bit</span></span>  <br/> |<span data-ttu-id="266f1-122">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="266f1-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="266f1-123">Se verdadeiro, rejeitar e cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="266f1-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="266f1-124">**Rejeitar**</span><span class="sxs-lookup"><span data-stu-id="266f1-124">**Reject**</span></span> <br/> |<span data-ttu-id="266f1-125">bit</span><span class="sxs-lookup"><span data-stu-id="266f1-125">bit</span></span>  <br/> |<span data-ttu-id="266f1-126">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="266f1-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="266f1-127">Se verdadeiro, aceitar e cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="266f1-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="266f1-128">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="266f1-128">**Cancel**</span></span> <br/> |<span data-ttu-id="266f1-129">bit</span><span class="sxs-lookup"><span data-stu-id="266f1-129">bit</span></span>  <br/> |<span data-ttu-id="266f1-130">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="266f1-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="266f1-131">Se verdadeiro, aceitar e rejeitar será nulo.</span><span class="sxs-lookup"><span data-stu-id="266f1-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

