---
title: Remove-CcLegacyServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: O cmdlet Remove-CcLegacyServerCertificate remove os certificados do servidor herdados do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda depois que você executa os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: f23a753df1a5c9f81b81bc0f1d7d33c01020b489
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="f7722-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f7722-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="f7722-104">O cmdlet Remove-CcLegacyServerCertificate remove os certificados do servidor herdados do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda depois que você executa os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="f7722-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="f7722-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f7722-105">Examples</span></span>
<span data-ttu-id="f7722-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f7722-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="f7722-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="f7722-107">Example 1</span></span>

<span data-ttu-id="f7722-108">O exemplo seguinte remove os certificados herdados emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda depois de você renovar os certificados:</span><span class="sxs-lookup"><span data-stu-id="f7722-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="f7722-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="f7722-109">Example 2</span></span>

<span data-ttu-id="f7722-110">O exemplo seguinte remove os certificados emitidos para o Servidor de Mediação e o Servidor de Borda depois de você renovar os certificados: </span><span class="sxs-lookup"><span data-stu-id="f7722-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 

```

## <a name="parameters"></a><span data-ttu-id="f7722-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f7722-111">Parameters</span></span>
<span data-ttu-id="f7722-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f7722-112"></span></span>

|<span data-ttu-id="f7722-113">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="f7722-113">**Parameter**</span></span>|<span data-ttu-id="f7722-114">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="f7722-114">**Required**</span></span>|<span data-ttu-id="f7722-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f7722-115">**Type**</span></span>|<span data-ttu-id="f7722-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f7722-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f7722-117">Funções</span><span class="sxs-lookup"><span data-stu-id="f7722-117">Roles</span></span> <br/> |<span data-ttu-id="f7722-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="f7722-118">Optional</span></span>  <br/> |<span data-ttu-id="f7722-119">System. Array</span><span class="sxs-lookup"><span data-stu-id="f7722-119">System.Array</span></span>  <br/> | <span data-ttu-id="f7722-120">Matriz das funções do servidor do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f7722-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f7722-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f7722-121">Input Types</span></span>
<span data-ttu-id="f7722-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f7722-122"></span></span>

<span data-ttu-id="f7722-p101">Nenhum. O cmdlet Remove-CcLegacyServerCertificate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="f7722-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f7722-125">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="f7722-125">Return Types</span></span>
<span data-ttu-id="f7722-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f7722-126"></span></span>

<span data-ttu-id="f7722-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f7722-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7722-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f7722-128">See also</span></span>
<span data-ttu-id="f7722-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f7722-129"></span></span>

[<span data-ttu-id="f7722-130">Renovar-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f7722-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="f7722-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f7722-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="f7722-132">Renovar-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f7722-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="f7722-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f7722-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

