---
title: Renovar-CcServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: O cmdlet Renew-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão prestes a expirar ou já expiraram. Este comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.
ms.openlocfilehash: 3d895a24c4cc8b400aa48ce394324435cfbb3979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="a287a-104">Renovar-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="a287a-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="a287a-105">O cmdlet Renew-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão prestes a expirar ou já expiraram.</span><span class="sxs-lookup"><span data-stu-id="a287a-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="a287a-106">Este comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="a287a-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="a287a-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a287a-107">Examples</span></span>
<span data-ttu-id="a287a-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a287a-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="a287a-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="a287a-109">Example 1</span></span>

<span data-ttu-id="a287a-110">O exemplo seguinte renova os certificados para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="a287a-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="a287a-111">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="a287a-111">Example 2</span></span>

<span data-ttu-id="a287a-112">O exemplo seguinte renova os certificados para o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="a287a-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="a287a-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="a287a-113">Detailed Description</span></span>
<span data-ttu-id="a287a-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a287a-114"></span></span>

<span data-ttu-id="a287a-115">Conector de nuvem internos certificados emitidos para o repositório de gerenciamento Central, o servidor de mediação e o servidor de borda são válidas por dois anos depois que eles são emitidos a partir de um serviço de autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="a287a-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="a287a-116">Se os certificados estiverem prestes a expirar ou já expiraram, execute cmdlet Renew-CcServerCertificate para renovar os certificados.</span><span class="sxs-lookup"><span data-stu-id="a287a-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="a287a-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a287a-117">Parameters</span></span>
<span data-ttu-id="a287a-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a287a-118"></span></span>

|<span data-ttu-id="a287a-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="a287a-119">**Parameter**</span></span>|<span data-ttu-id="a287a-120">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="a287a-120">**Required**</span></span>|<span data-ttu-id="a287a-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a287a-121">**Type**</span></span>|<span data-ttu-id="a287a-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a287a-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a287a-123">Funções</span><span class="sxs-lookup"><span data-stu-id="a287a-123">Roles</span></span>  <br/> |<span data-ttu-id="a287a-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="a287a-124">Optional</span></span>  <br/> |<span data-ttu-id="a287a-125">System. Array</span><span class="sxs-lookup"><span data-stu-id="a287a-125">System.Array</span></span>  <br/> | <span data-ttu-id="a287a-126">Matriz das funções do servidor do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a287a-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a287a-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="a287a-127">Input Types</span></span>
<span data-ttu-id="a287a-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a287a-128"></span></span>

<span data-ttu-id="a287a-p104">Nenhum. O cmdlet Renew-CcServerCertificate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="a287a-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a287a-131">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="a287a-131">Return Types</span></span>
<span data-ttu-id="a287a-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a287a-132"></span></span>

<span data-ttu-id="a287a-133">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a287a-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a287a-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a287a-134">See also</span></span>
<span data-ttu-id="a287a-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a287a-135"></span></span>

[<span data-ttu-id="a287a-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="a287a-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="a287a-137">Renovar-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="a287a-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="a287a-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="a287a-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

