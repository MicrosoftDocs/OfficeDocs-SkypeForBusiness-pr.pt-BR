---
title: Remove-CcLegacyServerCertificate
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
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: O cmdlet Remove-CcLegacyServerCertificate remove certificados de servidor herdados no Armazenamento de Gerenciamento Central, no Servidor de Mediação e no Servidor de Borda depois de executar os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824277"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="2b51b-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="2b51b-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="2b51b-104">O cmdlet Remove-CcLegacyServerCertificate remove certificados de servidor herdados no Armazenamento de Gerenciamento Central, no Servidor de Mediação e no Servidor de Borda depois de executar os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="2b51b-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="2b51b-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2b51b-105">Examples</span></span>
<span data-ttu-id="2b51b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2b51b-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2b51b-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2b51b-107">Example 1</span></span>

<span data-ttu-id="2b51b-108">O exemplo a seguir remove os certificados herdados emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda após a renovação dos certificados:</span><span class="sxs-lookup"><span data-stu-id="2b51b-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="2b51b-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="2b51b-109">Example 2</span></span>

<span data-ttu-id="2b51b-110">O próximo exemplo remove os certificados emitidos para o Servidor de Mediação e o Servidor de Borda após a renovação dos certificados:</span><span class="sxs-lookup"><span data-stu-id="2b51b-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="2b51b-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2b51b-111">Parameters</span></span>
<span data-ttu-id="2b51b-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2b51b-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="2b51b-113">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="2b51b-113">**Parameter**</span></span>|<span data-ttu-id="2b51b-114">**Required**</span><span class="sxs-lookup"><span data-stu-id="2b51b-114">**Required**</span></span>|<span data-ttu-id="2b51b-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2b51b-115">**Type**</span></span>|<span data-ttu-id="2b51b-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2b51b-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2b51b-117">Funções</span><span class="sxs-lookup"><span data-stu-id="2b51b-117">Roles</span></span> <br/> |<span data-ttu-id="2b51b-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="2b51b-118">Optional</span></span>  <br/> |<span data-ttu-id="2b51b-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="2b51b-119">System.Array</span></span>  <br/> | <span data-ttu-id="2b51b-120">Matriz de funções de servidor do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2b51b-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2b51b-121">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="2b51b-121">Input Types</span></span>
<span data-ttu-id="2b51b-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2b51b-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2b51b-123">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2b51b-123">None.</span></span> <span data-ttu-id="2b51b-124">O Remove-CcLegacyServerCertificate cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="2b51b-124">The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2b51b-125">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="2b51b-125">Return Types</span></span>
<span data-ttu-id="2b51b-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2b51b-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2b51b-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2b51b-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2b51b-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="2b51b-128">See also</span></span>
<span data-ttu-id="2b51b-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2b51b-129"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="2b51b-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="2b51b-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="2b51b-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="2b51b-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="2b51b-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="2b51b-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="2b51b-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="2b51b-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

