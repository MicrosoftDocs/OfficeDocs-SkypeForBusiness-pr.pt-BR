---
title: 'Lync Server 2013: Get-CsAddressBookConfiguration para gerenciamento de catálogo de endereços'
description: 'Lync Server 2013: Get-CsAddressBookConfiguration para gerenciamento de catálogo de endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91b96aead7b7038464f3166691a5952b9ff850dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566997"
---
# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Get-CsAddressBookConfiguration para gerenciamento de catálogo de endereços no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Quem pode executar este cmdlet: por padrão, os membros do grupo a seguir estão autorizados a executar o cmdlet Get-CsAddressBookConfiguration localmente: RTCUniversalServerAdmins. Para retornar uma lista de todas as funções RBAC (controle de acesso baseado em função) que receberam a atribuição desse cmdlet (incluindo qualquer função RBAC personalizada criada por você), execute o seguinte comando no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

O cmdlet Get-CsAddressBookConfiguration retorna informações sobre uma configuração que já existe.

Por exemplo:

    Get-CsAddressBookConfiguration -Identity site:Redmond

Combinando a funcionalidade do CsAddressBookConfiguration Get e do Set CsAddressBookConfiguration, permite ao administrador definir quais configurações serão modificadas e aplicar as modificações. Por exemplo, isto combinado:

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

Retorna todas as configurações em todos os sites e aplica RunTimeOfDay de 23h às configurações.

<div>

## <a name="see-also"></a>Confira também


[Get-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

