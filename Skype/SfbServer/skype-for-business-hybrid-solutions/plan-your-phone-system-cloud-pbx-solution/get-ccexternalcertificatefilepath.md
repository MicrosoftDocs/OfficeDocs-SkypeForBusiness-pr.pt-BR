---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: O cmdlet Get-CcExternalCertificateFilePath retorna o caminho do arquivo do certificado externo para a implantação do Skype for Business Cloud Connector Edition. O usuário prepara este certificado.
ms.openlocfilehash: ed725814380741aade73166d01025650dfa78538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287318"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="50b3a-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="50b3a-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="50b3a-p102">O cmdlet Get-CcExternalCertificateFilePath retorna o caminho do arquivo do certificado externo para a implantação do Skype for Business Cloud Connector Edition. O usuário prepara este certificado.</span><span class="sxs-lookup"><span data-stu-id="50b3a-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="50b3a-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="50b3a-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="50b3a-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="50b3a-108">Examples</span></span>
<span data-ttu-id="50b3a-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="50b3a-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="50b3a-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="50b3a-110">Example 1</span></span>

<span data-ttu-id="50b3a-111">O seguinte exemplo mostra o caminho do certificado para o Servidor de Borda:</span><span class="sxs-lookup"><span data-stu-id="50b3a-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="50b3a-112">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="50b3a-112">Example 2</span></span>

<span data-ttu-id="50b3a-113">O seguinte exemplo mostra o certificado definido para o Servidor de Mediação:</span><span class="sxs-lookup"><span data-stu-id="50b3a-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="50b3a-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="50b3a-114">Detailed Description</span></span>
<span data-ttu-id="50b3a-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="50b3a-115"></span></span>

<span data-ttu-id="50b3a-p103">Durante a implantação ou ao modificar a topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o Servidor de Mediação. O certificado para o Servidor de Mediação será obrigatório se o TLS for usado entre o(s) gateway(s) e o Servidor de Mediação. Para altera o caminho, use cmdlet o Set-CcExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="50b3a-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="50b3a-119">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="50b3a-119">Parameters</span></span>
<span data-ttu-id="50b3a-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="50b3a-120"></span></span>

|<span data-ttu-id="50b3a-121">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="50b3a-121">**Parameter**</span></span>|<span data-ttu-id="50b3a-122">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="50b3a-122">**Required**</span></span>|<span data-ttu-id="50b3a-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="50b3a-123">**Type**</span></span>|<span data-ttu-id="50b3a-124">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="50b3a-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="50b3a-125">Destino </span><span class="sxs-lookup"><span data-stu-id="50b3a-125">Target</span></span>  <br/> |<span data-ttu-id="50b3a-126">Opcional</span><span class="sxs-lookup"><span data-stu-id="50b3a-126">Optional</span></span>  <br/> | <span data-ttu-id="50b3a-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="50b3a-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="50b3a-p104">Digite o caminho do arquivo solicitado. Os tipos incluem:</span><span class="sxs-lookup"><span data-stu-id="50b3a-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="50b3a-130">EdgeServer (padrão)</span><span class="sxs-lookup"><span data-stu-id="50b3a-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="50b3a-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="50b3a-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="50b3a-132">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="50b3a-132">Input Types</span></span>
<span data-ttu-id="50b3a-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50b3a-133"></span></span>

<span data-ttu-id="50b3a-134">O cmdlet Get-CcExternalCertificateFilePath não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="50b3a-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="50b3a-135">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="50b3a-135">Return Types</span></span>
<span data-ttu-id="50b3a-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50b3a-136"></span></span>

<span data-ttu-id="50b3a-137">O comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="50b3a-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50b3a-138">Consulte também</span><span class="sxs-lookup"><span data-stu-id="50b3a-138">See also</span></span>
<span data-ttu-id="50b3a-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50b3a-139"></span></span>

[<span data-ttu-id="50b3a-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="50b3a-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

