---
title: Tabela ClientVersions Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: A tabela ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e de versões que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa uma versão de cliente.
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213379"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="52756-104">Tabela ClientVersions Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="52756-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="52756-105">A tabela ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e de versões que tenham participado em sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="52756-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="52756-106">Cada registro na tabela representa uma versão de cliente.</span><span class="sxs-lookup"><span data-stu-id="52756-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="52756-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="52756-107">**Column**</span></span>|<span data-ttu-id="52756-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="52756-108">**Data Type**</span></span>|<span data-ttu-id="52756-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="52756-109">**Key/Index**</span></span>|<span data-ttu-id="52756-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="52756-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="52756-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="52756-111">**VersionId**</span></span> <br/> |<span data-ttu-id="52756-112">**int**</span><span class="sxs-lookup"><span data-stu-id="52756-112">**int**</span></span> <br/> |<span data-ttu-id="52756-113">Primária</span><span class="sxs-lookup"><span data-stu-id="52756-113">Primary</span></span>  <br/> |<span data-ttu-id="52756-114">Número exclusivo identificando este tipo de cliente e versão.</span><span class="sxs-lookup"><span data-stu-id="52756-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="52756-115">**Versão**</span><span class="sxs-lookup"><span data-stu-id="52756-115">**Version**</span></span> <br/> |<span data-ttu-id="52756-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="52756-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="52756-117">Nome da versão.</span><span class="sxs-lookup"><span data-stu-id="52756-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="52756-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="52756-118">**ClientType**</span></span> <br/> |<span data-ttu-id="52756-119">int</span><span class="sxs-lookup"><span data-stu-id="52756-119">int</span></span>  <br/> ||<span data-ttu-id="52756-120">Especifica o tipo do cliente usado na sessão.</span><span class="sxs-lookup"><span data-stu-id="52756-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="52756-121">Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="52756-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="52756-122">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52756-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

