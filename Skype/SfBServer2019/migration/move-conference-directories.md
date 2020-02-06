---
title: Mover Diretórios de Conferência
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Antes de encerrar um pool, você deve executar o procedimento a seguir para cada diretório de conferência em seu pool herdado.
ms.openlocfilehash: bdcb816a91f6bc4a4372141595e46ba2369618a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813279"
---
# <a name="move-conference-directories"></a><span data-ttu-id="99c24-103">Mover Diretórios de Conferência</span><span class="sxs-lookup"><span data-stu-id="99c24-103">Move Conference Directories</span></span>

<span data-ttu-id="99c24-104">Antes de encerrar um pool, você deve executar o procedimento a seguir para cada diretório de conferência em seu pool herdado.</span><span class="sxs-lookup"><span data-stu-id="99c24-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="99c24-105">Para mover um diretório de conferência para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="99c24-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="99c24-106">Abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="99c24-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="99c24-107">Para obter a identidade dos diretórios de conferências em sua organização, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="99c24-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="99c24-108">O comando anterior retorna todos os diretórios de conferência em sua organização.</span><span class="sxs-lookup"><span data-stu-id="99c24-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="99c24-109">Por isso, talvez você queira limitar os resultados ao pool sendo descomissionado.</span><span class="sxs-lookup"><span data-stu-id="99c24-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="99c24-110">Por exemplo, se você estiver decomissionando o pool com o nome de domínio totalmente qualificado (FQDN) pool01.contoso.net, use este comando para limitar os dados retornados a diretórios de conferência desse pool:</span><span class="sxs-lookup"><span data-stu-id="99c24-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="99c24-111">Esse comando retorna somente os diretórios de conferência onde a propriedade ServiceId contém a pool01.contoso.net de FQDN.</span><span class="sxs-lookup"><span data-stu-id="99c24-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="99c24-112">Para mover os diretórios de conferência, execute o seguinte comando para cada diretório de conferência no pool:</span><span class="sxs-lookup"><span data-stu-id="99c24-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="99c24-113">Por exemplo, para mover o diretório de conferências 3, use este comando, especificando um pool do Skype for Business Server 2019 como TargetPool:</span><span class="sxs-lookup"><span data-stu-id="99c24-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="99c24-114">Se você quiser mover todos os diretórios de conferência em um pool, use um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="99c24-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="99c24-115">Baixar [desinstalação do Microsoft Legacy e remover funções de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para obter instruções passo a passo abrangentes sobre como descomissionar pools herdados.</span><span class="sxs-lookup"><span data-stu-id="99c24-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="99c24-116">Ao mover os diretórios de conferência, você pode encontrar o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="99c24-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="99c24-117">Geralmente, esse erro ocorre quando o Shell de gerenciamento do Skype for Business Server exige um conjunto atualizado de permissões do Active Directory para concluir uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="99c24-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="99c24-118">Para resolver o problema, feche a instância atual do Shell de gerenciamento e, em seguida, abra uma nova instância do Shell e execute o comando novamente para mover o diretório de conferência.</span><span class="sxs-lookup"><span data-stu-id="99c24-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

