---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'O cmdlet Get-CcApplianceDirectory recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados neste diretório. '
ms.openlocfilehash: bcd80018b2286865945638f66c13e4c5198346dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891480"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="b12b4-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b12b4-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="b12b4-p102">O cmdlet Get-CcApplianceDirectory recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados neste diretório. </span><span class="sxs-lookup"><span data-stu-id="b12b4-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="b12b4-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="b12b4-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="b12b4-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b12b4-108">Parameters</span></span>

<span data-ttu-id="b12b4-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b12b4-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b12b4-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b12b4-110">Examples</span></span>
<span data-ttu-id="b12b4-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b12b4-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="b12b4-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b12b4-112">Example 1</span></span>

<span data-ttu-id="b12b4-113">O exemplo a seguir mostra a pasta atual, onde estão armazenados os arquivos de máquina virtual e configuração dos componentes do conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="b12b4-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="b12b4-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="b12b4-114">Detailed Description</span></span>
<span data-ttu-id="b12b4-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b12b4-115"></span></span>

<span data-ttu-id="b12b4-116">A cmdlet Get-CcApplianceDirectory mostra onde todos os certificados externos, logs e arquivos de configuração e a máquina virtual são armazenados para o aparelho de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b12b4-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="b12b4-117">Cada dispositivo de conector de nuvem tem quatro componentes: o servidor de mediação, repositório de gerenciamento Central, servidor de borda e um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="b12b4-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="b12b4-118">A pasta padrão é C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="b12b4-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="b12b4-119">Você pode alterar esta pasta quando o cmdlet Set-CCApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="b12b4-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b12b4-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="b12b4-120">Input Types</span></span>
<span data-ttu-id="b12b4-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b12b4-121"></span></span>

<span data-ttu-id="b12b4-p104">Nenhum. O cmdlet Get-CcApplianceLogDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="b12b4-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b12b4-124">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="b12b4-124">Return Types</span></span>
<span data-ttu-id="b12b4-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b12b4-125"></span></span>

<span data-ttu-id="b12b4-126">O comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b12b4-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b12b4-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b12b4-127">See also</span></span>
<span data-ttu-id="b12b4-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b12b4-128"></span></span>

[<span data-ttu-id="b12b4-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b12b4-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

