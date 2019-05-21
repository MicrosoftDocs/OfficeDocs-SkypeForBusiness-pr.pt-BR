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
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: O cmdlet Renew-CcCACertificate renova o certficado de Autoridade de Certificação raiz do Skype for Business Cloud Connector Edition que está prestes a expirar ou já expirou. Esse comando foi alterado para Update-CcCACertificate no Cloud Connector 2,0 e versões posteriores.
ms.openlocfilehash: f1e376b5b944468ec5bf508c6221a099a83d4804
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287101"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="25972-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="25972-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="25972-105">O cmdlet Renew-CcCACertificate renova o certficado de Autoridade de Certificação raiz do Skype for Business Cloud Connector Edition que está prestes a expirar ou já expirou.</span><span class="sxs-lookup"><span data-stu-id="25972-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="25972-106">Esse comando foi alterado para Update-CcCACertificate no Cloud Connector 2,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="25972-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="25972-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="25972-107">Parameters</span></span>

<span data-ttu-id="25972-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="25972-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="25972-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="25972-109">Examples</span></span>
<span data-ttu-id="25972-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="25972-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="25972-111">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="25972-111">Example 1</span></span>

<span data-ttu-id="25972-112">O exemplo seguinte renova o certificado de Autoridade de Certificação raiz: </span><span class="sxs-lookup"><span data-stu-id="25972-112">The following example renews the root CA certificate:</span></span> 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="25972-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="25972-113">Detailed Description</span></span>
<span data-ttu-id="25972-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="25972-114"></span></span>

<span data-ttu-id="25972-115">O certificado de Autoridade de Certificação raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação foi instalado.</span><span class="sxs-lookup"><span data-stu-id="25972-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="25972-p103">Se o certificado raiz estiver prestes a expirar ou já expirou, execute o cmdlet Renew-CcCACertificate para renovar o certificado. Depois que o certificado raiz tiver sido renovado, serão emitidos novos certificados automaticamente para o servidor AD, o Repositório de Gerenciamento Central e o Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="25972-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="25972-118">Se existirem vários dispositivos no mesmo site PSTN, execute o cmdlet Renew-CcCACertificate em todos os dispositivos do mesmo site PSTN.</span><span class="sxs-lookup"><span data-stu-id="25972-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="25972-119">Na última etapa, execute o cmdlet Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e depois copie e instale o certificado exportado para seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="25972-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="25972-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="25972-120">Input Types</span></span>
<span data-ttu-id="25972-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="25972-121"></span></span>

<span data-ttu-id="25972-p104">Nenhum. O cmdlet Renew-CcCACertificate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="25972-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="25972-124">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="25972-124">Return Types</span></span>
<span data-ttu-id="25972-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="25972-125"></span></span>

<span data-ttu-id="25972-126">Nenhum </span><span class="sxs-lookup"><span data-stu-id="25972-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="25972-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25972-127">See also</span></span>
<span data-ttu-id="25972-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="25972-128"></span></span>

[<span data-ttu-id="25972-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="25972-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="25972-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="25972-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="25972-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="25972-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

