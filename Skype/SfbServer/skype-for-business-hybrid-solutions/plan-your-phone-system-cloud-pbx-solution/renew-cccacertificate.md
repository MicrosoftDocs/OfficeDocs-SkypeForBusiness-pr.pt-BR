---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: O Renew-CcCACertificate cmdlet renova o certificado de AC raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou já expirou. Esse comando foi alterado para Update-CcCACertificate no Cloud Connector 2.0 e versões posteriores.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824267"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="e7adf-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="e7adf-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="e7adf-105">O Renew-CcCACertificate cmdlet renova o certificado de AC raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou já expirou.</span><span class="sxs-lookup"><span data-stu-id="e7adf-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="e7adf-106">Esse comando foi alterado para Update-CcCACertificate no Cloud Connector 2.0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="e7adf-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="e7adf-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e7adf-107">Parameters</span></span>

<span data-ttu-id="e7adf-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e7adf-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e7adf-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e7adf-109">Examples</span></span>
<span data-ttu-id="e7adf-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e7adf-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e7adf-111">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="e7adf-111">Example 1</span></span>

<span data-ttu-id="e7adf-112">O exemplo a seguir renova o certificado ca raiz:</span><span class="sxs-lookup"><span data-stu-id="e7adf-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="e7adf-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="e7adf-113">Detailed Description</span></span>
<span data-ttu-id="e7adf-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e7adf-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e7adf-115">O certificado de autoridade de certificação raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação está instalado.</span><span class="sxs-lookup"><span data-stu-id="e7adf-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="e7adf-116">Se o certificado raiz estiver próximo de expirar ou já tiver expirado, execute o Renew-CcCACertificate cmdlet para renovar o certificado.</span><span class="sxs-lookup"><span data-stu-id="e7adf-116">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="e7adf-117">Depois que o certificado raiz for renovado, o Servidor do AD, o Armazenamento de Gerenciamento Central e o Servidor de Borda receberão novos certificados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e7adf-117">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="e7adf-118">Se houver vários dispositivos no mesmo site PSTN, execute o cmdlet Renew-CcCACertificate em todos os dispositivos do mesmo site PSTN.</span><span class="sxs-lookup"><span data-stu-id="e7adf-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="e7adf-119">Como última etapa, execute Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e, em seguida, copie e instale o certificado exportado para seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="e7adf-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e7adf-120">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="e7adf-120">Input Types</span></span>
<span data-ttu-id="e7adf-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7adf-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e7adf-122">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e7adf-122">None.</span></span> <span data-ttu-id="e7adf-123">O Renew-CcCACertificate cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="e7adf-123">The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e7adf-124">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="e7adf-124">Return Types</span></span>
<span data-ttu-id="e7adf-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7adf-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e7adf-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e7adf-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7adf-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="e7adf-127">See also</span></span>
<span data-ttu-id="e7adf-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7adf-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e7adf-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="e7adf-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="e7adf-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="e7adf-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="e7adf-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="e7adf-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

