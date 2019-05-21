---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'O cmdlet Export-CcRootCertificate exporta o Certificado de Autoridade de Certificação raiz para um arquivo local no servidor host do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: 7d6d0978698b4b20b570107b51c9a89ff237b730
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287374"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="58a6a-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="58a6a-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="58a6a-104">O cmdlet Export-CcRootCertificate exporta o Certificado de Autoridade de Certificação raiz para um arquivo local no servidor host do Skype for Business Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="58a6a-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="58a6a-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="58a6a-105">Examples</span></span>
<span data-ttu-id="58a6a-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="58a6a-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="58a6a-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="58a6a-107">Example 1</span></span>

<span data-ttu-id="58a6a-p101">O exemplo a seguir define o parâmetro Path como um caminho de diretório, não um caminho de arquivo. Ele gera o arquivo c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="58a6a-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="58a6a-110">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="58a6a-110">Detailed Description</span></span>
<span data-ttu-id="58a6a-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="58a6a-111"></span></span>

<span data-ttu-id="58a6a-p102">O cmdlet Export-CcRootCertificate permite que você salve os certificados raiz e intermediário em um caminho de arquivo. Isso pode ser útil em um cenário de recuperação de desastre. </span><span class="sxs-lookup"><span data-stu-id="58a6a-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="58a6a-114">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="58a6a-114">Parameters</span></span>
<span data-ttu-id="58a6a-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="58a6a-115"></span></span>

|<span data-ttu-id="58a6a-116">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="58a6a-116">**Parameter**</span></span>|<span data-ttu-id="58a6a-117">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="58a6a-117">**Required**</span></span>|<span data-ttu-id="58a6a-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="58a6a-118">**Type**</span></span>|<span data-ttu-id="58a6a-119">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="58a6a-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58a6a-120">Path</span><span class="sxs-lookup"><span data-stu-id="58a6a-120">Path</span></span>  <br/> |<span data-ttu-id="58a6a-121">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="58a6a-121">Required</span></span>  <br/> |<span data-ttu-id="58a6a-122">System.String</span><span class="sxs-lookup"><span data-stu-id="58a6a-122">System.String</span></span>  <br/> |<span data-ttu-id="58a6a-123">Caminho do arquivo em que o certificado será armazenado. </span><span class="sxs-lookup"><span data-stu-id="58a6a-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="58a6a-124">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="58a6a-124">Input Types</span></span>
<span data-ttu-id="58a6a-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="58a6a-125"></span></span>

<span data-ttu-id="58a6a-p103">Nenhum. O cmdlet Export-CcRootCertificate não aceita a entrada por pipeline. </span><span class="sxs-lookup"><span data-stu-id="58a6a-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="58a6a-128">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="58a6a-128">Return Types</span></span>
<span data-ttu-id="58a6a-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="58a6a-129"></span></span>

<span data-ttu-id="58a6a-130">Nenhum </span><span class="sxs-lookup"><span data-stu-id="58a6a-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58a6a-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58a6a-131">See also</span></span>
<span data-ttu-id="58a6a-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="58a6a-132"></span></span>

<span data-ttu-id="58a6a-133">Nenhum</span><span class="sxs-lookup"><span data-stu-id="58a6a-133">None</span></span>
  

