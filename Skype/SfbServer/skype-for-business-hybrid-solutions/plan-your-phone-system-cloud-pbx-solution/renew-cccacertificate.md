---
title: Renovar-CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: O cmdlet Renew-CcCACertificate renova o certficado de Autoridade de Certificação raiz do Skype for Business Cloud Connector Edition que está prestes a expirar ou já expirou. Este comando foi alterado para atualização-CcCACertificate na nuvem conector 2.0 e versões posteriores.
ms.openlocfilehash: bfcf7c69e27af8ebf83c85a8c90cc46491fbc454
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="311b5-104">Renovar-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="311b5-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="311b5-105">O cmdlet Renew-CcCACertificate renova o certficado de Autoridade de Certificação raiz do Skype for Business Cloud Connector Edition que está prestes a expirar ou já expirou.</span><span class="sxs-lookup"><span data-stu-id="311b5-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="311b5-106">Este comando foi alterado para atualização-CcCACertificate na nuvem conector 2.0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="311b5-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="311b5-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="311b5-107">Parameters</span></span>

<span data-ttu-id="311b5-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="311b5-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="311b5-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="311b5-109">Examples</span></span>
<span data-ttu-id="311b5-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="311b5-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="311b5-111">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="311b5-111">Example 1</span></span>

<span data-ttu-id="311b5-112">O exemplo seguinte renova o certificado de Autoridade de Certificação raiz: </span><span class="sxs-lookup"><span data-stu-id="311b5-112">The following example renews the root CA certificate:</span></span> 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="311b5-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="311b5-113">Detailed Description</span></span>
<span data-ttu-id="311b5-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="311b5-114"></span></span>

<span data-ttu-id="311b5-115">O certificado de Autoridade de Certificação raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação foi instalado.</span><span class="sxs-lookup"><span data-stu-id="311b5-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="311b5-p103">Se o certificado raiz estiver prestes a expirar ou já expirou, execute o cmdlet Renew-CcCACertificate para renovar o certificado. Depois que o certificado raiz tiver sido renovado, serão emitidos novos certificados automaticamente para o servidor AD, o Repositório de Gerenciamento Central e o Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="311b5-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="311b5-118">Se existirem vários dispositivos no mesmo site PSTN, execute o cmdlet Renew-CcCACertificate em todos os dispositivos do mesmo site PSTN.</span><span class="sxs-lookup"><span data-stu-id="311b5-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="311b5-119">Na última etapa, execute o cmdlet Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e depois copie e instale o certificado exportado para seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="311b5-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="311b5-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="311b5-120">Input Types</span></span>
<span data-ttu-id="311b5-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="311b5-121"></span></span>

<span data-ttu-id="311b5-p104">Nenhum. O cmdlet Renew-CcCACertificate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="311b5-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="311b5-124">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="311b5-124">Return Types</span></span>
<span data-ttu-id="311b5-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="311b5-125"></span></span>

<span data-ttu-id="311b5-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="311b5-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="311b5-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="311b5-127">See also</span></span>
<span data-ttu-id="311b5-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="311b5-128"></span></span>

[<span data-ttu-id="311b5-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="311b5-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="311b5-130">Renovar-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="311b5-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="311b5-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="311b5-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

