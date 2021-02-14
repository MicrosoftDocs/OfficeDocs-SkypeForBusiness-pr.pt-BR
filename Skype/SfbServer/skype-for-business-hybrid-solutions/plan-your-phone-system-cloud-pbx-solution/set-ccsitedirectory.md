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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: O Set-CcSiteDirectory cmdlet define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá o VHD base e os arquivos de configuração do Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824185"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="42bfa-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="42bfa-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="42bfa-105">O Set-CcSiteDirectory cmdlet define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="42bfa-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="42bfa-106">A pasta conterá o VHD base e os arquivos de configuração do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="42bfa-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="42bfa-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="42bfa-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="42bfa-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42bfa-108">Examples</span></span>
<span data-ttu-id="42bfa-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="42bfa-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="42bfa-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="42bfa-110">Example 1</span></span>

<span data-ttu-id="42bfa-111">O exemplo a seguir define o diretório raiz do \\ site como SiteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="42bfa-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="42bfa-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="42bfa-112">Detailed Description</span></span>
<span data-ttu-id="42bfa-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="42bfa-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="42bfa-114">Para fornecer afinidade de gateway e alta disponibilidade, os dispositivos do Cloud Connector podem ser combinados em sites.</span><span class="sxs-lookup"><span data-stu-id="42bfa-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="42bfa-115">Os usuários são atribuídos a sites em vez de dispositivos do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="42bfa-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="42bfa-116">Cada site tem uma pasta compartilhada onde os arquivos de instalação base do VHD e do Cloud Connector são armazenados.</span><span class="sxs-lookup"><span data-stu-id="42bfa-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="42bfa-117">Os dispositivos usam essa pasta durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="42bfa-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="42bfa-118">Essa pasta deve ser compartilhada com todos os outros dispositivos em um site do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="42bfa-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="42bfa-119">A pasta padrão é C:\Users \% userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="42bfa-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="42bfa-120">O caminho pode ser exibido usando o Get-CcSiteDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="42bfa-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="42bfa-121">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="42bfa-121">Parameters</span></span>
<span data-ttu-id="42bfa-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="42bfa-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="42bfa-123">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="42bfa-123">**Parameter**</span></span>|<span data-ttu-id="42bfa-124">**Required**</span><span class="sxs-lookup"><span data-stu-id="42bfa-124">**Required**</span></span>|<span data-ttu-id="42bfa-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="42bfa-125">**Type**</span></span>|<span data-ttu-id="42bfa-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="42bfa-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="42bfa-127">Path</span><span class="sxs-lookup"><span data-stu-id="42bfa-127">Path</span></span> <br/> | <span data-ttu-id="42bfa-128">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="42bfa-128">Required</span></span> <br/> | <span data-ttu-id="42bfa-129">System.String</span><span class="sxs-lookup"><span data-stu-id="42bfa-129">System.String</span></span> <br/> |<span data-ttu-id="42bfa-130">Fornece o caminho para a pasta onde os arquivos de site do Cloud Connector serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="42bfa-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="42bfa-131">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="42bfa-131">Input Types</span></span>
<span data-ttu-id="42bfa-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="42bfa-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="42bfa-133">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="42bfa-133">None.</span></span> <span data-ttu-id="42bfa-134">O Set-CcSiteDirectory cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="42bfa-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="42bfa-135">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="42bfa-135">Return Types</span></span>
<span data-ttu-id="42bfa-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="42bfa-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="42bfa-137">Nenhum</span><span class="sxs-lookup"><span data-stu-id="42bfa-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="42bfa-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="42bfa-138">See also</span></span>
<span data-ttu-id="42bfa-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="42bfa-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="42bfa-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="42bfa-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

