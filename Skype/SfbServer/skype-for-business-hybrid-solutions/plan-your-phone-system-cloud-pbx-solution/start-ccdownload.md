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
description: O cmdlet Start-CcDownload baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma sincronizada.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824175"
---
# <a name="start-ccdownload"></a><span data-ttu-id="2c586-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="2c586-103">Start-CcDownload</span></span>
 
<span data-ttu-id="2c586-104">O cmdlet Start-CcDownload baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma sincronizada.</span><span class="sxs-lookup"><span data-stu-id="2c586-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="2c586-105">Com o Cloud Connector versão 2.0 e posteriores, você também pode especificar o parâmetro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="2c586-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="2c586-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2c586-106">Examples</span></span>
<span data-ttu-id="2c586-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c586-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2c586-108">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2c586-108">Example 1</span></span>

<span data-ttu-id="2c586-109">O exemplo a seguir baixa os bits do conector de nuvem e o arquivo MSI sincronicamente do site de download público do conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="2c586-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="2c586-110">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="2c586-110">Example 2</span></span>

<span data-ttu-id="2c586-111">O próximo exemplo baixa os bits do conector de nuvem e o arquivo MSI de forma síncrona a partir de um site de download particular:</span><span class="sxs-lookup"><span data-stu-id="2c586-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="2c586-112">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="2c586-112">Example 3</span></span>

<span data-ttu-id="2c586-113">O terceiro exemplo baixa os bits e o arquivo msi do Cloud Connector de forma sincronizada de um site de download privado.</span><span class="sxs-lookup"><span data-stu-id="2c586-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="2c586-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="2c586-114">Detailed Description</span></span>
<span data-ttu-id="2c586-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2c586-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2c586-116">Se houver uma nova versão disponível no site de download, o Start-CcDownload baixará e instalará o arquivo MSI do site de download e, em seguida, baixará o bits do conector de nuvem sincronicamente.</span><span class="sxs-lookup"><span data-stu-id="2c586-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="2c586-117">Se não houver nenhuma nova versão do arquivo msi, o Start-CcDownload baixará apenas os bits do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2c586-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="2c586-118">Se os bits do Cloud Connector já tiverem sido baixados, o Start-CcDownload não será executado.</span><span class="sxs-lookup"><span data-stu-id="2c586-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2c586-119">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2c586-119">Parameters</span></span>
<span data-ttu-id="2c586-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2c586-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="2c586-121">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="2c586-121">**Parameter**</span></span>|<span data-ttu-id="2c586-122">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="2c586-122">**Required**</span></span>|<span data-ttu-id="2c586-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2c586-123">**Type**</span></span>|<span data-ttu-id="2c586-124">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2c586-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c586-125">DownloadUrlRoot </span><span class="sxs-lookup"><span data-stu-id="2c586-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="2c586-126">Opcional </span><span class="sxs-lookup"><span data-stu-id="2c586-126">Optional</span></span> <br/> |<span data-ttu-id="2c586-127">System.String</span><span class="sxs-lookup"><span data-stu-id="2c586-127">System.String</span></span>  <br/> | <span data-ttu-id="2c586-128">A URL completa de uma versão específica do conector de nuvem no site de download particular.</span><span class="sxs-lookup"><span data-stu-id="2c586-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="2c586-129">Use esse parâmetro com cuidado: Certifique-se de que a versão do conector de nuvem que você está baixando.</span><span class="sxs-lookup"><span data-stu-id="2c586-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="2c586-130">DownloadBitsOnly </span><span class="sxs-lookup"><span data-stu-id="2c586-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="2c586-131">Opcional</span><span class="sxs-lookup"><span data-stu-id="2c586-131">Optional</span></span>  <br/> |<span data-ttu-id="2c586-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2c586-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="2c586-133">Ignore a etapa de baixar e instalar o MSI do site de download, baixe apenas os bits do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2c586-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2c586-134">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2c586-134">Input Types</span></span>
<span data-ttu-id="2c586-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c586-135"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2c586-p103">Nenhum. O cmdlet Start-CcDownload não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="2c586-p103">None. The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2c586-138">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="2c586-138">Return Types</span></span>
<span data-ttu-id="2c586-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c586-139"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2c586-140">Nenhum </span><span class="sxs-lookup"><span data-stu-id="2c586-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c586-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2c586-141">See also</span></span>
<span data-ttu-id="2c586-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c586-142"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2c586-143">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2c586-143">None</span></span>
  

