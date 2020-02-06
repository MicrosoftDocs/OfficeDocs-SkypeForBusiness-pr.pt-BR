---
title: Tabela ClientVersions no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: A tabela ClientVersions é uma tabela de suporte que armazena uma lista de vários tipos de cliente e versões que participaram de sessões registradas no banco de dados. Cada registro na tabela representa uma versão do cliente.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815399"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4d8ca-104">Tabela ClientVersions no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4d8ca-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4d8ca-105">A tabela ClientVersions é uma tabela de suporte que armazena uma lista de vários tipos de cliente e versões que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="4d8ca-106">Cada registro na tabela representa uma versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="4d8ca-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4d8ca-107">**Column**</span></span>|<span data-ttu-id="4d8ca-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4d8ca-108">**Data Type**</span></span>|<span data-ttu-id="4d8ca-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="4d8ca-109">**Key/Index**</span></span>|<span data-ttu-id="4d8ca-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4d8ca-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d8ca-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="4d8ca-111">**VersionId**</span></span> <br/> |<span data-ttu-id="4d8ca-112">**int**</span><span class="sxs-lookup"><span data-stu-id="4d8ca-112">**int**</span></span> <br/> |<span data-ttu-id="4d8ca-113">Primária</span><span class="sxs-lookup"><span data-stu-id="4d8ca-113">Primary</span></span>  <br/> |<span data-ttu-id="4d8ca-114">Número exclusivo que identifica esse tipo de cliente e a versão.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="4d8ca-115">**Versão**</span><span class="sxs-lookup"><span data-stu-id="4d8ca-115">**Version**</span></span> <br/> |<span data-ttu-id="4d8ca-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="4d8ca-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="4d8ca-117">Nome da versão.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="4d8ca-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="4d8ca-118">**ClientType**</span></span> <br/> |<span data-ttu-id="4d8ca-119">int</span><span class="sxs-lookup"><span data-stu-id="4d8ca-119">int</span></span>  <br/> ||<span data-ttu-id="4d8ca-120">Especifica o tipo de cliente usado na sessão.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="4d8ca-121">Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="4d8ca-122">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d8ca-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

