---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta a configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host dessa solução.
ms.openlocfilehash: 8afca55e6727c84c579957de9e2010e84a72fb15
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234053"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="def66-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="def66-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="def66-104">Exporta a configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host dessa solução.</span><span class="sxs-lookup"><span data-stu-id="def66-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="def66-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="def66-105">Examples</span></span>
<span data-ttu-id="def66-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="def66-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="def66-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="def66-107">Example 1</span></span>

<span data-ttu-id="def66-108">O exemplo a seguir define o parâmetro Path como um caminho de arquivo completo e exporta as configurações para esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="def66-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="def66-109">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="def66-109">Detailed Description</span></span>
<span data-ttu-id="def66-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="def66-110"></span></span>

<span data-ttu-id="def66-p101">O cmdlet Export-CcConfiguration permite que você salve a configuração do Cloud Connector em um arquivo com um caminho selecionado. Este comando foi introduzido na versão 2.0 do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="def66-p101">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path. This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="def66-113">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="def66-113">Parameters</span></span>
<span data-ttu-id="def66-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="def66-114"></span></span>

|<span data-ttu-id="def66-115">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="def66-115">**Parameter**</span></span>|<span data-ttu-id="def66-116">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="def66-116">**Required**</span></span>|<span data-ttu-id="def66-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="def66-117">**Type**</span></span>|<span data-ttu-id="def66-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="def66-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="def66-119">Path</span><span class="sxs-lookup"><span data-stu-id="def66-119">Path</span></span>  <br/> |<span data-ttu-id="def66-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="def66-120">Required</span></span>  <br/> |<span data-ttu-id="def66-121">System.String</span><span class="sxs-lookup"><span data-stu-id="def66-121">System.String</span></span>  <br/> |<span data-ttu-id="def66-122">Caminho completo onde as configurações do Cloud Connector serão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="def66-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="def66-123">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="def66-123">Input Types</span></span>
<span data-ttu-id="def66-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="def66-124"></span></span>

<span data-ttu-id="def66-p102">Nenhum. O cmdlet Export-CcConfiguration não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="def66-p102">None. The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="def66-127">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="def66-127">Return Types</span></span>
<span data-ttu-id="def66-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="def66-128"></span></span>

<span data-ttu-id="def66-129">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="def66-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="def66-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="def66-130">See also</span></span>
<span data-ttu-id="def66-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="def66-131"></span></span>

<span data-ttu-id="def66-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="def66-132">Import-CcConfiguration</span></span>
  

