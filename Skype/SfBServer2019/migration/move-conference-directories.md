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
ms.openlocfilehash: 18cbada5833a5160fc1eb81560c56bc9fcff3e2a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028009"
---
# <a name="move-conference-directories"></a>Mover Diretórios de Conferência

Antes de encerrar um pool, você deve executar o procedimento a seguir para cada diretório de conferência no seu pool herdado.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Para mover um diretório de conferência para Skype para Business Server 2019

1. Abra o Skype do Shell de gerenciamento do servidor de negócios.
    
2. Para obter a identidade dos diretórios de conferência em sua organização, execute o seguinte comando:
    
  ```
  Get-CsConferenceDirectory
  ```

    O comando anterior retorna todos os diretórios de conferência em sua organização. Por isso, talvez você queira limitar os resultados para o pool que está sendo descomissionar. Por exemplo, se você estiver encerrando o pool com o pool01. contoso.NET do domínio totalmente qualificado (FQDN) do nome, use este comando para limitar os dados retornados aos diretórios de conferência desse pool:
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
  ```

    Esse comando retorna apenas os diretórios de conferência onde a propriedade ServiceID contém o pool01. contoso.NET FQDN.
    
3. Para mover diretórios de conferência, execute o seguinte comando para cada diretório de conferência no pool:
    
  ```
  Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
  ```

    Por exemplo, para mover diretório de conferência 3, use este comando, especificando um Skype para Business Server 2019 pool como o TargetPool:
    
  ```
  Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
  ```

    Se você deseja mover todos os diretórios de conferência em um pool, use um comando semelhante ao seguinte:
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
  ```

Baixe o [Microsoft Desinstalando herdado e Removendo funções de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para instruções passo a passo abrangentes em encerrar os pools herdados.
  
Ao mover diretórios de conferência, você pode encontrar o seguinte erro:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Esse erro geralmente ocorre quando o Skype do Shell de gerenciamento do servidor de negócios requer um conjunto atualizado de permissões do Active Directory para concluir uma tarefa. Para resolver o problema, feche a instância atual do Shell de gerenciamento do, e em seguida, abra uma nova instância do shell e execute novamente o comando para mover o diretório de conferência.
  

