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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: O Renew-CcServerCertificate cmdlet renova os certificados para o Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram. Esse comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824257"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="2feaf-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="2feaf-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="2feaf-105">O Renew-CcServerCertificate cmdlet renova os certificados para o Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram.</span><span class="sxs-lookup"><span data-stu-id="2feaf-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="2feaf-106">Esse comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="2feaf-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="2feaf-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2feaf-107">Examples</span></span>
<span data-ttu-id="2feaf-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2feaf-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2feaf-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2feaf-109">Example 1</span></span>

<span data-ttu-id="2feaf-110">O exemplo a seguir renova os certificados para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando os certificados estão próximos de expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="2feaf-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="2feaf-111">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="2feaf-111">Example 2</span></span>

<span data-ttu-id="2feaf-112">O próximo exemplo renova os certificados para o Servidor de Mediação e o Servidor de Borda quando eles estão próximos de expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="2feaf-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="2feaf-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="2feaf-113">Detailed Description</span></span>
<span data-ttu-id="2feaf-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2feaf-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2feaf-115">Os certificados internos do Cloud Connector emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos após a emissão de um serviço de Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="2feaf-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="2feaf-116">Se os certificados estão próximos de expirar ou já expiraram, execute o cmdlet Renew-CcServerCertificate para renovar os certificados.</span><span class="sxs-lookup"><span data-stu-id="2feaf-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="2feaf-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2feaf-117">Parameters</span></span>
<span data-ttu-id="2feaf-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2feaf-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="2feaf-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="2feaf-119">**Parameter**</span></span>|<span data-ttu-id="2feaf-120">**Required**</span><span class="sxs-lookup"><span data-stu-id="2feaf-120">**Required**</span></span>|<span data-ttu-id="2feaf-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2feaf-121">**Type**</span></span>|<span data-ttu-id="2feaf-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2feaf-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2feaf-123">Funções</span><span class="sxs-lookup"><span data-stu-id="2feaf-123">Roles</span></span>  <br/> |<span data-ttu-id="2feaf-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="2feaf-124">Optional</span></span>  <br/> |<span data-ttu-id="2feaf-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="2feaf-125">System.Array</span></span>  <br/> | <span data-ttu-id="2feaf-126">Matriz de funções de servidor do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2feaf-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2feaf-127">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="2feaf-127">Input Types</span></span>
<span data-ttu-id="2feaf-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2feaf-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2feaf-129">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2feaf-129">None.</span></span> <span data-ttu-id="2feaf-130">O Renew-CcServerCertificate cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="2feaf-130">The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2feaf-131">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="2feaf-131">Return Types</span></span>
<span data-ttu-id="2feaf-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2feaf-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2feaf-133">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2feaf-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2feaf-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="2feaf-134">See also</span></span>
<span data-ttu-id="2feaf-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2feaf-135"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="2feaf-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="2feaf-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="2feaf-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="2feaf-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="2feaf-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="2feaf-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

