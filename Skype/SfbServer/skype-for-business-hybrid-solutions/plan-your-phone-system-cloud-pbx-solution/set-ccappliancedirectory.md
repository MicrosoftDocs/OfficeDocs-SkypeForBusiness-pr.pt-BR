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
ms.openlocfilehash: 1dfc85a08709fd550b91dbecdb5d4186f265ca67
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003221"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="b4a37-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b4a37-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="b4a37-p102">O cmdlet Set-CcApplianceDirectory define o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.</span><span class="sxs-lookup"><span data-stu-id="b4a37-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="b4a37-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b4a37-107">Examples</span></span>
<span data-ttu-id="b4a37-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b4a37-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="b4a37-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b4a37-109">Example 1</span></span>

<span data-ttu-id="b4a37-110">O exemplo a seguir define o diretório de trabalho no servidor host como c:\cloudconnector\applianceroot:</span><span class="sxs-lookup"><span data-stu-id="b4a37-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="b4a37-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b4a37-111">Parameters</span></span>
<span data-ttu-id="b4a37-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b4a37-112"></span></span>

|<span data-ttu-id="b4a37-113">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="b4a37-113">**Parameter**</span></span>|<span data-ttu-id="b4a37-114">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="b4a37-114">**Required**</span></span>|<span data-ttu-id="b4a37-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b4a37-115">**Type**</span></span>|<span data-ttu-id="b4a37-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b4a37-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b4a37-117">Path</span><span class="sxs-lookup"><span data-stu-id="b4a37-117">Path</span></span> <br/> | <span data-ttu-id="b4a37-118">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b4a37-118">Required</span></span> <br/> |<span data-ttu-id="b4a37-119">System.String</span><span class="sxs-lookup"><span data-stu-id="b4a37-119">System.String</span></span>  <br/> | <span data-ttu-id="b4a37-120">Especifica o caminho onde todos os arquivos da implantação são armazenados.</span><span class="sxs-lookup"><span data-stu-id="b4a37-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b4a37-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="b4a37-121">Input Types</span></span>
<span data-ttu-id="b4a37-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b4a37-122"></span></span>

<span data-ttu-id="b4a37-p103">Nenhum. O cmdlet Set-CcApplianceDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="b4a37-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b4a37-125">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="b4a37-125">Return Types</span></span>
<span data-ttu-id="b4a37-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b4a37-126"></span></span>

<span data-ttu-id="b4a37-127">Nenhum </span><span class="sxs-lookup"><span data-stu-id="b4a37-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b4a37-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4a37-128">See also</span></span>
<span data-ttu-id="b4a37-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b4a37-129"></span></span>

<span data-ttu-id="b4a37-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b4a37-130">None</span></span>
  

