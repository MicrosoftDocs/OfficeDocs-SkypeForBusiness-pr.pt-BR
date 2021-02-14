---
title: Get-CcSiteDirectory
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
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: O Get-CcSiteDirectory cmdlet mostra o diretório atual onde os arquivos de configuração no nível do site são armazenados. A pasta contém o VHD base e os arquivos de instalação do Skype for Business Cloud Connector Edition. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do Cloud Connector.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799861"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="0e47b-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="0e47b-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="0e47b-106">O Get-CcSiteDirectory cmdlet mostra o diretório atual onde os arquivos de configuração no nível do site são armazenados.</span><span class="sxs-lookup"><span data-stu-id="0e47b-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="0e47b-107">A pasta contém o VHD base e os arquivos de instalação do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0e47b-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="0e47b-108">Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0e47b-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="0e47b-109">Este cmdlet se aplica ao Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="0e47b-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="0e47b-110">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0e47b-110">Parameters</span></span>

<span data-ttu-id="0e47b-111">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0e47b-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="0e47b-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0e47b-112">Examples</span></span>
<span data-ttu-id="0e47b-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e47b-113"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0e47b-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0e47b-114">Example 1</span></span>

<span data-ttu-id="0e47b-115">O exemplo a seguir mostra a pasta atual onde os arquivos de configuração e máquinas virtuais dos componentes do Cloud Connector são armazenados:</span><span class="sxs-lookup"><span data-stu-id="0e47b-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="0e47b-116">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="0e47b-116">Detailed Description</span></span>
<span data-ttu-id="0e47b-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0e47b-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="0e47b-118">Para fornecer afinidade de gateway e alta disponibilidade, os dispositivos do Cloud Connector podem ser combinados em sites.</span><span class="sxs-lookup"><span data-stu-id="0e47b-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="0e47b-119">Os usuários são atribuídos a sites em vez de dispositivos do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0e47b-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="0e47b-120">Cada site tem uma pasta compartilhada onde os arquivos de instalação base do VHD e do Cloud Connector são armazenados.</span><span class="sxs-lookup"><span data-stu-id="0e47b-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="0e47b-121">Os dispositivos usam essa pasta durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="0e47b-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="0e47b-122">A pasta padrão é C:\Users \% userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="0e47b-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="0e47b-123">Você pode alterar o caminho usando o Set-CcSiteDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e47b-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="0e47b-124">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="0e47b-124">Input Types</span></span>
<span data-ttu-id="0e47b-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e47b-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0e47b-126">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0e47b-126">None.</span></span> <span data-ttu-id="0e47b-127">O Get-CcSiteDirectory cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="0e47b-127">The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0e47b-128">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="0e47b-128">Return Types</span></span>
<span data-ttu-id="0e47b-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e47b-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0e47b-130">Este comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="0e47b-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e47b-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="0e47b-131">See also</span></span>
<span data-ttu-id="0e47b-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e47b-132"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="0e47b-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="0e47b-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

