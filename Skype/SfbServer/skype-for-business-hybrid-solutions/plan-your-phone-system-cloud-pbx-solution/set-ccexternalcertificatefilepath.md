---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: O cmdlet Set-CcExternalCertificateFilePath especifica o caminho onde o certificado para o Servidor de Mediação ou para o Servidor de Borda é armazenado.
ms.openlocfilehash: 059d0f2fbf5fee708ceccd0d6e10ad4286fe4f85
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895346"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="654f1-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="654f1-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="654f1-104">O cmdlet Set-CcExternalCertificateFilePath especifica o caminho onde o certificado para o Servidor de Mediação ou para o Servidor de Borda é armazenado.</span><span class="sxs-lookup"><span data-stu-id="654f1-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="654f1-p101">Este certificado é necessário durante a implantação ou adição de novos dispositivos do Skype for Business Cloud Connector Edition. O comando também permite a importação de um novo certificado para o Servidor de Mediação após a implantação.</span><span class="sxs-lookup"><span data-stu-id="654f1-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="654f1-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1 e 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="654f1-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="654f1-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="654f1-108">Examples</span></span>
<span data-ttu-id="654f1-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="654f1-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="654f1-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="654f1-110">Example 1</span></span>

<span data-ttu-id="654f1-111">O seguinte exemplo mostra o caminho do certificado para o Servidor de Borda:</span><span class="sxs-lookup"><span data-stu-id="654f1-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="654f1-112">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="654f1-112">Example 2</span></span>

<span data-ttu-id="654f1-113">O exemplo seguinte define o caminho do certificado para o Servidor de Mediação:</span><span class="sxs-lookup"><span data-stu-id="654f1-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="654f1-114">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="654f1-114">Example 3</span></span>

<span data-ttu-id="654f1-115">O exemplo seguinte atualiza o certificado do Servidor de Mediação:</span><span class="sxs-lookup"><span data-stu-id="654f1-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="654f1-116">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="654f1-116">Detailed Description</span></span>
<span data-ttu-id="654f1-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="654f1-117"></span></span>

<span data-ttu-id="654f1-118">Durante a implantação ou ao modificar a topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o certificado do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="654f1-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="654f1-119">O certificado do Servidor de Mediação será necessário se o TLS for usado entre os gateways e o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="654f1-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="654f1-120">Quando você implantar um aparelho de conector de nuvem e deseja implantar o TLS, você pode apenas especificar o caminho para o certificado que será implantado no servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="654f1-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="654f1-121">No entanto, se você desejar atualizar o certificado de mediação em um dispositivo já implantado, você deve especificar o caminho e o parâmetro -Import.</span><span class="sxs-lookup"><span data-stu-id="654f1-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="654f1-122">Para ver o caminho, use o cmdlet Get-CCExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="654f1-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="654f1-123">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="654f1-123">Parameters</span></span>
<span data-ttu-id="654f1-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="654f1-124"></span></span>

|<span data-ttu-id="654f1-125">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="654f1-125">**Parameter**</span></span>|<span data-ttu-id="654f1-126">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="654f1-126">**Required**</span></span>|<span data-ttu-id="654f1-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="654f1-127">**Type**</span></span>|<span data-ttu-id="654f1-128">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="654f1-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="654f1-129">Destino </span><span class="sxs-lookup"><span data-stu-id="654f1-129">Target</span></span> <br/> | <span data-ttu-id="654f1-130">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="654f1-130">Required</span></span> <br/> |<span data-ttu-id="654f1-131">System.String</span><span class="sxs-lookup"><span data-stu-id="654f1-131">System.String</span></span>  <br/> |<span data-ttu-id="654f1-p103">Digite o caminho do arquivo solicitado. Os tipos incluem:</span><span class="sxs-lookup"><span data-stu-id="654f1-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="654f1-134">EdgeServer (padrão)</span><span class="sxs-lookup"><span data-stu-id="654f1-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="654f1-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="654f1-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="654f1-136">Importar</span><span class="sxs-lookup"><span data-stu-id="654f1-136">Import</span></span>  <br/> |<span data-ttu-id="654f1-137">Opcional</span><span class="sxs-lookup"><span data-stu-id="654f1-137">Optional</span></span>  <br/> |<span data-ttu-id="654f1-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="654f1-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="654f1-p104">Indica que o certificado deve ser importado para o Servidor de Mediação. Este parâmetro não será necessário se você implantar um dispositivo pela primeira vez. O parâmetro será necessário se você desejar alterar o certificado existente em uma versão já implantada.</span><span class="sxs-lookup"><span data-stu-id="654f1-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="654f1-142">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="654f1-142">Input Types</span></span>
<span data-ttu-id="654f1-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="654f1-143"></span></span>

<span data-ttu-id="654f1-144">O cmdlet Set-CcExternalCertificateFilePath não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="654f1-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="654f1-145">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="654f1-145">Return Types</span></span>
<span data-ttu-id="654f1-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="654f1-146"></span></span>

<span data-ttu-id="654f1-147">Nenhum</span><span class="sxs-lookup"><span data-stu-id="654f1-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="654f1-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="654f1-148">See also</span></span>
<span data-ttu-id="654f1-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="654f1-149"></span></span>

[<span data-ttu-id="654f1-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="654f1-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

