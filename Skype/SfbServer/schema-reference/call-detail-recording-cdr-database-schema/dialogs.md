---
title: Tabela de caixas de diálogo no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs em sessões ponto a ponto.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296319"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e8238-103">Tabela de caixas de diálogo no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e8238-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e8238-104">A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre DialogIDs em sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="e8238-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="e8238-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e8238-105">**Column**</span></span>|<span data-ttu-id="e8238-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e8238-106">**Data Type**</span></span>|<span data-ttu-id="e8238-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="e8238-107">**Key/Index**</span></span>|<span data-ttu-id="e8238-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e8238-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8238-109">**Id_da_sessãotime**</span><span class="sxs-lookup"><span data-stu-id="e8238-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="e8238-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e8238-110">datetime</span></span>  <br/> |<span data-ttu-id="e8238-111">Primária</span><span class="sxs-lookup"><span data-stu-id="e8238-111">Primary</span></span>  <br/> |<span data-ttu-id="e8238-112">Tempo de solicitação de sessão; usado em conjunto com o SessionIDSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e8238-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="e8238-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="e8238-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="e8238-114">int</span><span class="sxs-lookup"><span data-stu-id="e8238-114">int</span></span>  <br/> |<span data-ttu-id="e8238-115">Primária</span><span class="sxs-lookup"><span data-stu-id="e8238-115">Primary</span></span>  <br/> |<span data-ttu-id="e8238-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="e8238-116">ID number to identify the session.</span></span> <span data-ttu-id="e8238-117">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e8238-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="e8238-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="e8238-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="e8238-119">int</span><span class="sxs-lookup"><span data-stu-id="e8238-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="e8238-120">Checksum da externalId.</span><span class="sxs-lookup"><span data-stu-id="e8238-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="e8238-121">Este campo é usado para aumentar a velocidade das pesquisas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e8238-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="e8238-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="e8238-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="e8238-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="e8238-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="e8238-124">ID da caixa de diálogo SIP, armazenada como um binário.</span><span class="sxs-lookup"><span data-stu-id="e8238-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="e8238-125">O formato do binário é:</span><span class="sxs-lookup"><span data-stu-id="e8238-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="e8238-126">caixa de diálogo; de-marca; até-marca</span><span class="sxs-lookup"><span data-stu-id="e8238-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="e8238-127">Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e8238-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

