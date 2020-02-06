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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: O cmdlet Get-CcExternalCertificateFilePath retorna o caminho do arquivo do certificado externo para a implantação do Skype for Business Cloud Connector Edition. O usuário prepara este certificado.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799901"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="f6b18-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="f6b18-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="f6b18-p102">O cmdlet Get-CcExternalCertificateFilePath retorna o caminho do arquivo do certificado externo para a implantação do Skype for Business Cloud Connector Edition. O usuário prepara este certificado.</span><span class="sxs-lookup"><span data-stu-id="f6b18-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="f6b18-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="f6b18-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="f6b18-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f6b18-108">Examples</span></span>
<span data-ttu-id="f6b18-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b18-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f6b18-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="f6b18-110">Example 1</span></span>

<span data-ttu-id="f6b18-111">O seguinte exemplo mostra o caminho do certificado para o Servidor de Borda:</span><span class="sxs-lookup"><span data-stu-id="f6b18-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="f6b18-112">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="f6b18-112">Example 2</span></span>

<span data-ttu-id="f6b18-113">O seguinte exemplo mostra o certificado definido para o Servidor de Mediação:</span><span class="sxs-lookup"><span data-stu-id="f6b18-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="f6b18-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="f6b18-114">Detailed Description</span></span>
<span data-ttu-id="f6b18-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b18-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="f6b18-p103">Durante a implantação ou ao modificar a topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o Servidor de Mediação. O certificado para o Servidor de Mediação será obrigatório se o TLS for usado entre o(s) gateway(s) e o Servidor de Mediação. Para altera o caminho, use cmdlet o Set-CcExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="f6b18-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f6b18-119">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f6b18-119">Parameters</span></span>
<span data-ttu-id="f6b18-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b18-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="f6b18-121">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="f6b18-121">**Parameter**</span></span>|<span data-ttu-id="f6b18-122">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="f6b18-122">**Required**</span></span>|<span data-ttu-id="f6b18-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f6b18-123">**Type**</span></span>|<span data-ttu-id="f6b18-124">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f6b18-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6b18-125">Destino </span><span class="sxs-lookup"><span data-stu-id="f6b18-125">Target</span></span>  <br/> |<span data-ttu-id="f6b18-126">Opcional</span><span class="sxs-lookup"><span data-stu-id="f6b18-126">Optional</span></span>  <br/> | <span data-ttu-id="f6b18-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f6b18-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="f6b18-p104">Digite o caminho do arquivo solicitado. Os tipos incluem:</span><span class="sxs-lookup"><span data-stu-id="f6b18-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="f6b18-130">EdgeServer (padrão)</span><span class="sxs-lookup"><span data-stu-id="f6b18-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="f6b18-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="f6b18-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f6b18-132">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f6b18-132">Input Types</span></span>
<span data-ttu-id="f6b18-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b18-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="f6b18-134">O cmdlet Get-CcExternalCertificateFilePath não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="f6b18-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f6b18-135">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="f6b18-135">Return Types</span></span>
<span data-ttu-id="f6b18-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b18-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f6b18-137">O comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f6b18-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f6b18-138">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f6b18-138">See also</span></span>
<span data-ttu-id="f6b18-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b18-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="f6b18-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="f6b18-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

