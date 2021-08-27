---
title: Mover de diretórios de conferência
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Antes de desmantelar um pool, você deve executar o procedimento a seguir para cada diretório de conferência em seu pool herdável.
ms.openlocfilehash: 5d4333f74c1d45e57e45c66c8de6f3e279cee01f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596145"
---
# <a name="move-conference-directories"></a>Mover de diretórios de conferência

Antes de desmantelar um pool, você deve executar o procedimento a seguir para cada diretório de conferência em seu pool herdável.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Para mover um diretório de conferências para Skype for Business Server 2019

1. Abra o Shell Skype for Business Server Gerenciamento.
    
2. Para obter a identidade dos diretórios de conferência em sua organização, execute o seguinte comando:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    O comando anterior retorna todos os diretórios de conferência em sua organização. Por isso, talvez você queira limitar os resultados ao pool que está sendo desativado. Por exemplo, se você estiver desativando o pool com o nome de domínio totalmente qualificado (FQDN) pool01.contoso.net, use este comando para limitar os dados retornados aos diretórios de conferência desse pool:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Esse comando retorna apenas os diretórios de conferência onde a propriedade ServiceID contém o FQDN pool01.contoso.net.
    
3. Para mover diretórios de conferência, execute o seguinte comando para cada diretório de conferência no pool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Por exemplo, para mover o diretório de conferência 3, use este comando, especificando um pool Skype for Business Server 2019 como TargetPool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Se você quiser mover todos os diretórios de conferência em um pool, use um comando semelhante ao seguinte:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Baixe [Desinstalando](https://go.microsoft.com/fwlink/p/?linkId=246227) o legado da Microsoft e removendo funções de servidor para obter instruções completas e passo a passo sobre a desativação de pools herdados.
  
Ao mover diretórios de conferência, você pode encontrar o seguinte erro:
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Esse erro normalmente ocorre quando o Shell de Gerenciamento Skype for Business Server requer um conjunto atualizado de permissões do Active Directory para concluir uma tarefa. Para resolver o problema, feche a instância atual do Shell de Gerenciamento e abra uma nova instância do shell e execute o comando para mover o diretório de conferência.
  

