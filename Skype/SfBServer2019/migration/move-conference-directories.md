---
title: Mover Diretórios de Conferência
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de encerrar um pool, você deve executar o procedimento a seguir para cada diretório de conferência em seu pool herdado.
ms.openlocfilehash: 1cd4a3a3359ec1638c3ae93c6ce81d8ba2227b96
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988936"
---
# <a name="move-conference-directories"></a>Mover Diretórios de Conferência

Antes de encerrar um pool, você deve executar o procedimento a seguir para cada diretório de conferência em seu pool herdado.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Para mover um diretório de conferência para o Skype for Business Server 2019

1. Abra o Shell de gerenciamento do Skype for Business Server.
    
2. Para obter a identidade dos diretórios de conferências em sua organização, execute o seguinte comando:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    O comando anterior retorna todos os diretórios de conferência em sua organização. Por isso, talvez você queira limitar os resultados ao pool sendo descomissionado. Por exemplo, se você estiver decomissionando o pool com o nome de domínio totalmente qualificado (FQDN) pool01.contoso.net, use este comando para limitar os dados retornados a diretórios de conferência desse pool:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Esse comando retorna somente os diretórios de conferência onde a propriedade ServiceId contém a pool01.contoso.net de FQDN.
    
3. Para mover os diretórios de conferência, execute o seguinte comando para cada diretório de conferência no pool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Por exemplo, para mover o diretório de conferências 3, use este comando, especificando um pool do Skype for Business Server 2019 como TargetPool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Se você quiser mover todos os diretórios de conferência em um pool, use um comando semelhante ao seguinte:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Baixar [desinstalação do Microsoft Legacy e remover funções de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para obter instruções passo a passo abrangentes sobre como descomissionar pools herdados.
  
Ao mover os diretórios de conferência, você pode encontrar o seguinte erro:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Geralmente, esse erro ocorre quando o Shell de gerenciamento do Skype for Business Server exige um conjunto atualizado de permissões do Active Directory para concluir uma tarefa. Para resolver o problema, feche a instância atual do Shell de gerenciamento e, em seguida, abra uma nova instância do Shell e execute o comando novamente para mover o diretório de conferência.
  

