---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: O Get-CcSiteLogDirectory cmdlet mostra o diretório atual onde os logs no nível do site do Skype for Business Cloud Connector Edition estão armazenados.
ms.openlocfilehash: cace3ce3757294adbb3c55db24c619925f55ce5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799881"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="2ad33-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="2ad33-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="2ad33-104">O Get-CcSiteLogDirectory cmdlet mostra o diretório atual onde os logs no nível do site do Skype for Business Cloud Connector Edition estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="2ad33-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="2ad33-105">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2ad33-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="2ad33-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2ad33-106">Parameters</span></span>

<span data-ttu-id="2ad33-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2ad33-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2ad33-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2ad33-108">Examples</span></span>
<span data-ttu-id="2ad33-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2ad33-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2ad33-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2ad33-110">Example 1</span></span>

<span data-ttu-id="2ad33-111">O exemplo a seguir mostra a pasta atual onde os arquivos de log do site do Cloud Connector estão armazenados:</span><span class="sxs-lookup"><span data-stu-id="2ad33-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="2ad33-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="2ad33-112">Detailed Description</span></span>
<span data-ttu-id="2ad33-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2ad33-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2ad33-114">A pasta padrão é C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="2ad33-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="2ad33-115">Você pode alterar a pasta executando o Set-CcSiteDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad33-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="2ad33-116">Não há cmdlet separado que altera apenas o local da pasta de log sem alterar o diretório do site.</span><span class="sxs-lookup"><span data-stu-id="2ad33-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2ad33-117">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="2ad33-117">Input Types</span></span>
<span data-ttu-id="2ad33-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2ad33-118"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2ad33-119">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2ad33-119">None.</span></span> <span data-ttu-id="2ad33-120">O Get-CcSiteLogDirectory cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="2ad33-120">The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2ad33-121">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="2ad33-121">Return Types</span></span>
<span data-ttu-id="2ad33-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2ad33-122"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2ad33-123">O comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad33-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2ad33-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="2ad33-124">See also</span></span>
<span data-ttu-id="2ad33-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2ad33-125"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="2ad33-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="2ad33-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

