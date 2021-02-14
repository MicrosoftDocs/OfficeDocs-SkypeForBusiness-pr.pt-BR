---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: O Set-CcApplianceDirectory cmdlet define o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.
ms.openlocfilehash: a410d20c41fbb0bfef88449aaac96be727218add
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824217"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="429df-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="429df-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="429df-105">O Set-CcApplianceDirectory cmdlet define o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="429df-105">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="429df-106">Todos os arquivos de implantação são armazenados nesse diretório.</span><span class="sxs-lookup"><span data-stu-id="429df-106">All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="429df-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="429df-107">Examples</span></span>
<span data-ttu-id="429df-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="429df-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="429df-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="429df-109">Example 1</span></span>

<span data-ttu-id="429df-110">O exemplo a seguir define o diretório de trabalho no servidor host como c:\cloudconnector\applianceroot:</span><span class="sxs-lookup"><span data-stu-id="429df-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="429df-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="429df-111">Parameters</span></span>
<span data-ttu-id="429df-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="429df-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="429df-113">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="429df-113">**Parameter**</span></span>|<span data-ttu-id="429df-114">**Required**</span><span class="sxs-lookup"><span data-stu-id="429df-114">**Required**</span></span>|<span data-ttu-id="429df-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="429df-115">**Type**</span></span>|<span data-ttu-id="429df-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="429df-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="429df-117">Path</span><span class="sxs-lookup"><span data-stu-id="429df-117">Path</span></span> <br/> | <span data-ttu-id="429df-118">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="429df-118">Required</span></span> <br/> |<span data-ttu-id="429df-119">System.String</span><span class="sxs-lookup"><span data-stu-id="429df-119">System.String</span></span>  <br/> | <span data-ttu-id="429df-120">Especifica o caminho onde todos os arquivos de implantação são armazenados.</span><span class="sxs-lookup"><span data-stu-id="429df-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="429df-121">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="429df-121">Input Types</span></span>
<span data-ttu-id="429df-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="429df-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="429df-123">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="429df-123">None.</span></span> <span data-ttu-id="429df-124">O Set-CcApplianceDirectory cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="429df-124">The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="429df-125">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="429df-125">Return Types</span></span>
<span data-ttu-id="429df-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="429df-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="429df-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="429df-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="429df-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="429df-128">See also</span></span>
<span data-ttu-id="429df-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="429df-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="429df-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="429df-130">None</span></span>
  

