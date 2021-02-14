---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta a configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: cd0745081e3f069aaf58c9ffdbf24494bfb3ece1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801461"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="916d3-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="916d3-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="916d3-104">Exporta a configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="916d3-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="916d3-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="916d3-105">Examples</span></span>
<span data-ttu-id="916d3-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="916d3-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="916d3-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="916d3-107">Example 1</span></span>

<span data-ttu-id="916d3-108">O exemplo a seguir define o parâmetro Path como um caminho de arquivo completo e exporta configurações para esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="916d3-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="916d3-109">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="916d3-109">Detailed Description</span></span>
<span data-ttu-id="916d3-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="916d3-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="916d3-111">O Export-CcConfiguration cmdlet permite que você salve a configuração do Cloud Connector em um arquivo em um caminho selecionado.</span><span class="sxs-lookup"><span data-stu-id="916d3-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="916d3-112">Este comando foi introduzido na versão 2.0 do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="916d3-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="916d3-113">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="916d3-113">Parameters</span></span>
<span data-ttu-id="916d3-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="916d3-114"><a name="Examples"> </a></span></span>

|<span data-ttu-id="916d3-115">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="916d3-115">**Parameter**</span></span>|<span data-ttu-id="916d3-116">**Required**</span><span class="sxs-lookup"><span data-stu-id="916d3-116">**Required**</span></span>|<span data-ttu-id="916d3-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="916d3-117">**Type**</span></span>|<span data-ttu-id="916d3-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="916d3-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="916d3-119">Path</span><span class="sxs-lookup"><span data-stu-id="916d3-119">Path</span></span>  <br/> |<span data-ttu-id="916d3-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="916d3-120">Required</span></span>  <br/> |<span data-ttu-id="916d3-121">System.String</span><span class="sxs-lookup"><span data-stu-id="916d3-121">System.String</span></span>  <br/> |<span data-ttu-id="916d3-122">Caminho completo do arquivo onde as configurações do Cloud Connector serão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="916d3-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="916d3-123">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="916d3-123">Input Types</span></span>
<span data-ttu-id="916d3-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="916d3-124"><a name="Examples"> </a></span></span>

<span data-ttu-id="916d3-125">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="916d3-125">None.</span></span> <span data-ttu-id="916d3-126">O Export-CcConfiguration cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="916d3-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="916d3-127">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="916d3-127">Return Types</span></span>
<span data-ttu-id="916d3-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="916d3-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="916d3-129">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="916d3-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="916d3-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="916d3-130">See also</span></span>
<span data-ttu-id="916d3-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="916d3-131"><a name="Examples"> </a></span></span>

<span data-ttu-id="916d3-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="916d3-132">Import-CcConfiguration</span></span>
  

