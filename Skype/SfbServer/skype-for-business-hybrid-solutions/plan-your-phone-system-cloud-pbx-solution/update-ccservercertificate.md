---
title: Update-CcServerCertificate
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
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: O Update-CcServerCertificate cmdlet renova os certificados para o Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram.
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824105"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="c48cb-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="c48cb-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="c48cb-104">O Update-CcServerCertificate cmdlet renova os certificados para o Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram.</span><span class="sxs-lookup"><span data-stu-id="c48cb-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="c48cb-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="c48cb-105">Examples</span></span>
<span data-ttu-id="c48cb-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c48cb-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c48cb-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="c48cb-107">Example 1</span></span>

<span data-ttu-id="c48cb-108">O exemplo a seguir renova os certificados para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando os certificados estão próximos de expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="c48cb-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="c48cb-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="c48cb-109">Example 2</span></span>

<span data-ttu-id="c48cb-110">O próximo exemplo renova os certificados para o Servidor de Mediação e o Servidor de Borda quando eles estão próximos de expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="c48cb-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="c48cb-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="c48cb-111">Detailed Description</span></span>
<span data-ttu-id="c48cb-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c48cb-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c48cb-113">Os certificados internos do Cloud Connector emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos após a emissão de um serviço de Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="c48cb-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="c48cb-114">Se os certificados estão próximos de expirar ou já expiraram, execute o cmdlet Update-CcServerCertificate para renovar os certificados.</span><span class="sxs-lookup"><span data-stu-id="c48cb-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="c48cb-115">Este comando substitui o Renew-CcServerCertificate cmdlet no Cloud Connector 2.0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="c48cb-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c48cb-116">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c48cb-116">Parameters</span></span>
<span data-ttu-id="c48cb-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c48cb-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c48cb-118">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="c48cb-118">**Parameter**</span></span>|<span data-ttu-id="c48cb-119">**Required**</span><span class="sxs-lookup"><span data-stu-id="c48cb-119">**Required**</span></span>|<span data-ttu-id="c48cb-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c48cb-120">**Type**</span></span>|<span data-ttu-id="c48cb-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c48cb-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c48cb-122">Funções</span><span class="sxs-lookup"><span data-stu-id="c48cb-122">Roles</span></span>  <br/> |<span data-ttu-id="c48cb-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="c48cb-123">Optional</span></span>  <br/> |<span data-ttu-id="c48cb-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="c48cb-124">System.Array</span></span>  <br/> | <span data-ttu-id="c48cb-125">Matriz de funções de servidor do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c48cb-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c48cb-126">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="c48cb-126">Input Types</span></span>
<span data-ttu-id="c48cb-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c48cb-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c48cb-128">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c48cb-128">None.</span></span> <span data-ttu-id="c48cb-129">O Update-CcServerCertificate cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="c48cb-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c48cb-130">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="c48cb-130">Return Types</span></span>
<span data-ttu-id="c48cb-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c48cb-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c48cb-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c48cb-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c48cb-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="c48cb-133">See also</span></span>
<span data-ttu-id="c48cb-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c48cb-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c48cb-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="c48cb-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="c48cb-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="c48cb-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="c48cb-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="c48cb-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

