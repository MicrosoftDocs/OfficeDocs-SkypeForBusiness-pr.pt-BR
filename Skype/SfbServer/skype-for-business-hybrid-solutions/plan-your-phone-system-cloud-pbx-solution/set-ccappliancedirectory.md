---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: O cmdlet Set-CcApplianceDirectory define o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.
ms.openlocfilehash: 16c9c858d770b7d4a74c9030ebdc760f5a9f25e9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888179"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="53cea-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="53cea-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="53cea-p102">O cmdlet Set-CcApplianceDirectory define o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.</span><span class="sxs-lookup"><span data-stu-id="53cea-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="53cea-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="53cea-107">Examples</span></span>
<span data-ttu-id="53cea-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="53cea-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="53cea-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="53cea-109">Example 1</span></span>

<span data-ttu-id="53cea-110">O exemplo a seguir define o diretório de trabalho no servidor host como c:\cloudconnector\applianceroot:</span><span class="sxs-lookup"><span data-stu-id="53cea-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="53cea-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="53cea-111">Parameters</span></span>
<span data-ttu-id="53cea-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="53cea-112"></span></span>

|<span data-ttu-id="53cea-113">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="53cea-113">**Parameter**</span></span>|<span data-ttu-id="53cea-114">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="53cea-114">**Required**</span></span>|<span data-ttu-id="53cea-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="53cea-115">**Type**</span></span>|<span data-ttu-id="53cea-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="53cea-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="53cea-117">Path</span><span class="sxs-lookup"><span data-stu-id="53cea-117">Path</span></span> <br/> | <span data-ttu-id="53cea-118">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="53cea-118">Required</span></span> <br/> |<span data-ttu-id="53cea-119">System.String</span><span class="sxs-lookup"><span data-stu-id="53cea-119">System.String</span></span>  <br/> | <span data-ttu-id="53cea-120">Especifica o caminho onde todos os arquivos da implantação são armazenados.</span><span class="sxs-lookup"><span data-stu-id="53cea-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="53cea-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="53cea-121">Input Types</span></span>
<span data-ttu-id="53cea-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53cea-122"></span></span>

<span data-ttu-id="53cea-p103">Nenhum. O cmdlet Set-CcApplianceDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="53cea-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="53cea-125">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="53cea-125">Return Types</span></span>
<span data-ttu-id="53cea-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53cea-126"></span></span>

<span data-ttu-id="53cea-127">Nenhum </span><span class="sxs-lookup"><span data-stu-id="53cea-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="53cea-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="53cea-128">See also</span></span>
<span data-ttu-id="53cea-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53cea-129"></span></span>

<span data-ttu-id="53cea-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="53cea-130">None</span></span>
  

