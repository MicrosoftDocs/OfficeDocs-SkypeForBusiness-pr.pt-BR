---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: O Start-CcDownload cmdlet baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma síncrona.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824175"
---
# <a name="start-ccdownload"></a><span data-ttu-id="a1d2d-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="a1d2d-103">Start-CcDownload</span></span>
 
<span data-ttu-id="a1d2d-104">O Start-CcDownload cmdlet baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="a1d2d-105">Com o Cloud Connector versão 2.0 e posterior, você também pode especificar o parâmetro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="a1d2d-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a1d2d-106">Examples</span></span>
<span data-ttu-id="a1d2d-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d2d-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a1d2d-108">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="a1d2d-108">Example 1</span></span>

<span data-ttu-id="a1d2d-109">O exemplo a seguir baixa os bits e o arquivo msi do Cloud Connector de forma síncrona do site de download público do Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="a1d2d-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="a1d2d-110">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="a1d2d-110">Example 2</span></span>

<span data-ttu-id="a1d2d-111">O próximo exemplo baixa os bits e o arquivo msi do Cloud Connector de forma síncrona de um site de download privado:</span><span class="sxs-lookup"><span data-stu-id="a1d2d-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="a1d2d-112">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="a1d2d-112">Example 3</span></span>

<span data-ttu-id="a1d2d-113">O terceiro exemplo baixa os bits e o arquivo msi do Cloud Connector de forma síncrona de um site de download privado.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="a1d2d-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="a1d2d-114">Detailed Description</span></span>
<span data-ttu-id="a1d2d-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d2d-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a1d2d-116">Se houver uma nova versão disponível no site de download, o Start-CcDownload baixará e instalará o arquivo msi do site de download e baixará os bits do Cloud Connector de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="a1d2d-117">Se não houver nenhuma nova versão do arquivo msi, o Start-CcDownload baixará apenas os bits do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="a1d2d-118">Se os bits do Cloud Connector já foram baixados, Start-CcDownload não será executado.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a1d2d-119">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a1d2d-119">Parameters</span></span>
<span data-ttu-id="a1d2d-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d2d-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="a1d2d-121">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="a1d2d-121">**Parameter**</span></span>|<span data-ttu-id="a1d2d-122">**Required**</span><span class="sxs-lookup"><span data-stu-id="a1d2d-122">**Required**</span></span>|<span data-ttu-id="a1d2d-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a1d2d-123">**Type**</span></span>|<span data-ttu-id="a1d2d-124">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a1d2d-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a1d2d-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="a1d2d-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="a1d2d-126">Opcional</span><span class="sxs-lookup"><span data-stu-id="a1d2d-126">Optional</span></span> <br/> |<span data-ttu-id="a1d2d-127">System.String</span><span class="sxs-lookup"><span data-stu-id="a1d2d-127">System.String</span></span>  <br/> | <span data-ttu-id="a1d2d-128">A URL completa de uma versão específica do Cloud Connector no site de download privado.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="a1d2d-129">Use esse parâmetro com cuidado. Certifique-se de que está ciente de qual versão do Cloud Connector você está baixando.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="a1d2d-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="a1d2d-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="a1d2d-131">Opcional</span><span class="sxs-lookup"><span data-stu-id="a1d2d-131">Optional</span></span>  <br/> |<span data-ttu-id="a1d2d-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a1d2d-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a1d2d-133">Ignore a etapa para baixar e instalar o MSI do site de download, baixe apenas os bits do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a1d2d-134">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="a1d2d-134">Input Types</span></span>
<span data-ttu-id="a1d2d-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d2d-135"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a1d2d-136">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-136">None.</span></span> <span data-ttu-id="a1d2d-137">O Start-CcDownload cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="a1d2d-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a1d2d-138">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="a1d2d-138">Return Types</span></span>
<span data-ttu-id="a1d2d-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d2d-139"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a1d2d-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a1d2d-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1d2d-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="a1d2d-141">See also</span></span>
<span data-ttu-id="a1d2d-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d2d-142"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a1d2d-143">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a1d2d-143">None</span></span>
  

