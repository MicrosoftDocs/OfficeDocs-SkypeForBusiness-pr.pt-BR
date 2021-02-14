---
title: Tabela ClientVersions no Skype for Business Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e as versões que participaram de sessões gravadas no banco de dados. Cada registro da tabela representa uma versão de cliente.
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813311"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9b752-104">Tabela ClientVersions no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9b752-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9b752-p102">ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e as versões que participaram de sessões gravadas no banco de dados. Cada registro da tabela representa uma versão de cliente.</span><span class="sxs-lookup"><span data-stu-id="9b752-p102">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="9b752-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9b752-107">**Column**</span></span>|<span data-ttu-id="9b752-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9b752-108">**Data Type**</span></span>|<span data-ttu-id="9b752-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="9b752-109">**Key/Index**</span></span>|<span data-ttu-id="9b752-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="9b752-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9b752-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="9b752-111">**VersionId**</span></span> <br/> |<span data-ttu-id="9b752-112">**int**</span><span class="sxs-lookup"><span data-stu-id="9b752-112">**int**</span></span> <br/> |<span data-ttu-id="9b752-113">Primário</span><span class="sxs-lookup"><span data-stu-id="9b752-113">Primary</span></span>  <br/> |<span data-ttu-id="9b752-114">Número exclusivo que identifica esse tipo de cliente e a versão.</span><span class="sxs-lookup"><span data-stu-id="9b752-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="9b752-115">**Versão**</span><span class="sxs-lookup"><span data-stu-id="9b752-115">**Version**</span></span> <br/> |<span data-ttu-id="9b752-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="9b752-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="9b752-117">Nome da versão.</span><span class="sxs-lookup"><span data-stu-id="9b752-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="9b752-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="9b752-118">**ClientType**</span></span> <br/> |<span data-ttu-id="9b752-119">int</span><span class="sxs-lookup"><span data-stu-id="9b752-119">int</span></span>  <br/> ||<span data-ttu-id="9b752-120">Especifique o tipo de cliente utilizado na sessão.</span><span class="sxs-lookup"><span data-stu-id="9b752-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="9b752-121">Consulte a [tabela UserAgentDef para](useragentdef.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9b752-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="9b752-122">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b752-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

