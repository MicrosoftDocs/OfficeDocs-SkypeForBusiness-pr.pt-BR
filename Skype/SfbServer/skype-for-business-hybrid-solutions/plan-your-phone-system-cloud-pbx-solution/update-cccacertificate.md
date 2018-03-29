---
title: Update-CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: O cmdlet Update-CcCACertificate renova o certificado da autoridade de certificação raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou que já tenha expirado.
ms.openlocfilehash: f23298f1be30ab96b3e77ff0625ff6e3b419e111
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="update-cccacertificate"></a><span data-ttu-id="5763a-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5763a-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="5763a-104">O cmdlet Update-CcCACertificate renova o certificado da autoridade de certificação raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou que já tenha expirado.</span><span class="sxs-lookup"><span data-stu-id="5763a-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="5763a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5763a-105">Parameters</span></span>

<span data-ttu-id="5763a-106">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5763a-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="5763a-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5763a-107">Examples</span></span>
<span data-ttu-id="5763a-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5763a-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="5763a-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="5763a-109">Example 1</span></span>

<span data-ttu-id="5763a-110">O exemplo seguinte renova o certificado de Autoridade de Certificação raiz: </span><span class="sxs-lookup"><span data-stu-id="5763a-110">The following example renews the root CA certificate:</span></span> 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="5763a-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="5763a-111">Detailed Description</span></span>
<span data-ttu-id="5763a-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5763a-112"></span></span>

<span data-ttu-id="5763a-113">O certificado de Autoridade de Certificação raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação foi instalado.</span><span class="sxs-lookup"><span data-stu-id="5763a-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="5763a-114">Se o certificado raiz estiver quase expirado ou já tiver expirado, execute o cmdlet Update-CcCACertificate para renovar o certificado.</span><span class="sxs-lookup"><span data-stu-id="5763a-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="5763a-115">Depois que o certificado raiz for renovado, o Servidor AD, o Repositório de Gerenciamento Central e o Servidor de Borda receberão novos certificados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5763a-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="5763a-116">Se houver vários dispositivos no mesmo local de PSTN, execute o cmdlet Update-CcCACertificate em todos os dispositivos do mesmo local de PSTN.</span><span class="sxs-lookup"><span data-stu-id="5763a-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="5763a-117">Na última etapa, execute o cmdlet Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e depois copie e instale o certificado exportado para seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="5763a-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="5763a-118">Este comando substitui o cmdlet Renew-CcCACertificate no Cloud Connector 2.0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="5763a-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5763a-119">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="5763a-119">Input Types</span></span>
<span data-ttu-id="5763a-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5763a-120"></span></span>

<span data-ttu-id="5763a-121">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5763a-121">None.</span></span> <span data-ttu-id="5763a-122">O cmdlet Update-CcCACertificate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="5763a-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5763a-123">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="5763a-123">Return Types</span></span>
<span data-ttu-id="5763a-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5763a-124"></span></span>

<span data-ttu-id="5763a-125">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5763a-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5763a-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5763a-126">See also</span></span>
<span data-ttu-id="5763a-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5763a-127"></span></span>

[<span data-ttu-id="5763a-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5763a-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="5763a-129">Renovar-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="5763a-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="5763a-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="5763a-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

