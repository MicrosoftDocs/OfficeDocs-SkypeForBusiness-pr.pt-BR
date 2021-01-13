---
title: Tabela Roles
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809971"
---
# <a name="roles-table"></a><span data-ttu-id="7ef32-103">Tabela Roles</span><span class="sxs-lookup"><span data-stu-id="7ef32-103">Roles table</span></span>
 
<span data-ttu-id="7ef32-104">A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.</span><span class="sxs-lookup"><span data-stu-id="7ef32-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="7ef32-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7ef32-105">**Column**</span></span>|<span data-ttu-id="7ef32-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="7ef32-106">**Data Type**</span></span>|<span data-ttu-id="7ef32-107">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="7ef32-107">**Key/Index**</span></span>|<span data-ttu-id="7ef32-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="7ef32-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ef32-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="7ef32-109">**RoleId**</span></span> <br/> |<span data-ttu-id="7ef32-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7ef32-110">tinyint</span></span>  <br/> |<span data-ttu-id="7ef32-111">Primário</span><span class="sxs-lookup"><span data-stu-id="7ef32-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="7ef32-112">**Função**</span><span class="sxs-lookup"><span data-stu-id="7ef32-112">**Role**</span></span> <br/> |<span data-ttu-id="7ef32-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7ef32-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="7ef32-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="7ef32-114">Allowed values:</span></span> <br/>  <span data-ttu-id="7ef32-115">0 - Desconhecido</span><span class="sxs-lookup"><span data-stu-id="7ef32-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="7ef32-116">1 - Apresentador</span><span class="sxs-lookup"><span data-stu-id="7ef32-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="7ef32-117">2 - Participante</span><span class="sxs-lookup"><span data-stu-id="7ef32-117">2 - Attendee</span></span> <br/> |
   

