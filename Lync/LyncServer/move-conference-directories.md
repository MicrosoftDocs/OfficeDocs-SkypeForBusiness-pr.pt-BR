---
title: Mover diretórios de conferência
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d53e3183d781f527373ffcfb8573da9fbb52d41f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500298"
---
# <a name="move-conference-directories"></a>Mover diretórios de conferência

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Antes de encerrar um pool, você precisa executar o procedimento a seguir para cada diretório de conferência no pool do Office Communications Server 2007 R2.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Para mover um diretório de conferência para o Lync Server 2013

1.  Abra o Shell de Gerenciamento do Lync Server.

2.  Para obter a identidade dos diretórios de conferência de sua organização, execute os seguintes comandos:
    
        Get-CsConferenceDirectory
    
    Como este cmdlet retorna todos os diretórios de conferência da organização, convém limitar os resultados apenas ao pool que deseja encerrar. Por exemplo, caso deseje encerrar um pool com o FQDN (nome de domínio totalmente qualificado) pool01.contoso.net:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Este cmdlet retorna todos os diretórios de conferência cujos IDs de serviço contêm o FQDN pool01.contoso.net.

3.  Para mover diretórios de conferência, execute o seguinte comando para cada diretório de conferência no pool:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Por exemplo:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Você pode encontrar um erro, mostrado abaixo, que é causado pelo shell de gerenciamento do Lync Server que requer um conjunto atualizado de permissões do Active Directory. Para resolver o erro, feche a janela atual e abra um novo Shell de gerenciamento do Lync Server e execute o comando novamente.



</div>

![Saída de erro move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory saída de erro")

</div>

</div>

<span> </span>

</div>

</div>

</div>

