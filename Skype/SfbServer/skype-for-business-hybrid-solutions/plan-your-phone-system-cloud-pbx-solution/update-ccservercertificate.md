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
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 'O cmdlet Update-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão próximos de expirar ou já tiverem expirado. '
ms.openlocfilehash: 34da35e607f8941da9c962386509f8a0b87ec122
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286877"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="fc826-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="fc826-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="fc826-104">O cmdlet Update-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão próximos de expirar ou já tiverem expirado. </span><span class="sxs-lookup"><span data-stu-id="fc826-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="fc826-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="fc826-105">Examples</span></span>
<span data-ttu-id="fc826-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fc826-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="fc826-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="fc826-107">Example 1</span></span>

<span data-ttu-id="fc826-108">O exemplo seguinte renova os certificados para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="fc826-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="fc826-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="fc826-109">Example 2</span></span>

<span data-ttu-id="fc826-110">O exemplo seguinte renova os certificados para o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:</span><span class="sxs-lookup"><span data-stu-id="fc826-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="fc826-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="fc826-111">Detailed Description</span></span>
<span data-ttu-id="fc826-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fc826-112"></span></span>

<span data-ttu-id="fc826-113">Os certificados internos do conector de nuvem emitidos para o repositório de gerenciamento central, servidor de mediação e Edge Server são válidos por dois anos após serem emitidos a partir de um serviço de autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="fc826-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="fc826-114">Se os certificados estiverem próximos de expirar ou já tiverem expirado, execute o cmdlet Update-CcServerCertificate para renovar os certificados.</span><span class="sxs-lookup"><span data-stu-id="fc826-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="fc826-115">Este comando substitui o cmdlet Renew-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="fc826-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="fc826-116">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fc826-116">Parameters</span></span>
<span data-ttu-id="fc826-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fc826-117"></span></span>

|<span data-ttu-id="fc826-118">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="fc826-118">**Parameter**</span></span>|<span data-ttu-id="fc826-119">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="fc826-119">**Required**</span></span>|<span data-ttu-id="fc826-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fc826-120">**Type**</span></span>|<span data-ttu-id="fc826-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fc826-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc826-122">Funções</span><span class="sxs-lookup"><span data-stu-id="fc826-122">Roles</span></span>  <br/> |<span data-ttu-id="fc826-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="fc826-123">Optional</span></span>  <br/> |<span data-ttu-id="fc826-124">System.Array </span><span class="sxs-lookup"><span data-stu-id="fc826-124">System.Array</span></span>  <br/> | <span data-ttu-id="fc826-125">Matriz das funções do servidor do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fc826-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="fc826-126">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="fc826-126">Input Types</span></span>
<span data-ttu-id="fc826-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc826-127"></span></span>

<span data-ttu-id="fc826-p102">Nenhum. O cmdlet Update-CcServerCertificate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="fc826-p102">None. The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fc826-130">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="fc826-130">Return Types</span></span>
<span data-ttu-id="fc826-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc826-131"></span></span>

<span data-ttu-id="fc826-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fc826-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc826-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fc826-133">See also</span></span>
<span data-ttu-id="fc826-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc826-134"></span></span>

[<span data-ttu-id="fc826-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="fc826-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="fc826-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="fc826-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="fc826-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="fc826-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

