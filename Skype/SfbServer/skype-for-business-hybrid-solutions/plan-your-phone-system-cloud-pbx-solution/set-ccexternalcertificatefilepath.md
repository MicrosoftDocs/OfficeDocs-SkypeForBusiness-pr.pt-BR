---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: O Set-CcExternalCertificateFilePath cmdlet especifica o caminho onde o certificado para o Servidor de Mediação ou Servidor de Borda está armazenado.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824195"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="0381e-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0381e-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="0381e-104">O Set-CcExternalCertificateFilePath cmdlet especifica o caminho onde o certificado para o Servidor de Mediação ou Servidor de Borda está armazenado.</span><span class="sxs-lookup"><span data-stu-id="0381e-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="0381e-105">Esse certificado é necessário durante a implantação ou ao adicionar novos dispositivos do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0381e-105">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="0381e-106">O comando também permite importar um novo certificado para o Servidor de Mediação após a implantação.</span><span class="sxs-lookup"><span data-stu-id="0381e-106">The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="0381e-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="0381e-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="0381e-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0381e-108">Examples</span></span>
<span data-ttu-id="0381e-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0381e-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0381e-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0381e-110">Example 1</span></span>

<span data-ttu-id="0381e-111">O exemplo a seguir define o caminho do certificado para o Servidor de Borda:</span><span class="sxs-lookup"><span data-stu-id="0381e-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="0381e-112">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="0381e-112">Example 2</span></span>

<span data-ttu-id="0381e-113">O próximo exemplo define o caminho do certificado para o Servidor de Mediação:</span><span class="sxs-lookup"><span data-stu-id="0381e-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="0381e-114">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="0381e-114">Example 3</span></span>

<span data-ttu-id="0381e-115">O próximo exemplo atualiza o certificado para o Servidor de Mediação:</span><span class="sxs-lookup"><span data-stu-id="0381e-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="0381e-116">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="0381e-116">Detailed Description</span></span>
<span data-ttu-id="0381e-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0381e-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="0381e-118">Durante a implantação ou ao modificar a topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o certificado do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="0381e-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="0381e-119">O certificado para o Servidor de Mediação é necessário se o TLS for usado entre o (s) gateway(s) e o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="0381e-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="0381e-120">Quando você implanta um dispositivo do Cloud Connector e deseja implantar o TLS, só é possível especificar o caminho para o certificado que será implantado no Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="0381e-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="0381e-121">No entanto, se você quiser atualizar o certificado de Mediação em um dispositivo já implantado, será necessário especificar o caminho e o parâmetro -Import.</span><span class="sxs-lookup"><span data-stu-id="0381e-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="0381e-122">Para ver o caminho, use o Get-CCExternalCertificateFilePath cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0381e-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0381e-123">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0381e-123">Parameters</span></span>
<span data-ttu-id="0381e-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0381e-124"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="0381e-125">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="0381e-125">**Parameter**</span></span>|<span data-ttu-id="0381e-126">**Required**</span><span class="sxs-lookup"><span data-stu-id="0381e-126">**Required**</span></span>|<span data-ttu-id="0381e-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0381e-127">**Type**</span></span>|<span data-ttu-id="0381e-128">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0381e-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0381e-129">Target</span><span class="sxs-lookup"><span data-stu-id="0381e-129">Target</span></span> <br/> | <span data-ttu-id="0381e-130">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="0381e-130">Required</span></span> <br/> |<span data-ttu-id="0381e-131">System.String</span><span class="sxs-lookup"><span data-stu-id="0381e-131">System.String</span></span>  <br/> |<span data-ttu-id="0381e-132">Tipo de caminho de arquivo solicitado.</span><span class="sxs-lookup"><span data-stu-id="0381e-132">Type of file path requested.</span></span> <span data-ttu-id="0381e-133">Os tipos incluem:</span><span class="sxs-lookup"><span data-stu-id="0381e-133">Types include:</span></span>  <br/> <span data-ttu-id="0381e-134">EdgeServer (padrão)</span><span class="sxs-lookup"><span data-stu-id="0381e-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="0381e-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="0381e-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="0381e-136">Importar</span><span class="sxs-lookup"><span data-stu-id="0381e-136">Import</span></span>  <br/> |<span data-ttu-id="0381e-137">Opcional</span><span class="sxs-lookup"><span data-stu-id="0381e-137">Optional</span></span>  <br/> |<span data-ttu-id="0381e-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0381e-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0381e-139">Indica que o certificado deve ser importado para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="0381e-139">Indicates that the certificate must be imported to the Mediation Server.</span></span> <span data-ttu-id="0381e-140">Esse parâmetro não será necessário se você implantar um dispositivo pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="0381e-140">This parameter is not needed if you deploy an appliance for first time.</span></span> <span data-ttu-id="0381e-141">O parâmetro é necessário se você quiser alterar o certificado existente em uma versão já implantada.</span><span class="sxs-lookup"><span data-stu-id="0381e-141">The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0381e-142">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="0381e-142">Input Types</span></span>
<span data-ttu-id="0381e-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0381e-143"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0381e-144">O Set-CcExternalCertificateFilePath cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="0381e-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0381e-145">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="0381e-145">Return Types</span></span>
<span data-ttu-id="0381e-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0381e-146"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0381e-147">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0381e-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0381e-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="0381e-148">See also</span></span>
<span data-ttu-id="0381e-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0381e-149"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="0381e-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0381e-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

