---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: O Get-CcApplianceDirectory cmdlet recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800841"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="666da-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="666da-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="666da-105">O Get-CcApplianceDirectory cmdlet recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="666da-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="666da-106">Todos os arquivos de implantação são armazenados nesse diretório.</span><span class="sxs-lookup"><span data-stu-id="666da-106">All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="666da-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="666da-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="666da-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="666da-108">Parameters</span></span>

<span data-ttu-id="666da-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="666da-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="666da-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="666da-110">Examples</span></span>
<span data-ttu-id="666da-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="666da-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="666da-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="666da-112">Example 1</span></span>

<span data-ttu-id="666da-113">O exemplo a seguir mostra a pasta atual onde os arquivos de configuração e máquina virtual dos componentes do Cloud Connector são armazenados:</span><span class="sxs-lookup"><span data-stu-id="666da-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="666da-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="666da-114">Detailed Description</span></span>
<span data-ttu-id="666da-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="666da-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="666da-116">O Get-CcApplianceDirectory cmdlet mostra onde todos os arquivos de configuração e de máquina virtual, logs e certificados externos são armazenados para o dispositivo do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="666da-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="666da-117">Cada dispositivo do Cloud Connector tem quatro componentes: Servidor de Mediação, Armazenamento de Gerenciamento Central, Servidor de Borda e um Controlador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="666da-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="666da-118">A pasta padrão é C:\Users \% userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="666da-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="666da-119">Você pode alterar essa pasta usando o Set-CCApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="666da-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="666da-120">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="666da-120">Input Types</span></span>
<span data-ttu-id="666da-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="666da-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="666da-122">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="666da-122">None.</span></span> <span data-ttu-id="666da-123">O Get-CCApplianceDirectory cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="666da-123">The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="666da-124">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="666da-124">Return Types</span></span>
<span data-ttu-id="666da-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="666da-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="666da-126">O comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="666da-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="666da-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="666da-127">See also</span></span>
<span data-ttu-id="666da-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="666da-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="666da-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="666da-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

