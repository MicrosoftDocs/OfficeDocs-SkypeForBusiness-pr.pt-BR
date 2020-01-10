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
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta a configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host dessa solução.
ms.openlocfilehash: cb3ea5a48c4e8911dc94526f85a517082d057b6e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003431"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="2c7ac-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="2c7ac-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="2c7ac-104">Exporta a configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host dessa solução.</span><span class="sxs-lookup"><span data-stu-id="2c7ac-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="2c7ac-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2c7ac-105">Examples</span></span>
<span data-ttu-id="2c7ac-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c7ac-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="2c7ac-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2c7ac-107">Example 1</span></span>

<span data-ttu-id="2c7ac-108">O exemplo a seguir define o parâmetro Path como um caminho de arquivo completo e exporta as configurações para esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="2c7ac-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="2c7ac-109">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="2c7ac-109">Detailed Description</span></span>
<span data-ttu-id="2c7ac-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c7ac-110"></span></span>

<span data-ttu-id="2c7ac-p101">O cmdlet Export-CcConfiguration permite que você salve a configuração do Cloud Connector em um arquivo com um caminho selecionado. Este comando foi introduzido na versão 2.0 do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="2c7ac-p101">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path. This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2c7ac-113">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2c7ac-113">Parameters</span></span>
<span data-ttu-id="2c7ac-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c7ac-114"></span></span>

|<span data-ttu-id="2c7ac-115">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="2c7ac-115">**Parameter**</span></span>|<span data-ttu-id="2c7ac-116">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="2c7ac-116">**Required**</span></span>|<span data-ttu-id="2c7ac-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2c7ac-117">**Type**</span></span>|<span data-ttu-id="2c7ac-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2c7ac-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c7ac-119">Path</span><span class="sxs-lookup"><span data-stu-id="2c7ac-119">Path</span></span>  <br/> |<span data-ttu-id="2c7ac-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="2c7ac-120">Required</span></span>  <br/> |<span data-ttu-id="2c7ac-121">System.String</span><span class="sxs-lookup"><span data-stu-id="2c7ac-121">System.String</span></span>  <br/> |<span data-ttu-id="2c7ac-122">Caminho completo onde as configurações do Cloud Connector serão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="2c7ac-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2c7ac-123">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2c7ac-123">Input Types</span></span>
<span data-ttu-id="2c7ac-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c7ac-124"></span></span>

<span data-ttu-id="2c7ac-p102">Nenhum. O cmdlet Export-CcConfiguration não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="2c7ac-p102">None. The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2c7ac-127">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="2c7ac-127">Return Types</span></span>
<span data-ttu-id="2c7ac-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c7ac-128"></span></span>

<span data-ttu-id="2c7ac-129">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2c7ac-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c7ac-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2c7ac-130">See also</span></span>
<span data-ttu-id="2c7ac-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c7ac-131"></span></span>

<span data-ttu-id="2c7ac-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="2c7ac-132">Import-CcConfiguration</span></span>
  

