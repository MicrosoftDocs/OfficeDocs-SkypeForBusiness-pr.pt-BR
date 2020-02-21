---
title: 'Lync Server 2013: Update-CsAddressBook para gerenciamento de catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745e636cc4bac682beaf2ea308cd465c3d194df7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Update-CsAddressBook para gerenciamento de catálogo de endereços no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Quem pode executar esse cmdlet: Por padrão, membros dos seguintes grupos estão autorizados a executar o cmdlet Update-CsAddressBook localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para retornar uma lista de todas as funções RBAC que este cmdlet foi atribuído (incluindo qualquer função RBAC que você criou sozinho), execute o seguinte comando no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

O cmdlet Update-CsAddressBook substitui o comando **abserver. exe – syncNow** do Office Communications Server. O objetivo do cmdlet é iniciar uma sincronização imediatamente em vez de aguardar o horário agendado. O primeiro comando de exemplo atualiza todos os catálogos de endereços na organização. A segunda atualiza apenas o catálogo de endereços associado ao servidor definido.

<div>


> [!NOTE]  
> No Lync Server 2013, o replicador de usuários do Lync Server selecionará as alterações do Active Directory e atualizará o banco de dados de usuário do Lync Server com base em um intervalo configurado. O replicador de usuários do Lync Server também propagará as alterações para o banco de dados do RTCab rapidamente, sem que o administrador tenha que executar Update-CSAddressBook. Os administradores precisarão executar o Atualizar -CSAddressBook somente se o download de arquivo do Catálogo de Endereços estiver habilitado.



</div>

Por exemplo:

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>Consulte também


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

