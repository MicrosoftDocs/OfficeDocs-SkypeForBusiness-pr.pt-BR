---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: O Update-CcCACertificate cmdlet renova o certificado de AC raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou já expirou.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824115"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="53b86-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="53b86-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="53b86-104">O Update-CcCACertificate cmdlet renova o certificado de AC raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou já expirou.</span><span class="sxs-lookup"><span data-stu-id="53b86-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="53b86-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="53b86-105">Parameters</span></span>

<span data-ttu-id="53b86-106">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="53b86-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="53b86-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="53b86-107">Examples</span></span>
<span data-ttu-id="53b86-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="53b86-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="53b86-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="53b86-109">Example 1</span></span>

<span data-ttu-id="53b86-110">O exemplo a seguir renova o certificado ca raiz:</span><span class="sxs-lookup"><span data-stu-id="53b86-110">The following example renews the root CA certificate:</span></span> 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="53b86-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="53b86-111">Detailed Description</span></span>
<span data-ttu-id="53b86-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="53b86-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="53b86-113">O certificado de autoridade de certificação raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação está instalado.</span><span class="sxs-lookup"><span data-stu-id="53b86-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="53b86-114">Se o certificado raiz estiver próximo de expirar ou já tiver expirado, execute o Update-CcCACertificate cmdlet para renovar o certificado.</span><span class="sxs-lookup"><span data-stu-id="53b86-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="53b86-115">Depois que o certificado raiz for renovado, o Servidor do AD, o Armazenamento de Gerenciamento Central e o Servidor de Borda receberão novos certificados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="53b86-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="53b86-116">Se houver vários dispositivos no mesmo site PSTN, execute o cmdlet Update-CcCACertificate em todos os dispositivos do mesmo site PSTN.</span><span class="sxs-lookup"><span data-stu-id="53b86-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="53b86-117">Como última etapa, execute Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e, em seguida, copie e instale o certificado exportado para seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="53b86-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="53b86-118">Este comando substitui o Renew-CcCACertificate cmdlet no Cloud Connector 2.0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="53b86-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="53b86-119">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="53b86-119">Input Types</span></span>
<span data-ttu-id="53b86-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53b86-120"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="53b86-121">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="53b86-121">None.</span></span> <span data-ttu-id="53b86-122">O Update-CcCACertificate cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="53b86-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="53b86-123">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="53b86-123">Return Types</span></span>
<span data-ttu-id="53b86-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53b86-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="53b86-125">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="53b86-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="53b86-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="53b86-126">See also</span></span>
<span data-ttu-id="53b86-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="53b86-127"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="53b86-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="53b86-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="53b86-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="53b86-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="53b86-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="53b86-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

