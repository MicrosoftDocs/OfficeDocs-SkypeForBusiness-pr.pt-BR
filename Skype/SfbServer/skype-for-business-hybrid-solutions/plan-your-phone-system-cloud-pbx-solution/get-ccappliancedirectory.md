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
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'O cmdlet Get-CcApplianceDirectory recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados neste diretório. '
ms.openlocfilehash: ada1b587b738d882f81557e61438d6642aa03fff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287388"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="f513a-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="f513a-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="f513a-p102">O cmdlet Get-CcApplianceDirectory recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados neste diretório. </span><span class="sxs-lookup"><span data-stu-id="f513a-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="f513a-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="f513a-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="f513a-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f513a-108">Parameters</span></span>

<span data-ttu-id="f513a-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f513a-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f513a-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f513a-110">Examples</span></span>
<span data-ttu-id="f513a-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f513a-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="f513a-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="f513a-112">Example 1</span></span>

<span data-ttu-id="f513a-113">O exemplo a seguir mostra a pasta atual na qual os arquivos de configuração e de máquina virtual dos componentes do conector de nuvem são armazenados:</span><span class="sxs-lookup"><span data-stu-id="f513a-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="f513a-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="f513a-114">Detailed Description</span></span>
<span data-ttu-id="f513a-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f513a-115"></span></span>

<span data-ttu-id="f513a-116">O cmdlet Get-CcApplianceDirectory mostra onde todos os arquivos de configuração e de máquina virtual, logs e certificados externos são armazenados para o aparelho do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="f513a-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="f513a-117">Cada dispositivo de conector de nuvem tem quatro componentes: servidor de mediação, repositório de gerenciamento central, servidor de borda e um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="f513a-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="f513a-118">A pasta padrão é C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="f513a-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="f513a-119">Você pode alterar esta pasta quando o cmdlet Set-CCApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="f513a-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f513a-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f513a-120">Input Types</span></span>
<span data-ttu-id="f513a-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f513a-121"></span></span>

<span data-ttu-id="f513a-p104">Nenhum. O cmdlet Get-CcApplianceLogDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="f513a-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f513a-124">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="f513a-124">Return Types</span></span>
<span data-ttu-id="f513a-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f513a-125"></span></span>

<span data-ttu-id="f513a-126">O comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f513a-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f513a-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f513a-127">See also</span></span>
<span data-ttu-id="f513a-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f513a-128"></span></span>

[<span data-ttu-id="f513a-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="f513a-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

