---
title: Iniciar-CcDownload
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: O cmdlet Start-CcDownload baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma sincronizada.
ms.openlocfilehash: aec8d5c1848e7e55d6ed4b7e4d3633942f74ab55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="start-ccdownload"></a><span data-ttu-id="1a912-103">Iniciar-CcDownload</span><span class="sxs-lookup"><span data-stu-id="1a912-103">Start-CcDownload</span></span>
 
<span data-ttu-id="1a912-104">O cmdlet Start-CcDownload baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma sincronizada.</span><span class="sxs-lookup"><span data-stu-id="1a912-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="1a912-105">Com o Cloud Connector versão 2.0 e posteriores, você também pode especificar o parâmetro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="1a912-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="1a912-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1a912-106">Examples</span></span>
<span data-ttu-id="1a912-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1a912-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="1a912-108">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="1a912-108">Example 1</span></span>

<span data-ttu-id="1a912-109">O exemplo a seguir baixa os bits de conector de nuvem e o arquivo msi de maneira síncrona o conector de nuvem pública do site de download:</span><span class="sxs-lookup"><span data-stu-id="1a912-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="1a912-110">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="1a912-110">Example 2</span></span>

<span data-ttu-id="1a912-111">O próximo exemplo baixa os bits de conector de nuvem e o arquivo msi de maneira síncrona de um site de download privada:</span><span class="sxs-lookup"><span data-stu-id="1a912-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="1a912-112">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="1a912-112">Example 3</span></span>

<span data-ttu-id="1a912-113">O terceiro exemplo baixa os bits e o arquivo msi do Cloud Connector de forma sincronizada de um site de download privado.</span><span class="sxs-lookup"><span data-stu-id="1a912-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="1a912-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="1a912-114">Detailed Description</span></span>
<span data-ttu-id="1a912-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1a912-115"></span></span>

<span data-ttu-id="1a912-116">Se houver uma nova versão disponível no site de download, Start-CcDownload irá baixar e instalar o arquivo msi no site de download e, em seguida, baixe os bits de conector de nuvem de maneira síncrona.</span><span class="sxs-lookup"><span data-stu-id="1a912-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="1a912-117">Se não houver nenhuma nova versão do arquivo msi, o Start-CcDownload baixará apenas os bits do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1a912-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="1a912-118">Se os bits do Cloud Connector já tiverem sido baixados, o Start-CcDownload não será executado.</span><span class="sxs-lookup"><span data-stu-id="1a912-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1a912-119">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1a912-119">Parameters</span></span>
<span data-ttu-id="1a912-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1a912-120"></span></span>

|<span data-ttu-id="1a912-121">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="1a912-121">**Parameter**</span></span>|<span data-ttu-id="1a912-122">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="1a912-122">**Required**</span></span>|<span data-ttu-id="1a912-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1a912-123">**Type**</span></span>|<span data-ttu-id="1a912-124">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1a912-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1a912-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="1a912-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="1a912-126">Opcional</span><span class="sxs-lookup"><span data-stu-id="1a912-126">Optional</span></span> <br/> |<span data-ttu-id="1a912-127">System. String</span><span class="sxs-lookup"><span data-stu-id="1a912-127">System.String</span></span>  <br/> | <span data-ttu-id="1a912-128">Site de download a URL completa de uma versão específica do conector de nuvem em particular.</span><span class="sxs-lookup"><span data-stu-id="1a912-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="1a912-129">Use esse parâmetro com cuidado — Certifique-se de que você está ciente de qual versão do conector de nuvem você estiver baixando os dados.</span><span class="sxs-lookup"><span data-stu-id="1a912-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="1a912-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="1a912-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="1a912-131">Opcional</span><span class="sxs-lookup"><span data-stu-id="1a912-131">Optional</span></span>  <br/> |<span data-ttu-id="1a912-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1a912-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="1a912-133">Ignore a etapa de baixar e instalar o MSI do site de download, baixe apenas os bits do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1a912-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1a912-134">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="1a912-134">Input Types</span></span>
<span data-ttu-id="1a912-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1a912-135"></span></span>

<span data-ttu-id="1a912-136">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1a912-136">None.</span></span> <span data-ttu-id="1a912-137">O cmdlet Start-CcDownload não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="1a912-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1a912-138">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="1a912-138">Return Types</span></span>
<span data-ttu-id="1a912-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1a912-139"></span></span>

<span data-ttu-id="1a912-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1a912-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1a912-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1a912-141">See also</span></span>
<span data-ttu-id="1a912-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1a912-142"></span></span>

<span data-ttu-id="1a912-143">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1a912-143">None</span></span>
  

