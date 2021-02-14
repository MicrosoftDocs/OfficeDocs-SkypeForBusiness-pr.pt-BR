---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: O Reset-CcCACertificate cmdlet reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de AUTORIDADE de Certificação raiz.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824247"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="2fbb7-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="2fbb7-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="2fbb7-104">O Reset-CcCACertificate cmdlet reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de AUTORIDADE de Certificação raiz.</span><span class="sxs-lookup"><span data-stu-id="2fbb7-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="2fbb7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2fbb7-105">Parameters</span></span>

<span data-ttu-id="2fbb7-106">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2fbb7-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2fbb7-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2fbb7-107">Examples</span></span>
<span data-ttu-id="2fbb7-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2fbb7-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2fbb7-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2fbb7-109">Example 1</span></span>

<span data-ttu-id="2fbb7-110">O exemplo a seguir reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de autoridade de certificação raiz:</span><span class="sxs-lookup"><span data-stu-id="2fbb7-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="2fbb7-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="2fbb7-111">Detailed Description</span></span>
<span data-ttu-id="2fbb7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2fbb7-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2fbb7-113">Se o certificado de AC raiz estiver comprometido ou não for mais seguro, você deverá atualizar o certificado de ac raiz e todos os certificados emitidos pela CA raiz.</span><span class="sxs-lookup"><span data-stu-id="2fbb7-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="2fbb7-114">O cmdlet Reset-CcCACertificate revoga todos os certificados, desinstala e reinstala a Autoridade de Certificação e limpa todos os certificados relacionados ao antigo serviço de Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="2fbb7-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="2fbb7-115">Para obter mais informações, consulte "Certificados de autoridade de certificação ou certificados internos emitidos para CMS, Servidor de Mediação e Servidor de Borda estão próximos de expirar ou estão comprometidos" na Solução de problemas de sua implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2fbb7-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2fbb7-116">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="2fbb7-116">Input Types</span></span>
<span data-ttu-id="2fbb7-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2fbb7-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2fbb7-118">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2fbb7-118">None.</span></span> <span data-ttu-id="2fbb7-119">O Reset-CcCACertificate cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="2fbb7-119">The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2fbb7-120">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="2fbb7-120">Return Types</span></span>
<span data-ttu-id="2fbb7-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2fbb7-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2fbb7-122">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2fbb7-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2fbb7-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="2fbb7-123">See also</span></span>
<span data-ttu-id="2fbb7-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2fbb7-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2fbb7-125">[Renew-CcCACertificate](renew-cccacertificate.md) Somente a versão 1.4.2</span><span class="sxs-lookup"><span data-stu-id="2fbb7-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="2fbb7-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Somente a versão 1.4.2</span><span class="sxs-lookup"><span data-stu-id="2fbb7-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="2fbb7-127">[Update-CcCACertificate](update-cccacertificate.md) Versão 2.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="2fbb7-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="2fbb7-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Versão 2.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="2fbb7-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="2fbb7-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="2fbb7-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

