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
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: O cmdlet Get-CcSiteDirectory mostra o diretório atual em que os arquivos de configuração no nível do site estão armazenados. A pasta contém o VHD de base e os arquivos de instalação do Skype for Business Cloud Connector Edition. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do conector de nuvem.
ms.openlocfilehash: 095776a680fbbcc8c43a8f99700b357175010b5a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003361"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="4c4fa-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="4c4fa-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="4c4fa-106">O cmdlet Get-CcSiteDirectory mostra o diretório atual em que os arquivos de configuração no nível do site estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="4c4fa-107">A pasta contém o VHD de base e os arquivos de instalação do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="4c4fa-108">Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="4c4fa-109">Este cmdlet se aplica ao Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="4c4fa-110">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4c4fa-110">Parameters</span></span>

<span data-ttu-id="4c4fa-111">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4c4fa-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4c4fa-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4c4fa-112">Examples</span></span>
<span data-ttu-id="4c4fa-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4c4fa-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="4c4fa-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="4c4fa-114">Example 1</span></span>

<span data-ttu-id="4c4fa-115">O exemplo a seguir mostra a pasta atual em que os arquivos de configuração e máquinas virtuais dos componentes do conector de nuvem são armazenados:</span><span class="sxs-lookup"><span data-stu-id="4c4fa-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="4c4fa-116">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="4c4fa-116">Detailed Description</span></span>
<span data-ttu-id="4c4fa-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4c4fa-117"></span></span>

<span data-ttu-id="4c4fa-118">Para oferecer afinidade de gateway e alta disponibilidade, os aparelhos do Cloud Connector podem ser combinados em sites.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="4c4fa-119">Os usuários são atribuídos a sites em vez de aparelhos de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="4c4fa-120">Cada site tem uma pasta compartilhada na qual os arquivos de instalação do VHD e do conector de nuvem base estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="4c4fa-121">Os dispositivos usam essa pasta durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="4c4fa-122">A pasta padrão é C:\Users\%USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="4c4fa-123">Você pode alterar o caminho usando o cmdlet Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4c4fa-124">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="4c4fa-124">Input Types</span></span>
<span data-ttu-id="4c4fa-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4c4fa-125"></span></span>

<span data-ttu-id="4c4fa-p104">Nenhum. O cmdlet Get-CcSiteDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4c4fa-128">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="4c4fa-128">Return Types</span></span>
<span data-ttu-id="4c4fa-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4c4fa-129"></span></span>

<span data-ttu-id="4c4fa-130">Este comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4c4fa-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4c4fa-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4c4fa-131">See also</span></span>
<span data-ttu-id="4c4fa-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4c4fa-132"></span></span>

[<span data-ttu-id="4c4fa-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="4c4fa-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

