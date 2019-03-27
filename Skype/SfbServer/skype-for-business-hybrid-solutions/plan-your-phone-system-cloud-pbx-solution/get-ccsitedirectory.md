---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: O cmdlet Get-CcSiteDirectory mostra o diretório atual em que os arquivos de configuração no nível do site estão armazenados. A pasta contém o VHD de base e os arquivos de instalação do Skype for Business Cloud Connector Edition. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do conector de nuvem.
ms.openlocfilehash: d0869f3cbd1c43e523107a0ff8dce6fd769889a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882394"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="8d895-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="8d895-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="8d895-106">O cmdlet Get-CcSiteDirectory mostra o diretório atual em que os arquivos de configuração no nível do site estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="8d895-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="8d895-107">A pasta contém o VHD de base e os arquivos de instalação do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="8d895-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="8d895-108">Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="8d895-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="8d895-109">Este cmdlet se aplica ao Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="8d895-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="8d895-110">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8d895-110">Parameters</span></span>

<span data-ttu-id="8d895-111">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8d895-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8d895-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="8d895-112">Examples</span></span>
<span data-ttu-id="8d895-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8d895-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="8d895-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="8d895-114">Example 1</span></span>

<span data-ttu-id="8d895-115">O exemplo a seguir mostra a pasta atual, onde os arquivos de configuração e máquinas virtuais dos componentes do conector de nuvem são armazenados:</span><span class="sxs-lookup"><span data-stu-id="8d895-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="8d895-116">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="8d895-116">Detailed Description</span></span>
<span data-ttu-id="8d895-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8d895-117"></span></span>

<span data-ttu-id="8d895-118">Para fornecer alta disponibilidade e a afinidade de gateway, aparelhos de conector de nuvem podem ser combinados em sites.</span><span class="sxs-lookup"><span data-stu-id="8d895-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="8d895-119">Os usuários são atribuídos a sites, em vez de aparelhos de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="8d895-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="8d895-120">Cada site possui uma pasta compartilhada onde os arquivos de instalação base do VHD e o conector de nuvem são armazenados.</span><span class="sxs-lookup"><span data-stu-id="8d895-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="8d895-121">Os dispositivos usam essa pasta durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="8d895-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="8d895-122">A pasta padrão é C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="8d895-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="8d895-123">Você pode alterar o caminho usando o cmdlet Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="8d895-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8d895-124">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="8d895-124">Input Types</span></span>
<span data-ttu-id="8d895-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8d895-125"></span></span>

<span data-ttu-id="8d895-p104">Nenhum. O cmdlet Get-CcSiteDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="8d895-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8d895-128">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="8d895-128">Return Types</span></span>
<span data-ttu-id="8d895-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8d895-129"></span></span>

<span data-ttu-id="8d895-130">Este comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="8d895-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8d895-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8d895-131">See also</span></span>
<span data-ttu-id="8d895-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8d895-132"></span></span>

[<span data-ttu-id="8d895-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="8d895-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

