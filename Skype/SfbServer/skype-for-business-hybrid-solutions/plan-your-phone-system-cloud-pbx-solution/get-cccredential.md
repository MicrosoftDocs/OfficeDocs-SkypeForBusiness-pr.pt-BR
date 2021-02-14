---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: O Get-CcCredential cmdlet retorna a credencial da implantação atual do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: c4e2d47ffc31eb7afef76c710fc93024ce2c593e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800391"
---
# <a name="get-cccredential"></a><span data-ttu-id="334dc-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="334dc-103">Get-CcCredential</span></span>
 
<span data-ttu-id="334dc-104">O Get-CcCredential cmdlet retorna a credencial da implantação atual do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="334dc-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="334dc-105">Com a versão 2.0 e posterior, você também pode usar o parâmetro -DisplayPassword para mostrar as senhas de TenantAdmin, DomainAdmin e VMAdmin.</span><span class="sxs-lookup"><span data-stu-id="334dc-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="334dc-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="334dc-106">Examples</span></span>
<span data-ttu-id="334dc-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="334dc-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="334dc-108">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="334dc-108">Example 1</span></span>

<span data-ttu-id="334dc-109">O exemplo a seguir retorna a credencial do administrador de domínio do domínio da máquina virtual do Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="334dc-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="334dc-110">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="334dc-110">Detailed Description</span></span>
<span data-ttu-id="334dc-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="334dc-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="334dc-112">O Get-CcCredential cmdlet retorna as informações de credencial sobre o tipo de conta especificado.</span><span class="sxs-lookup"><span data-stu-id="334dc-112">The Get-CcCredential cmdlet returns the credential information about the specified account type.</span></span> <span data-ttu-id="334dc-113">Essas credenciais são especificadas pelo administrador que executa os cmdlets Register-CcAppliance e Install-CcAppliance ao implantar o dispositivo atual.</span><span class="sxs-lookup"><span data-stu-id="334dc-113">These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="334dc-114">O Get-CcCredential cmdlet retorna uma instância do objeto System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="334dc-114">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span> <span data-ttu-id="334dc-115">A propriedade de senha do objeto de retorno é System.Security.SecureString.</span><span class="sxs-lookup"><span data-stu-id="334dc-115">The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="334dc-116">Se você quiser obter o texto claro da senha do administrador do domínio, certifique-se de que a senha seja a entrada da conta de logon atual no servidor host e abra um console do PowerShell como administrador e execute o script abaixo:</span><span class="sxs-lookup"><span data-stu-id="334dc-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="334dc-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="334dc-117">Parameters</span></span>
<span data-ttu-id="334dc-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="334dc-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="334dc-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="334dc-119">**Parameter**</span></span>|<span data-ttu-id="334dc-120">**Required**</span><span class="sxs-lookup"><span data-stu-id="334dc-120">**Required**</span></span>|<span data-ttu-id="334dc-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="334dc-121">**Type**</span></span>|<span data-ttu-id="334dc-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="334dc-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="334dc-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="334dc-123">AccountType</span></span> <br/> |<span data-ttu-id="334dc-124">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="334dc-124">Required</span></span>  <br/> | <span data-ttu-id="334dc-125">System.String</span><span class="sxs-lookup"><span data-stu-id="334dc-125">System.String</span></span> <br/> | <span data-ttu-id="334dc-126">O valor accountType pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="334dc-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="334dc-127">VmAdmin: o administrador local das máquinas virtuais do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="334dc-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="334dc-128">DomainAdmin: Administrador de domínio do domínio da máquina virtual do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="334dc-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="334dc-129">SafeModeAdmin: SafeModeAdmin do controlador de domínio da máquina virtual do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="334dc-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="334dc-130">ExternalCert: conta do certificado externo instalado no Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="334dc-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="334dc-131">TenantAdmin: Administrador do locatário do O365.</span><span class="sxs-lookup"><span data-stu-id="334dc-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="334dc-132">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="334dc-132">Input Types</span></span>
<span data-ttu-id="334dc-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="334dc-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="334dc-134">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="334dc-134">None.</span></span> <span data-ttu-id="334dc-135">O Get-CcCredential cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="334dc-135">The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="334dc-136">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="334dc-136">Return Types</span></span>
<span data-ttu-id="334dc-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="334dc-137"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="334dc-138">O Get-CcCredential cmdlet retorna uma instância do objeto System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="334dc-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="334dc-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="334dc-139">See also</span></span>
<span data-ttu-id="334dc-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="334dc-140"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="334dc-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="334dc-141">Set-CcCredential</span></span>](set-cccredential.md)
  

