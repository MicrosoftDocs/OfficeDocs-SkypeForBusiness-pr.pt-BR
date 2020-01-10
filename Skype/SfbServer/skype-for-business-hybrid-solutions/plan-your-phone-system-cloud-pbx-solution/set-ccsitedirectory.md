---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: O cmdlet Set-CcSiteDirectory define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá o VHD de base e os arquivos de configuração do Cloud Connector.
ms.openlocfilehash: d0cc8d2a66adb831ea2d85381902eb9d3df7ba6a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003191"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="4783b-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="4783b-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="4783b-105">O cmdlet Set-CcSiteDirectory define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="4783b-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="4783b-106">A pasta conterá o VHD de base e os arquivos de configuração do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4783b-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="4783b-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4783b-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="4783b-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4783b-108">Examples</span></span>
<span data-ttu-id="4783b-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4783b-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="4783b-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="4783b-110">Example 1</span></span>

<span data-ttu-id="4783b-111">O exemplo a seguir define o diretório raiz do \\site para SiteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="4783b-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="4783b-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="4783b-112">Detailed Description</span></span>
<span data-ttu-id="4783b-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4783b-113"></span></span>

<span data-ttu-id="4783b-114">Para oferecer afinidade de gateway e alta disponibilidade, os aparelhos do Cloud Connector podem ser combinados em sites.</span><span class="sxs-lookup"><span data-stu-id="4783b-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="4783b-115">Os usuários são atribuídos a sites em vez de aparelhos de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4783b-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="4783b-116">Cada site tem uma pasta compartilhada na qual os arquivos de instalação do VHD e do conector de nuvem base estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="4783b-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="4783b-117">Os dispositivos usam essa pasta durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="4783b-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="4783b-118">Essa pasta deve ser compartilhada com todos os outros dispositivos em um site do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4783b-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="4783b-119">A pasta padrão é C:\Users\%USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="4783b-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="4783b-120">O caminho pode ser exibido por meio do cmdlet Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="4783b-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4783b-121">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4783b-121">Parameters</span></span>
<span data-ttu-id="4783b-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4783b-122"></span></span>

|<span data-ttu-id="4783b-123">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="4783b-123">**Parameter**</span></span>|<span data-ttu-id="4783b-124">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="4783b-124">**Required**</span></span>|<span data-ttu-id="4783b-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4783b-125">**Type**</span></span>|<span data-ttu-id="4783b-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4783b-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4783b-127">Path</span><span class="sxs-lookup"><span data-stu-id="4783b-127">Path</span></span> <br/> | <span data-ttu-id="4783b-128">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4783b-128">Required</span></span> <br/> | <span data-ttu-id="4783b-129">System.String</span><span class="sxs-lookup"><span data-stu-id="4783b-129">System.String</span></span> <br/> |<span data-ttu-id="4783b-130">Fornece o caminho para a pasta em que os arquivos do site do conector de nuvem serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="4783b-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4783b-131">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="4783b-131">Input Types</span></span>
<span data-ttu-id="4783b-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4783b-132"></span></span>

<span data-ttu-id="4783b-133">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4783b-133">None.</span></span> <span data-ttu-id="4783b-134">O cmdlet Set-CcSiteDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="4783b-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4783b-135">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="4783b-135">Return Types</span></span>
<span data-ttu-id="4783b-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4783b-136"></span></span>

<span data-ttu-id="4783b-137">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4783b-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4783b-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4783b-138">See also</span></span>
<span data-ttu-id="4783b-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4783b-139"></span></span>

[<span data-ttu-id="4783b-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="4783b-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

