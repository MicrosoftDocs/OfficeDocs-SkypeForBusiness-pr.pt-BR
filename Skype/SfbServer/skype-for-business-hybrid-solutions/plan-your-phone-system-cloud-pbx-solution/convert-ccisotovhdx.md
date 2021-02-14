---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: O Convert-CcIsoToVhdx cmdlet cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802421"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="5ccc3-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="5ccc3-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="5ccc3-105">O Convert-CcIsoToVhdx cmdlet cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-105">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file.</span></span> <span data-ttu-id="5ccc3-106">O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-106">The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="5ccc3-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5ccc3-107">Parameters</span></span>

|<span data-ttu-id="5ccc3-108">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="5ccc3-108">**Parameter**</span></span>|<span data-ttu-id="5ccc3-109">**Required**</span><span class="sxs-lookup"><span data-stu-id="5ccc3-109">**Required**</span></span>|<span data-ttu-id="5ccc3-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5ccc3-110">**Type**</span></span>|<span data-ttu-id="5ccc3-111">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5ccc3-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ccc3-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="5ccc3-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="5ccc3-113">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5ccc3-113">Required</span></span> <br/> |<span data-ttu-id="5ccc3-114">System.String</span><span class="sxs-lookup"><span data-stu-id="5ccc3-114">System.String</span></span>  <br/> | <span data-ttu-id="5ccc3-115">O caminho para o arquivo ISO do Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="5ccc3-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="5ccc3-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="5ccc3-117">Opcional</span><span class="sxs-lookup"><span data-stu-id="5ccc3-117">Optional</span></span>  <br/> |<span data-ttu-id="5ccc3-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5ccc3-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5ccc3-119">Se o processo de conversão falhar durante a atualização do Windows, você pode tentar configurar uma rede/proxy e atualizar o Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-119">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually.</span></span> <span data-ttu-id="5ccc3-120">Depois que o trabalho manual for concluído, você poderá executar esse cmdlet com o parâmetro -GeneralizeOnly e ele concluirá os trabalhos restantes.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-120">After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="5ccc3-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="5ccc3-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="5ccc3-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="5ccc3-122">Optional</span></span>  <br/> |<span data-ttu-id="5ccc3-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5ccc3-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5ccc3-124">Para atualizar o Windows, algumas configurações manuais de rede/proxy na VM base podem ser necessárias.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-124">To update Windows, some manual network/proxy configuration on the base VM might be necessary.</span></span> <span data-ttu-id="5ccc3-125">O processo de conversão será pausado antes da atualização do Windows se esse parâmetro for fornecido.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-125">The conversion process will pause before Windows update if this parameter is provided.</span></span> <span data-ttu-id="5ccc3-126">Depois que a configuração manual for feita, você poderá retomar o processo.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-126">After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="5ccc3-127">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5ccc3-127">Examples</span></span>
<span data-ttu-id="5ccc3-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5ccc3-128"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5ccc3-129">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="5ccc3-129">Example 1</span></span>

<span data-ttu-id="5ccc3-130">O exemplo a seguir prepara o arquivo VHDX base usando um arquivo ISO do Windows Server 2012 R2 localizado em "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span><span class="sxs-lookup"><span data-stu-id="5ccc3-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="5ccc3-131">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="5ccc3-131">Example 2</span></span>

<span data-ttu-id="5ccc3-132">Se o Convert-CcIsoToVhdx cmdlet falhar durante a atualização do Windows, provavelmente é devido à configuração incorreta de rede/proxy.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="5ccc3-133">Você pode seguir as instruções na mensagem de erro e fazer logon na máquina virtual base para corrigir o problema e atualizar o Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="5ccc3-134">Depois que o trabalho manual for concluído, execute o cmdlet novamente com o parâmetro -GeneralizeOnly para concluir os trabalhos restantes:</span><span class="sxs-lookup"><span data-stu-id="5ccc3-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="5ccc3-135">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="5ccc3-135">Example 3</span></span>

<span data-ttu-id="5ccc3-136">Se a configuração manual for necessária para atualizar o Windows, você poderá usar o parâmetro -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="5ccc3-137">Com esse parâmetro, o Cloud Connector pausa antes do processo de atualização do Windows.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="5ccc3-138">Em seguida, você pode concluir a configuração manual e retomar o processo de conversão da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="5ccc3-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="5ccc3-139">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="5ccc3-139">Detailed Description</span></span>
<span data-ttu-id="5ccc3-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5ccc3-140"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="5ccc3-141">O Convert-CcIsoToVhdx cmdlet cria uma VM base primeiro, instala alguns componentes básicos dos que o Cloud Connector depende e, em seguida, instala as atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="5ccc3-142">Por fim, ele generaliza a máquina virtual (sysprep) para obter um arquivo VHDX base que será usado pelas máquinas virtuais de um dispositivo do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="5ccc3-143">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="5ccc3-143">Input Types</span></span>
<span data-ttu-id="5ccc3-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ccc3-144"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="5ccc3-145">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-145">None.</span></span> <span data-ttu-id="5ccc3-146">O Convert-CcIsoToVhdx cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="5ccc3-146">The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="5ccc3-147">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="5ccc3-147">Return Types</span></span>
<span data-ttu-id="5ccc3-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ccc3-148"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5ccc3-149">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5ccc3-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5ccc3-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="5ccc3-150">See also</span></span>
<span data-ttu-id="5ccc3-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ccc3-151"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5ccc3-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5ccc3-152">None</span></span>
  

