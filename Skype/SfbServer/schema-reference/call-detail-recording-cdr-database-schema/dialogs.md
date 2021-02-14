---
title: Tabela Dialogs in Skype for Business Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: A tabela Dialogs é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816041"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6c81f-103">Tabela Dialogs in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6c81f-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6c81f-104">A tabela Dialogs é uma tabela de suporte que armazena as informações sobre DialogIDs para sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="6c81f-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="6c81f-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6c81f-105">**Column**</span></span>|<span data-ttu-id="6c81f-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="6c81f-106">**Data Type**</span></span>|<span data-ttu-id="6c81f-107">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="6c81f-107">**Key/Index**</span></span>|<span data-ttu-id="6c81f-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="6c81f-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6c81f-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="6c81f-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="6c81f-110">datetime</span><span class="sxs-lookup"><span data-stu-id="6c81f-110">datetime</span></span>  <br/> |<span data-ttu-id="6c81f-111">Primário</span><span class="sxs-lookup"><span data-stu-id="6c81f-111">Primary</span></span>  <br/> |<span data-ttu-id="6c81f-112">Hora da solicitação de sessão; usado em conjunto com SessionIDSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6c81f-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="6c81f-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="6c81f-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="6c81f-114">int</span><span class="sxs-lookup"><span data-stu-id="6c81f-114">int</span></span>  <br/> |<span data-ttu-id="6c81f-115">Primário</span><span class="sxs-lookup"><span data-stu-id="6c81f-115">Primary</span></span>  <br/> |<span data-ttu-id="6c81f-116">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="6c81f-116">ID number to identify the session.</span></span> <span data-ttu-id="6c81f-117">Usado em conjunto com SessionIDTime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6c81f-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="6c81f-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="6c81f-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="6c81f-119">int</span><span class="sxs-lookup"><span data-stu-id="6c81f-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="6c81f-120">Checksum of the ExternalID.</span><span class="sxs-lookup"><span data-stu-id="6c81f-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="6c81f-121">Esse campo é usado para aumentar a velocidade de pesquisas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6c81f-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="6c81f-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="6c81f-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="6c81f-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="6c81f-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="6c81f-124">ID da caixa de diálogo SIP, armazenada como um binário.</span><span class="sxs-lookup"><span data-stu-id="6c81f-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="6c81f-125">O formato do binário é:</span><span class="sxs-lookup"><span data-stu-id="6c81f-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="6c81f-126">dialog;from-tag;to-tag</span><span class="sxs-lookup"><span data-stu-id="6c81f-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="6c81f-127">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="6c81f-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

