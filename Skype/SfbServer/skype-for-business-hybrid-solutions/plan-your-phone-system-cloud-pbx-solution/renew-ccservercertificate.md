---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 'O cmdlet Renew-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão prestes a expirar ou já expiraram. Este comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores. '
ms.openlocfilehash: 47f2bbefa6510ae49e2e4a3ddc321e288dee266e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003261"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="dc3d6-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="dc3d6-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="dc3d6-p102">O cmdlet Renew-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão prestes a expirar ou já expiraram. Este comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores. </span><span class="sxs-lookup"><span data-stu-id="dc3d6-p102">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired. This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="dc3d6-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="dc3d6-107">Examples</span></span>
<span data-ttu-id="dc3d6-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3d6-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="dc3d6-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="dc3d6-109">Example 1</span></span>

<span data-ttu-id="dc3d6-110">O exemplo seguinte renova os certificados para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="dc3d6-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="dc3d6-111">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="dc3d6-111">Example 2</span></span>

<span data-ttu-id="dc3d6-112">O exemplo seguinte renova os certificados para o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="dc3d6-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="dc3d6-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="dc3d6-113">Detailed Description</span></span>
<span data-ttu-id="dc3d6-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3d6-114"></span></span>

<span data-ttu-id="dc3d6-115">Os certificados internos do conector de nuvem emitidos para o repositório de gerenciamento central, servidor de mediação e Edge Server são válidos por dois anos após serem emitidos a partir de um serviço de autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="dc3d6-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="dc3d6-116">Se os certificados estiverem prestes a expirar ou já expiraram, execute cmdlet Renew-CcServerCertificate para renovar os certificados.</span><span class="sxs-lookup"><span data-stu-id="dc3d6-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="dc3d6-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dc3d6-117">Parameters</span></span>
<span data-ttu-id="dc3d6-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3d6-118"></span></span>

|<span data-ttu-id="dc3d6-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="dc3d6-119">**Parameter**</span></span>|<span data-ttu-id="dc3d6-120">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="dc3d6-120">**Required**</span></span>|<span data-ttu-id="dc3d6-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dc3d6-121">**Type**</span></span>|<span data-ttu-id="dc3d6-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="dc3d6-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc3d6-123">Funções</span><span class="sxs-lookup"><span data-stu-id="dc3d6-123">Roles</span></span>  <br/> |<span data-ttu-id="dc3d6-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="dc3d6-124">Optional</span></span>  <br/> |<span data-ttu-id="dc3d6-125">System.Array </span><span class="sxs-lookup"><span data-stu-id="dc3d6-125">System.Array</span></span>  <br/> | <span data-ttu-id="dc3d6-126">Matriz das funções do servidor do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="dc3d6-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="dc3d6-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="dc3d6-127">Input Types</span></span>
<span data-ttu-id="dc3d6-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3d6-128"></span></span>

<span data-ttu-id="dc3d6-p104">Nenhum. O cmdlet Renew-CcServerCertificate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="dc3d6-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="dc3d6-131">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="dc3d6-131">Return Types</span></span>
<span data-ttu-id="dc3d6-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3d6-132"></span></span>

<span data-ttu-id="dc3d6-133">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc3d6-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc3d6-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc3d6-134">See also</span></span>
<span data-ttu-id="dc3d6-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3d6-135"></span></span>

[<span data-ttu-id="dc3d6-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="dc3d6-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="dc3d6-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="dc3d6-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="dc3d6-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="dc3d6-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

