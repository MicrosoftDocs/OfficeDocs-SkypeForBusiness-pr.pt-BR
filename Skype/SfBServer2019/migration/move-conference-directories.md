---
title: Mover Diretórios de Conferência
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de encerrar um pool, você deve executar o procedimento a seguir para cada diretório de conferência no seu pool herdado.
ms.openlocfilehash: b7526d8c3c032bf8b1f9052dce7da7e8a87b66b5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372802"
---
# <a name="move-conference-directories"></a><span data-ttu-id="7fa30-103">Mover Diretórios de Conferência</span><span class="sxs-lookup"><span data-stu-id="7fa30-103">Move Conference Directories</span></span>

<span data-ttu-id="7fa30-104">Antes de encerrar um pool, você deve executar o procedimento a seguir para cada diretório de conferência no seu pool herdado.</span><span class="sxs-lookup"><span data-stu-id="7fa30-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="7fa30-105">Para mover um diretório de conferência para Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7fa30-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="7fa30-106">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="7fa30-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="7fa30-107">Para obter a identidade dos diretórios de conferência em sua organização, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7fa30-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="7fa30-108">O comando anterior retorna todos os diretórios de conferência em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7fa30-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="7fa30-109">Por isso, talvez você queira limitar os resultados para o pool que está sendo descomissionar.</span><span class="sxs-lookup"><span data-stu-id="7fa30-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="7fa30-110">Por exemplo, se você estiver encerrando o pool com o pool01. contoso.NET do domínio totalmente qualificado (FQDN) do nome, use este comando para limitar os dados retornados aos diretórios de conferência desse pool:</span><span class="sxs-lookup"><span data-stu-id="7fa30-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="7fa30-111">Esse comando retorna apenas os diretórios de conferência onde a propriedade ServiceID contém o pool01. contoso.NET FQDN.</span><span class="sxs-lookup"><span data-stu-id="7fa30-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="7fa30-112">Para mover diretórios de conferência, execute o seguinte comando para cada diretório de conferência no pool:</span><span class="sxs-lookup"><span data-stu-id="7fa30-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="7fa30-113">Por exemplo, para mover diretório de conferência 3, use este comando, especificando um Skype para Business Server 2019 pool como o TargetPool:</span><span class="sxs-lookup"><span data-stu-id="7fa30-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="7fa30-114">Se você deseja mover todos os diretórios de conferência em um pool, use um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="7fa30-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="7fa30-115">Baixe o [Microsoft Desinstalando herdado e Removendo funções de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para instruções passo a passo abrangentes em encerrar os pools herdados.</span><span class="sxs-lookup"><span data-stu-id="7fa30-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="7fa30-116">Ao mover diretórios de conferência, você pode encontrar o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="7fa30-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="7fa30-117">Esse erro geralmente ocorre quando o Skype do Shell de gerenciamento do servidor de negócios requer um conjunto atualizado de permissões do Active Directory para concluir uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="7fa30-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="7fa30-118">Para resolver o problema, feche a instância atual do Shell de gerenciamento do, e em seguida, abra uma nova instância do shell e execute novamente o comando para mover o diretório de conferência.</span><span class="sxs-lookup"><span data-stu-id="7fa30-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

