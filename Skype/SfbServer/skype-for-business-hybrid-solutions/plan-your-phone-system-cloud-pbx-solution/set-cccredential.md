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
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'O cmdlet Set-CcCredential define a credencial da implantação atual do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: bcb88f11fb78d995e6d8271593c2e09bb0b11d22
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003211"
---
# <a name="set-cccredential"></a><span data-ttu-id="86e1f-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="86e1f-103">Set-CcCredential</span></span>
 
<span data-ttu-id="86e1f-104">O cmdlet Set-CcCredential define a credencial da implantação atual do Skype for Business Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="86e1f-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="86e1f-105">Com o Cloud Connector versão 2,0 e posterior, esse cmdlet também pode definir as informações da conta para o administrador da máquina virtual e para o administrador do domínio.</span><span class="sxs-lookup"><span data-stu-id="86e1f-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="86e1f-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="86e1f-106">Examples</span></span>
<span data-ttu-id="86e1f-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="86e1f-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="86e1f-108">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="86e1f-108">Example 1</span></span>

<span data-ttu-id="86e1f-109">O exemplo a seguir especifica o nome e a senha da conta do administrador do locatário:</span><span class="sxs-lookup"><span data-stu-id="86e1f-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="86e1f-110">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="86e1f-110">Detailed Description</span></span>
<span data-ttu-id="86e1f-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="86e1f-111"></span></span>

<span data-ttu-id="86e1f-112">O cmdlet Set-CcCredential define o nome da conta e a senha para o administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="86e1f-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="86e1f-113">Para versões anteriores à 2.0, o administrador deve ser um Administrador Global do Office 365.</span><span class="sxs-lookup"><span data-stu-id="86e1f-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="86e1f-114">O Cloud Connector usa essa conta para obter informações de configuração, definir parâmetros de configuração e atualizar o status do aparelho para a configuração do locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="86e1f-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="86e1f-115">Com a versão 2,0 e posterior, você também pode usar esse cmdlet para atualizar as senhas das contas VmAdmin e DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="86e1f-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="86e1f-116">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="86e1f-116">Parameters</span></span>
<span data-ttu-id="86e1f-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="86e1f-117"></span></span>

|<span data-ttu-id="86e1f-118">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="86e1f-118">**Parameter**</span></span>|<span data-ttu-id="86e1f-119">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="86e1f-119">**Required**</span></span>|<span data-ttu-id="86e1f-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="86e1f-120">**Type**</span></span>|<span data-ttu-id="86e1f-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="86e1f-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="86e1f-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="86e1f-122">AccountType</span></span> <br/> | <span data-ttu-id="86e1f-123">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86e1f-123">Required</span></span> <br/> |<span data-ttu-id="86e1f-124">System.String</span><span class="sxs-lookup"><span data-stu-id="86e1f-124">System.String</span></span>  <br/> | <span data-ttu-id="86e1f-125"> O valor do parâmetro deve ser "TenantAdmin", "VmAdmin" ou "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="86e1f-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="86e1f-126">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="86e1f-126">Input Types</span></span>
<span data-ttu-id="86e1f-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="86e1f-127"></span></span>

<span data-ttu-id="86e1f-p102">Nenhum. O cmdlet Set-CcCredential não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="86e1f-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="86e1f-130">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="86e1f-130">Return Types</span></span>
<span data-ttu-id="86e1f-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="86e1f-131"></span></span>

<span data-ttu-id="86e1f-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="86e1f-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86e1f-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="86e1f-133">See also</span></span>
<span data-ttu-id="86e1f-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="86e1f-134"></span></span>

[<span data-ttu-id="86e1f-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="86e1f-135">Get-CcCredential</span></span>](get-cccredential.md)
  

