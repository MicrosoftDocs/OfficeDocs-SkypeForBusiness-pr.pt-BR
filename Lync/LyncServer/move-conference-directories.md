---
title: Mover diretórios de conferências
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba7480e3454d338d9d6f2ff521c09e26b4f17c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Mover diretórios de conferências

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

Antes de encerrar um pool, você precisa executar o procedimento a seguir para cada diretório de conferência no pool do Office Communications Server 2007 R2.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Para mover um diretório de conferências para o Lync Server 2013

1.  Abra o Shell de gerenciamento do Lync Server.

2.  Para obter a identidade dos diretórios de conferências em sua organização, execute os seguintes comandos:
    
        Get-CsConferenceDirectory
    
    Como esse cmdlet retorna todos os diretórios de conferência em sua organização, talvez você queira limitar os resultados apenas ao pool que deseja encerrar. Por exemplo, se você quiser encerrar um pool com o nome de domínio totalmente qualificado (FQDN) pool01.contoso.net:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Esse cmdlet retorna todos os diretórios de conferência em que a ID de serviço contém a pool01.contoso.net FQDN.

3.  Para mover diretórios de conferência, execute o seguinte procedimento para cada diretório de conferências no pool:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Por exemplo:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Você pode observar um erro, mostrado abaixo, que é causado pelo shell de gerenciamento do Lync Server que exige um conjunto atualizado de permissões do Active Directory. Para resolver o erro, feche a janela atual e abra um novo Shell de gerenciamento do Lync Server e execute o comando novamente.



</div>

![Saída de erro move-CsConferenceDirectory] (images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Saída de erro move-CsConferenceDirectory")

</div>

</div>

<span> </span>

</div>

</div>

</div>

