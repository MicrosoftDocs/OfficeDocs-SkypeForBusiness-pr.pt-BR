---
title: 'Lync Server 2013: excluir um objeto de contato de telefone de área comum'
description: 'Lync Server 2013: excluir um objeto de contato de telefone de área comum.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e918f7a46269f70577f28b2c3e55297959430721
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566597"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Excluir um objeto de contato de telefone de área comum no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-20_

Você pode querer excluir o objeto de contato associado a um telefone de área comum. Por exemplo, se você remover o telefone de um funcionário de descanso, não será necessário ter um objeto de contato associado a esse telefone. O cmdlet **Remove-CsCommonAreaPhone** fornece uma maneira de excluir contas de telefone de área comum. Quando você executa esse cmdlet, o telefone é excluído da lista de telefones de área comum retornados por **Get-CsCommonAreaPhone**. Além disso, o objeto de contato associado a esse telefone é excluído dos serviços de domínio do Active Directory.

Use **Remove-CsCommonAreaPhone** para remover um telefone de área comum ou todos os telefones de área comum que têm um elemento comum, como um nome de exibição ou código de área e de cidade. Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Removendo um telefone de área comum especificado

  - O comando a seguir remove o telefone de área comum com o endereço SIP sip:mainlobby@litwareinc.com:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Removendo telefones de área comuns com base em seu nome de exibição

  - Este comando Remove todos os telefones de área comum onde o nome de exibição inclui o valor de cadeia de caracteres "Building 14":
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Removendo telefones de área comum com base em seus códigos de área e país

  - Este comando Remove todos os telefones de área comum para os Estados Unidos (código do país 1) e o código de área 425:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

