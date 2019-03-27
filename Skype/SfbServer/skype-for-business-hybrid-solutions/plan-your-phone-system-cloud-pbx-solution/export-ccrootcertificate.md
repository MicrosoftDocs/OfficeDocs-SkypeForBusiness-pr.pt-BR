---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'O cmdlet Export-CcRootCertificate exporta o Certificado de Autoridade de Certificação raiz para um arquivo local no servidor host do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: c2647baa9ab6762feb8f550e0d726b18ab5d3090
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889221"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="3bc70-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="3bc70-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="3bc70-104">O cmdlet Export-CcRootCertificate exporta o Certificado de Autoridade de Certificação raiz para um arquivo local no servidor host do Skype for Business Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="3bc70-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="3bc70-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3bc70-105">Examples</span></span>
<span data-ttu-id="3bc70-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3bc70-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="3bc70-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="3bc70-107">Example 1</span></span>

<span data-ttu-id="3bc70-p101">O exemplo a seguir define o parâmetro Path como um caminho de diretório, não um caminho de arquivo. Ele gera o arquivo c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="3bc70-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="3bc70-110">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="3bc70-110">Detailed Description</span></span>
<span data-ttu-id="3bc70-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3bc70-111"></span></span>

<span data-ttu-id="3bc70-p102">O cmdlet Export-CcRootCertificate permite que você salve os certificados raiz e intermediário em um caminho de arquivo. Isso pode ser útil em um cenário de recuperação de desastre. </span><span class="sxs-lookup"><span data-stu-id="3bc70-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="3bc70-114">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3bc70-114">Parameters</span></span>
<span data-ttu-id="3bc70-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3bc70-115"></span></span>

|<span data-ttu-id="3bc70-116">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="3bc70-116">**Parameter**</span></span>|<span data-ttu-id="3bc70-117">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="3bc70-117">**Required**</span></span>|<span data-ttu-id="3bc70-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3bc70-118">**Type**</span></span>|<span data-ttu-id="3bc70-119">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3bc70-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3bc70-120">Path</span><span class="sxs-lookup"><span data-stu-id="3bc70-120">Path</span></span>  <br/> |<span data-ttu-id="3bc70-121">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="3bc70-121">Required</span></span>  <br/> |<span data-ttu-id="3bc70-122">System.String</span><span class="sxs-lookup"><span data-stu-id="3bc70-122">System.String</span></span>  <br/> |<span data-ttu-id="3bc70-123">Caminho do arquivo em que o certificado será armazenado. </span><span class="sxs-lookup"><span data-stu-id="3bc70-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3bc70-124">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="3bc70-124">Input Types</span></span>
<span data-ttu-id="3bc70-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3bc70-125"></span></span>

<span data-ttu-id="3bc70-p103">Nenhum. O cmdlet Export-CcRootCertificate não aceita a entrada por pipeline. </span><span class="sxs-lookup"><span data-stu-id="3bc70-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="3bc70-128">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="3bc70-128">Return Types</span></span>
<span data-ttu-id="3bc70-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3bc70-129"></span></span>

<span data-ttu-id="3bc70-130">Nenhum </span><span class="sxs-lookup"><span data-stu-id="3bc70-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3bc70-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3bc70-131">See also</span></span>
<span data-ttu-id="3bc70-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3bc70-132"></span></span>

<span data-ttu-id="3bc70-133">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3bc70-133">None</span></span>
  

