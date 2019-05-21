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
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: O cmdlet Set-CcApplianceDirectory define o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.
ms.openlocfilehash: 56a13da740b0c23adee7e05ddbcc1bbc82f0f1cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287052"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="88152-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="88152-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="88152-p102">O cmdlet Set-CcApplianceDirectory define o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.</span><span class="sxs-lookup"><span data-stu-id="88152-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="88152-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="88152-107">Examples</span></span>
<span data-ttu-id="88152-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="88152-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="88152-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="88152-109">Example 1</span></span>

<span data-ttu-id="88152-110">O exemplo a seguir define o diretório de trabalho no servidor host como c:\cloudconnector\applianceroot:</span><span class="sxs-lookup"><span data-stu-id="88152-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="88152-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="88152-111">Parameters</span></span>
<span data-ttu-id="88152-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="88152-112"></span></span>

|<span data-ttu-id="88152-113">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="88152-113">**Parameter**</span></span>|<span data-ttu-id="88152-114">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="88152-114">**Required**</span></span>|<span data-ttu-id="88152-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="88152-115">**Type**</span></span>|<span data-ttu-id="88152-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="88152-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="88152-117">Path</span><span class="sxs-lookup"><span data-stu-id="88152-117">Path</span></span> <br/> | <span data-ttu-id="88152-118">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="88152-118">Required</span></span> <br/> |<span data-ttu-id="88152-119">System.String</span><span class="sxs-lookup"><span data-stu-id="88152-119">System.String</span></span>  <br/> | <span data-ttu-id="88152-120">Especifica o caminho onde todos os arquivos da implantação são armazenados.</span><span class="sxs-lookup"><span data-stu-id="88152-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="88152-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="88152-121">Input Types</span></span>
<span data-ttu-id="88152-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="88152-122"></span></span>

<span data-ttu-id="88152-p103">Nenhum. O cmdlet Set-CcApplianceDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="88152-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="88152-125">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="88152-125">Return Types</span></span>
<span data-ttu-id="88152-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="88152-126"></span></span>

<span data-ttu-id="88152-127">Nenhum </span><span class="sxs-lookup"><span data-stu-id="88152-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="88152-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="88152-128">See also</span></span>
<span data-ttu-id="88152-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="88152-129"></span></span>

<span data-ttu-id="88152-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="88152-130">None</span></span>
  

