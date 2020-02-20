---
title: 'Lync Server 2013: Test-CsAddressBookWebQuery para gerenciamento de catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff045df8425b76a42edace4a6591f52566b8c9a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a>Test-CsAddressBookWebQuery para gerenciamento de catálogo de endereços no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Quem pode executar este cmdlet: por padrão, os membros dos seguintes grupos são autorizados a executar o cmdlet Test-CsAddressBookWebQuery: RTCUniversalServerAdmins. Para retornar uma lista de todas as funções RBAC que este cmdlet foi atribuído (incluindo qualquer função RBAC que você criou sozinho), execute o seguinte comando no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Semelhante à transação sintética test-CsAddressBookService, Test-CsAddressBookWebQuery executa uma consulta em relação à consulta à Web do catálogo de endereços para garantir que ela esteja funcionando corretamente. O cmdlet será conectado à autenticação de tíquete da Web e apresentará as credenciais especificadas em – usercredential. Se for autenticado, o cmdlet apresentará as informações – TargetSipAddress. O cmdlet deve relatar êxito se tiver conseguido recuperar as informações sobre o contato.

Por exemplo:

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a>Consulte também


[Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

