---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: 'O cmdlet Get-CcCredential retorna a credencial da implantação atual do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: 651190f31ad44e0bb2375bbf4a70951c2011e1a7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233992"
---
# <a name="get-cccredential"></a><span data-ttu-id="836a9-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="836a9-103">Get-CcCredential</span></span>
 
<span data-ttu-id="836a9-104">O cmdlet Get-CcCredential retorna a credencial da implantação atual do Skype for Business Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="836a9-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="836a9-105">Com a versão 2.0 e posterior, você também pode usar o parâmetro - DisplayPassword para mostrar as senhas para TenantAdmin, DomainAdmin e VMAdmin.</span><span class="sxs-lookup"><span data-stu-id="836a9-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="836a9-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="836a9-106">Examples</span></span>
<span data-ttu-id="836a9-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="836a9-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="836a9-108">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="836a9-108">Example 1</span></span>

<span data-ttu-id="836a9-109">O exemplo seguinte retorna a credencial do administrador do domínio da máquina virtual do Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="836a9-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="836a9-110">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="836a9-110">Detailed Description</span></span>
<span data-ttu-id="836a9-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="836a9-111"></span></span>

<span data-ttu-id="836a9-p101">O cmdlet Get-CcCredential retorna as informações de credencial sobre o tipo de conta especificado. Essas credenciais são especificadas pelo administrador que executa os cmdlets Register-CcAppliance e Install-CcAppliance ao implantar o dispositivo atual. </span><span class="sxs-lookup"><span data-stu-id="836a9-p101">The Get-CcCredential cmdlet returns the credential information about the specified account type. These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="836a9-p102">O cmdlet Get-CcCredential retorna instâncias do objeto System.Management.Automation.PSCredential. A propriedade da senha do objeto de retorno é o System.Security.SecureString.</span><span class="sxs-lookup"><span data-stu-id="836a9-p102">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object. The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="836a9-116">Se você deseja obter o texto claro da senha do administrador de domínio, verifique se a senha foi inserida pela conta de logon atual no servidor host e, em seguida, abra o console do PowerShell como administrador e execute o script a seguir:</span><span class="sxs-lookup"><span data-stu-id="836a9-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="836a9-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="836a9-117">Parameters</span></span>
<span data-ttu-id="836a9-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="836a9-118"></span></span>

|<span data-ttu-id="836a9-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="836a9-119">**Parameter**</span></span>|<span data-ttu-id="836a9-120">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="836a9-120">**Required**</span></span>|<span data-ttu-id="836a9-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="836a9-121">**Type**</span></span>|<span data-ttu-id="836a9-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="836a9-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="836a9-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="836a9-123">AccountType</span></span> <br/> |<span data-ttu-id="836a9-124">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="836a9-124">Required</span></span>  <br/> | <span data-ttu-id="836a9-125">System.String</span><span class="sxs-lookup"><span data-stu-id="836a9-125">System.String</span></span> <br/> | <span data-ttu-id="836a9-126">O valor AccountType pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="836a9-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="836a9-127">VmAdmin: o administrador local de máquinas virtuais do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="836a9-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="836a9-128">DomainAdmin: o administrador de domínio da máquina virtual do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="836a9-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="836a9-129">SafeModeAdmin: o SafeModeAdmin do controlador de domínio da máquina virtual do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="836a9-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="836a9-130">ExternalCert: conta do certificado externo instalado no Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="836a9-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="836a9-131">TenantAdmin: administrador do locatário do O365.</span><span class="sxs-lookup"><span data-stu-id="836a9-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="836a9-132">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="836a9-132">Input Types</span></span>
<span data-ttu-id="836a9-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="836a9-133"></span></span>

<span data-ttu-id="836a9-p103">Nenhum. O cmdlet Get-CcCredential não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="836a9-p103">None. The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="836a9-136">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="836a9-136">Return Types</span></span>
<span data-ttu-id="836a9-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="836a9-137"></span></span>

<span data-ttu-id="836a9-138">O cmdlet Get-CcCredential retorna instâncias do objeto System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="836a9-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="836a9-139">Consulte também</span><span class="sxs-lookup"><span data-stu-id="836a9-139">See also</span></span>
<span data-ttu-id="836a9-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="836a9-140"></span></span>

[<span data-ttu-id="836a9-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="836a9-141">Set-CcCredential</span></span>](set-cccredential.md)
  

