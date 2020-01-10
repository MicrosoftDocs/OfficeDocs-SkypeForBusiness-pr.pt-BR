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
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: O cmdlet Remove-CcLegacyServerCertificate remove os certificados do servidor herdados do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda depois que você executa os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: f22a57a3a366c621a1c035881c886190055b15e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003281"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="bdd60-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="bdd60-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="bdd60-104">O cmdlet Remove-CcLegacyServerCertificate remove os certificados do servidor herdados do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda depois que você executa os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="bdd60-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="bdd60-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="bdd60-105">Examples</span></span>
<span data-ttu-id="bdd60-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bdd60-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="bdd60-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="bdd60-107">Example 1</span></span>

<span data-ttu-id="bdd60-108">O exemplo seguinte remove os certificados herdados emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda depois de você renovar os certificados:</span><span class="sxs-lookup"><span data-stu-id="bdd60-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="bdd60-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="bdd60-109">Example 2</span></span>

<span data-ttu-id="bdd60-110">O exemplo seguinte remove os certificados emitidos para o Servidor de Mediação e o Servidor de Borda depois de você renovar os certificados: </span><span class="sxs-lookup"><span data-stu-id="bdd60-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="bdd60-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bdd60-111">Parameters</span></span>
<span data-ttu-id="bdd60-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bdd60-112"></span></span>

|<span data-ttu-id="bdd60-113">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="bdd60-113">**Parameter**</span></span>|<span data-ttu-id="bdd60-114">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="bdd60-114">**Required**</span></span>|<span data-ttu-id="bdd60-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="bdd60-115">**Type**</span></span>|<span data-ttu-id="bdd60-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bdd60-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="bdd60-117">Funções</span><span class="sxs-lookup"><span data-stu-id="bdd60-117">Roles</span></span> <br/> |<span data-ttu-id="bdd60-118">Opcional</span><span class="sxs-lookup"><span data-stu-id="bdd60-118">Optional</span></span>  <br/> |<span data-ttu-id="bdd60-119">System.Array </span><span class="sxs-lookup"><span data-stu-id="bdd60-119">System.Array</span></span>  <br/> | <span data-ttu-id="bdd60-120">Matriz das funções do servidor do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="bdd60-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="bdd60-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="bdd60-121">Input Types</span></span>
<span data-ttu-id="bdd60-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bdd60-122"></span></span>

<span data-ttu-id="bdd60-p101">Nenhum. O cmdlet Remove-CcLegacyServerCertificate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="bdd60-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bdd60-125">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="bdd60-125">Return Types</span></span>
<span data-ttu-id="bdd60-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bdd60-126"></span></span>

<span data-ttu-id="bdd60-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="bdd60-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bdd60-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bdd60-128">See also</span></span>
<span data-ttu-id="bdd60-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bdd60-129"></span></span>

[<span data-ttu-id="bdd60-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="bdd60-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="bdd60-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bdd60-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="bdd60-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bdd60-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="bdd60-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bdd60-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

