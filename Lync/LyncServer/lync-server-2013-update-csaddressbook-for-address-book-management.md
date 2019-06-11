---
title: 'Lync Server 2013: Update-CsAddressBook para gerenciamento de catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22923d0227c75ee6f2055d4a2ac350a6df6b37bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Update-CsAddressBook para o gerenciamento de catálogo de endereços no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Quem pode executar este cmdlet: por padrão, os membros dos grupos a seguir estão autorizados a executar o cmdlet Update-CsAddressBook localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

O cmdlet Update-CsAddressBook substitui o comando **abserver. exe – syncNow** do Office Communications Server. A finalidade do cmdlet é iniciar uma sincronização imediatamente em vez de aguardar o horário agendado. O primeiro exemplo de comando atualiza todos os catálogos de endereços da organização. A segunda atualiza somente o catálogo de endereços associado ao servidor definido.

<div>


> [!NOTE]  
> No Lync Server 2013, o duplicador de usuários do Lync Server atenderá as alterações do Active Directory e atualizará o banco de dados de usuários do Lync Server com base em um intervalo configurado. O duplicador de usuários do Lync Server também propagará as alterações para o banco de dados do RTCab rapidamente, sem que o administrador tenha que executar Update-CSAddressBook. Os administradores só precisarão executar Update-CSAddressBook se o download do arquivo do catálogo de endereços estiver habilitado.



</div>

Por exemplo:

   ```
    Update-CsAddressBook
   ```

   ```
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>Confira também


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

