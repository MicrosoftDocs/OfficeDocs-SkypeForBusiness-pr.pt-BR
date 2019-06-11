---
title: Mover Mover Diretórios de Conferência do Lync Server 2010 para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa32bb5be86d72d4f18d11bb85d5ce0b57a96725
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Mover Diretórios de Conferência

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-28_

Antes de encerrar um pool, você deve executar o procedimento a seguir para cada diretório de conferência no pool do Lync Server 2010.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Para mover um diretório de conferências para o Lync Server 2013

1.  Abra o Shell de gerenciamento do Lync Server.

2.  Para obter a identidade dos diretórios de conferências em sua organização, execute o seguinte comando:
    
        Get-CsConferenceDirectory
    
    O comando anterior retorna todos os diretórios de conferência em sua organização. Por isso, talvez você queira limitar os resultados ao pool sendo descomissionado. Por exemplo, se você estiver decomissionando o pool com o nome de domínio totalmente qualificado (FQDN) pool01.contoso.net, use este comando para limitar os dados retornados a diretórios de conferência desse pool:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Esse comando retorna somente os diretórios de conferência onde a propriedade ServiceId contém a pool01.contoso.net de FQDN.

3.  Para mover os diretórios de conferência, execute o seguinte comando para cada diretório de conferência no pool:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Por exemplo, para mover o diretório de conferências 3, use esse comando, especificando um pool do Lync Server 2013 como TargetPool:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Se você quiser mover todos os diretórios de conferência em um pool, use um comando semelhante ao seguinte:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Consulte o documento "desinstalar o Microsoft Lync Server 2010 e remover funções de servidor" (que pode ser baixado de [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) para obter instruções passo a passo abrangentes sobre como descomissionar pools do Lync 2010.

Ao mover diretórios de conferência, você pode encontrar o seguinte erro:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Esse erro geralmente ocorre quando o Shell de gerenciamento do Lync Server exige um conjunto atualizado de permissões do Active Directory para concluir uma tarefa. Para resolver o problema, feche a instância atual do Shell de gerenciamento, abra uma nova instância do Shell e execute o comando novamente para mover o diretório de conferência.

</div>

</div>

<span> </span>

</div>

</div>

</div>

