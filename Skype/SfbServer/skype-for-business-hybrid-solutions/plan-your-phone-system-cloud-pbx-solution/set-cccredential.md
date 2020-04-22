---
title: Set-CcCredential
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
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: O cmdlet Set-CcCredential define a credencial da implantação atual do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: a97d85ef6fec31383b349e9a0c3b3d9e25d04337
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780670"
---
# <a name="set-cccredential"></a><span data-ttu-id="0b8b4-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="0b8b4-103">Set-CcCredential</span></span>
 
<span data-ttu-id="0b8b4-104">O cmdlet Set-CcCredential define a credencial da implantação atual do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0b8b4-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="0b8b4-105">Com o Cloud Connector versão 2,0 e posterior, este cmdlet também pode definir as informações da conta para o administrador da máquina virtual e para o administrador do domínio.</span><span class="sxs-lookup"><span data-stu-id="0b8b4-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="0b8b4-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0b8b4-106">Examples</span></span>
<span data-ttu-id="0b8b4-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0b8b4-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0b8b4-108">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0b8b4-108">Example 1</span></span>

<span data-ttu-id="0b8b4-109">O exemplo a seguir especifica o nome da conta e a senha do administrador do locatário:</span><span class="sxs-lookup"><span data-stu-id="0b8b4-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="0b8b4-110">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="0b8b4-110">Detailed Description</span></span>
<span data-ttu-id="0b8b4-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0b8b4-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="0b8b4-112">O cmdlet Set-CcCredential define o nome da conta e a senha do administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="0b8b4-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="0b8b4-113">Para versões anteriores a 2,0, esse administrador deve ser um administrador global.</span><span class="sxs-lookup"><span data-stu-id="0b8b4-113">For releases prior to 2.0, this administrator must be a Global Administrator.</span></span> <span data-ttu-id="0b8b4-114">O Cloud Connector usa essa conta para obter informações de configuração, definir parâmetros de configuração e atualizar o status do dispositivo para a configuração da organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0b8b4-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 organization configuration.</span></span> <span data-ttu-id="0b8b4-115">Com a versão 2,0 e posterior, você também pode usar esse cmdlet para atualizar as senhas das contas VmAdmin e DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="0b8b4-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0b8b4-116">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0b8b4-116">Parameters</span></span>
<span data-ttu-id="0b8b4-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0b8b4-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="0b8b4-118">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="0b8b4-118">**Parameter**</span></span>|<span data-ttu-id="0b8b4-119">**Required**</span><span class="sxs-lookup"><span data-stu-id="0b8b4-119">**Required**</span></span>|<span data-ttu-id="0b8b4-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0b8b4-120">**Type**</span></span>|<span data-ttu-id="0b8b4-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0b8b4-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0b8b4-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="0b8b4-122">AccountType</span></span> <br/> | <span data-ttu-id="0b8b4-123">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="0b8b4-123">Required</span></span> <br/> |<span data-ttu-id="0b8b4-124">System. String</span><span class="sxs-lookup"><span data-stu-id="0b8b4-124">System.String</span></span>  <br/> | <span data-ttu-id="0b8b4-125">O valor do parâmetro deve ser "TenantAdmin", "VmAdmin" ou "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="0b8b4-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0b8b4-126">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="0b8b4-126">Input Types</span></span>
<span data-ttu-id="0b8b4-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0b8b4-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0b8b4-128">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0b8b4-128">None.</span></span> <span data-ttu-id="0b8b4-129">O cmdlet Set-CcCredential não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="0b8b4-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0b8b4-130">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="0b8b4-130">Return Types</span></span>
<span data-ttu-id="0b8b4-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0b8b4-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0b8b4-132">None</span><span class="sxs-lookup"><span data-stu-id="0b8b4-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b8b4-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="0b8b4-133">See also</span></span>
<span data-ttu-id="0b8b4-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0b8b4-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="0b8b4-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="0b8b4-135">Get-CcCredential</span></span>](get-cccredential.md)
  

