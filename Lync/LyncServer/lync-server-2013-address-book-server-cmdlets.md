---
title: 'Lync Server 2013: cmdlets do servidor do catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1782dbc22b94ed492878c545df70fa1bdaaeeeb3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a>Cmdlets do servidor de catálogo de endereços no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-26_

Os servidores de catálogo de endereços são intermediários entre os serviços de domínio do Active Directory e o Microsoft Lync Server 2013. O servidor de catálogo de endereços garante que as informações do usuário armazenadas no Lync Server 2013 estão sincronizadas com as informações do usuário armazenadas no Active Directory. Isso é feito pela sincronização periódica dos arquivos do Catálogo de Endereços com as informações armazenadas no banco de dados do Usuário. Por sua vez, o Lync Server inclui vários cmdlets para gerenciar servidores de catálogo de endereços.

<div>

## <a name="address-book-server-cmdlets"></a>Address Book Server Cmdlets

Não é possível definir as configurações do servidor do catálogo de endereços no painel de controle do Lync Server. O Windows PowerShell é a principal ferramenta para gerenciar essas configurações. Veja a seguir uma lista de cmdlets que se relacionam diretamente com o gerenciamento do Servidor de Catálogo de Endereços:

**Servidor do Catálogo de Endereços**

  - <span></span>  
    [Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - <span></span>  
    [New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - <span></span>  
    [Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - <span></span>  
    [Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Confira também


[Blog do PowerShell do Lync Server](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

