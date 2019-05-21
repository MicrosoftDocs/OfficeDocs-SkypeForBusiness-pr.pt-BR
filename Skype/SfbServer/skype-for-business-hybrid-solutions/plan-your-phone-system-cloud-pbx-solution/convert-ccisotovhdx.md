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
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: O cmdlet Convert-CcIsoToVhdx cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 7b1426fe3180576e28780aeae96ee8e4913bb399
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287535"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="5adb4-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="5adb4-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="5adb4-p102">O cmdlet Convert-CcIsoToVhdx cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5adb4-p102">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file. The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="5adb4-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5adb4-107">Parameters</span></span>

|<span data-ttu-id="5adb4-108">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="5adb4-108">**Parameter**</span></span>|<span data-ttu-id="5adb4-109">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="5adb4-109">**Required**</span></span>|<span data-ttu-id="5adb4-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5adb4-110">**Type**</span></span>|<span data-ttu-id="5adb4-111">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5adb4-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5adb4-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="5adb4-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="5adb4-113">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5adb4-113">Required</span></span> <br/> |<span data-ttu-id="5adb4-114">System.String</span><span class="sxs-lookup"><span data-stu-id="5adb4-114">System.String</span></span>  <br/> | <span data-ttu-id="5adb4-115">O caminho do arquivo ISO do Windows Server 2012 R2. </span><span class="sxs-lookup"><span data-stu-id="5adb4-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="5adb4-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="5adb4-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="5adb4-117">Opcional</span><span class="sxs-lookup"><span data-stu-id="5adb4-117">Optional</span></span>  <br/> |<span data-ttu-id="5adb4-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5adb4-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5adb4-p103">Se o processo de conversão falhar durante a atualização do Windows, você pode tentar configurar uma rede/proxy e atualizar o Windows manualmente. Após a conclusão do trabalho manual, você pode executar este cmdlet com o parâmetro -GeneralizeOnly e ele concluirá as tarefas  restantes. </span><span class="sxs-lookup"><span data-stu-id="5adb4-p103">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually. After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="5adb4-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="5adb4-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="5adb4-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="5adb4-122">Optional</span></span>  <br/> |<span data-ttu-id="5adb4-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5adb4-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5adb4-p104">Para atualizar o Windows, alguma configuração manual de rede/proxy na VM base pode ser necessária. O processo de conversão pausará antes da atualização do Windows, se esse parâmetro for fornecido. Depois que a configuração manual for concluída, será possível retomar o processo. </span><span class="sxs-lookup"><span data-stu-id="5adb4-p104">To update Windows, some manual network/proxy configuration on the base VM might be necessary. The conversion process will pause before Windows update if this parameter is provided. After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="5adb4-127">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5adb4-127">Examples</span></span>
<span data-ttu-id="5adb4-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5adb4-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="5adb4-129">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="5adb4-129">Example 1</span></span>

<span data-ttu-id="5adb4-130">O exemplo seguinte prepara o arquivo VHDX base usando um arquivo ISO do Windows Server 2012 R2 localizado em "C:\Windows_Server_2012_R2-EN-US-x64.ISO": </span><span class="sxs-lookup"><span data-stu-id="5adb4-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="5adb4-131">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="5adb4-131">Example 2</span></span>

<span data-ttu-id="5adb4-132">Se o cmdlet Convert-CcIsoToVhdx falhar durante a atualização do Windows, provavelmente será devido à configuração incorreta de rede/proxy.</span><span class="sxs-lookup"><span data-stu-id="5adb4-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="5adb4-133">Você pode seguir as instruções na mensagem de erro e fazer logon na máquina virtual base para corrigir o problema e atualizar o Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="5adb4-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="5adb4-134">Após a conclusão do trabalho manual, execute novamente o cmdlet com o parâmetro -GeneralizeOnly e ele concluirá as tarefas  restantes.</span><span class="sxs-lookup"><span data-stu-id="5adb4-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="5adb4-135">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="5adb4-135">Example 3</span></span>

<span data-ttu-id="5adb4-136">Se a configuração manual for necessária para atualizar o Windows, você pode usar o parâmetro -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="5adb4-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="5adb4-137">Com esse parâmetro, o conector de nuvem será pausado antes do processo do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="5adb4-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="5adb4-138">Então, você poderá concluir a configuração manual e retomar o processo de conversão como a seguir:</span><span class="sxs-lookup"><span data-stu-id="5adb4-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="5adb4-139">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="5adb4-139">Detailed Description</span></span>
<span data-ttu-id="5adb4-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5adb4-140"></span></span>

<span data-ttu-id="5adb4-141">O cmdlet Convert-CcIsoToVhdx cria uma VM base primeiro, instala alguns componentes básicos dos quais o conector de nuvem depende e, em seguida, instala as atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="5adb4-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="5adb4-142">Por fim, ele generaliza a máquina virtual (Sysprep) para obter um arquivo VHDX básico que será usado pelas máquinas virtuais de um aparelho de conexão de nuvem.</span><span class="sxs-lookup"><span data-stu-id="5adb4-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="5adb4-143">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="5adb4-143">Input Types</span></span>
<span data-ttu-id="5adb4-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5adb4-144"></span></span>

<span data-ttu-id="5adb4-p108">Nenhum. O cmdlet Convert-CcIsoToVhdx não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="5adb4-p108">None. The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="5adb4-147">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="5adb4-147">Return Types</span></span>
<span data-ttu-id="5adb4-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5adb4-148"></span></span>

<span data-ttu-id="5adb4-149">Nenhum </span><span class="sxs-lookup"><span data-stu-id="5adb4-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5adb4-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5adb4-150">See also</span></span>
<span data-ttu-id="5adb4-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5adb4-151"></span></span>

<span data-ttu-id="5adb4-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5adb4-152">None</span></span>
  

