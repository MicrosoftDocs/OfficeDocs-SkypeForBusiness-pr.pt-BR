---
title: Reset-CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: O cmdlet Reset-CcCACertificate reinstala o servidor AD de serviço de Autoridade de Certificação para criar um novo certificado de Autoridade de Certificação raiz.
ms.openlocfilehash: dc86c39e844accc789ba7a3503aa6261d40e5cb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="5518d-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5518d-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="5518d-104">O cmdlet Reset-CcCACertificate reinstala o servidor AD de serviço de Autoridade de Certificação para criar um novo certificado de Autoridade de Certificação raiz.</span><span class="sxs-lookup"><span data-stu-id="5518d-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="5518d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5518d-105">Parameters</span></span>

<span data-ttu-id="5518d-106">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5518d-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5518d-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5518d-107">Examples</span></span>
<span data-ttu-id="5518d-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5518d-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="5518d-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="5518d-109">Example 1</span></span>

<span data-ttu-id="5518d-110">O exemplo seguinte reinstala o servidor AD de serviço de Autoridade de Certificação para criar um novo certificado de Autoridade de Certificação raiz:</span><span class="sxs-lookup"><span data-stu-id="5518d-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="5518d-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="5518d-111">Detailed Description</span></span>
<span data-ttu-id="5518d-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5518d-112"></span></span>

<span data-ttu-id="5518d-113">Se o certificado de Autoridade de Certificação raiz estiver comprometido ou não for mais seguro, você deverá atualizar o certificado de Autoridade de Certificação raiz e todos os certificados emitidos pela Autoridade de Certificação raiz.</span><span class="sxs-lookup"><span data-stu-id="5518d-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="5518d-114">O cmdlet Reset-CcCACertificate revoga todos os certificados, desinstala e reinstala a Autoridade de Certificação e depois limpa todos os certificados relacionados ao serviço de Autoridade de Certificação antigo.</span><span class="sxs-lookup"><span data-stu-id="5518d-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="5518d-115">Para obter mais informações, consulte "Certificado certificados de autoridade de certificados internos emitidos CMS, o servidor de mediação e o servidor de borda estão prestes a expirar ou estão comprometidos" na sua implantação do conector de nuvem de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="5518d-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5518d-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="5518d-116">Input Types</span></span>
<span data-ttu-id="5518d-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5518d-117"></span></span>

<span data-ttu-id="5518d-p102">Nenhum. O cmdlet Reset-CcCACertificate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="5518d-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5518d-120">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="5518d-120">Return Types</span></span>
<span data-ttu-id="5518d-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5518d-121"></span></span>

<span data-ttu-id="5518d-122">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5518d-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5518d-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5518d-123">See also</span></span>
<span data-ttu-id="5518d-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5518d-124"></span></span>

<span data-ttu-id="5518d-125">[Renovar-CcCACertificate](renew-cccacertificate.md) Somente versão 1.4.2</span><span class="sxs-lookup"><span data-stu-id="5518d-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="5518d-126">[Renovar-CcServerCertificate](renew-ccservercertificate.md) Somente versão 1.4.2</span><span class="sxs-lookup"><span data-stu-id="5518d-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="5518d-127">[Update-CcCACertificate](update-cccacertificate.md) Versão 2.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="5518d-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="5518d-128">[Renovar-CcServerCertificate](renew-ccservercertificate.md) Versão 2.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="5518d-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="5518d-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="5518d-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

