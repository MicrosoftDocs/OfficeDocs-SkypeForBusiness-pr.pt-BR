---
title: Exibição FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: A exibição FileTransfer armazena informações sobre sessões de transferência de arquivos ponto a ponto. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821681"
---
# <a name="filetransfers-view"></a><span data-ttu-id="a1a36-104">Exibição FileTransfers</span><span class="sxs-lookup"><span data-stu-id="a1a36-104">FileTransfers view</span></span>
 
<span data-ttu-id="a1a36-105">A exibição FileTransfer armazena informações sobre sessões de transferência de arquivos ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="a1a36-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="a1a36-106">Essa exibição foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1a36-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1a36-107">O exibição FileTransfers contém todas as colunas no [exibição SessionDetails,](sessiondetails-0.md) além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="a1a36-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="a1a36-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a1a36-108">**Column**</span></span>|<span data-ttu-id="a1a36-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a1a36-109">**Data Type**</span></span>|<span data-ttu-id="a1a36-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a1a36-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a1a36-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="a1a36-111">**FileName**</span></span> <br/> |<span data-ttu-id="a1a36-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a1a36-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a1a36-113">Nome do arquivo transferido.</span><span class="sxs-lookup"><span data-stu-id="a1a36-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="a1a36-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="a1a36-114">**Cookie**</span></span> <br/> |<span data-ttu-id="a1a36-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="a1a36-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="a1a36-116">Usado para identificar cada mensagem de acompanhamento como sendo associado a este.</span><span class="sxs-lookup"><span data-stu-id="a1a36-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="a1a36-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="a1a36-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="a1a36-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a1a36-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="a1a36-119">Identificador exclusivo para distinguir entre as transferências de arquivo envolvendo o mesmo nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="a1a36-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="a1a36-120">**Accept**</span><span class="sxs-lookup"><span data-stu-id="a1a36-120">**Accept**</span></span> <br/> |<span data-ttu-id="a1a36-121">bit</span><span class="sxs-lookup"><span data-stu-id="a1a36-121">bit</span></span>  <br/> |<span data-ttu-id="a1a36-p103">Pode ser TRUE ou NULL. Se for TRUE, Rejeitar e Cancelar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="a1a36-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="a1a36-124">**Reject**</span><span class="sxs-lookup"><span data-stu-id="a1a36-124">**Reject**</span></span> <br/> |<span data-ttu-id="a1a36-125">bit</span><span class="sxs-lookup"><span data-stu-id="a1a36-125">bit</span></span>  <br/> |<span data-ttu-id="a1a36-p104">Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Cancelar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="a1a36-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="a1a36-128">**Cancel**</span><span class="sxs-lookup"><span data-stu-id="a1a36-128">**Cancel**</span></span> <br/> |<span data-ttu-id="a1a36-129">bit</span><span class="sxs-lookup"><span data-stu-id="a1a36-129">bit</span></span>  <br/> |<span data-ttu-id="a1a36-p105">Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Rejeitar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="a1a36-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

