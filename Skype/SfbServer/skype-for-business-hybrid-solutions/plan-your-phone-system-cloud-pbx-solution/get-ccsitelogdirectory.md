---
title: Get-CcSiteLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 'O cmdlet Get-CcSiteLogDirectory mostra o diretório atual onde estão armazenados os logs no nível do site do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: 68d89200ac8bf2aec32db45752d62d7ae205b830
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="a4881-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="a4881-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="a4881-104">O cmdlet Get-CcSiteLogDirectory mostra o diretório atual onde estão armazenados os logs no nível do site do Skype for Business Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="a4881-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="a4881-105">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a4881-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="a4881-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a4881-106">Parameters</span></span>

<span data-ttu-id="a4881-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a4881-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="a4881-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a4881-108">Examples</span></span>
<span data-ttu-id="a4881-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a4881-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="a4881-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="a4881-110">Example 1</span></span>

<span data-ttu-id="a4881-111">O exemplo a seguir mostra a pasta atual, onde os arquivos de log para o site do conector de nuvem são armazenados:</span><span class="sxs-lookup"><span data-stu-id="a4881-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="a4881-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="a4881-112">Detailed Description</span></span>
<span data-ttu-id="a4881-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a4881-113"></span></span>

<span data-ttu-id="a4881-114">A pasta padrão é C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="a4881-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="a4881-115">Você pode alterar a pasta executando o cmdlet Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="a4881-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="a4881-116">Não há cmdlet separado que altere somente o local da pasta de log sem alterar o diretório do site.</span><span class="sxs-lookup"><span data-stu-id="a4881-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="a4881-117">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="a4881-117">Input Types</span></span>
<span data-ttu-id="a4881-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a4881-118"></span></span>

<span data-ttu-id="a4881-p102">Nenhum. O cmdlet Get-CsClientVersionPolicy não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="a4881-p102">None. The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a4881-121">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="a4881-121">Return Types</span></span>
<span data-ttu-id="a4881-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a4881-122"></span></span>

<span data-ttu-id="a4881-123">O comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a4881-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4881-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a4881-124">See also</span></span>
<span data-ttu-id="a4881-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a4881-125"></span></span>

[<span data-ttu-id="a4881-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="a4881-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

