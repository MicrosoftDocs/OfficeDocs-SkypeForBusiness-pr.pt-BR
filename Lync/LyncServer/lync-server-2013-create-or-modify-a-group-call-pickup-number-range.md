---
title: 'Lync Server 2013: criar ou modificar um intervalo de números de recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd323e609a811a9735c966645c5176fb8784bb4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Criar ou modificar um intervalo de números de recebimento de chamadas em grupo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-30_

Use o procedimento a seguir para criar ou modificar um intervalo de números do grupo de recebimento de chamada na tabela de órbita de estacionamento de chamada.

<div>


> [!NOTE]  
> Você deve usar o Shell de gerenciamento do Lync Server para criar, modificar, remover e exibir intervalos de números de recebimento de chamadas em grupo na tabela de órbita de estacionamento de chamada. Os intervalos de números de recebimento de chamadas de grupo não estão disponíveis no painel de controle do Lync Server.



</div>

<div>


> [!IMPORTANT]  
> O intervalo de números do grupo de recebimento de chamadas deve ser atribuído a um tipo de GroupPickup. Os usuários são habilitados para o recebimento de chamadas em grupo somente se o número do grupo atribuído for o tipo GroupPickup.



</div>

Os intervalos de números do grupo de recebimento de chamadas devem estar em conformidade com as seguintes regras:

  - O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.

  - O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.

  - O intervalo de números deve ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

  - Se o intervalo de números começar com o \* caractere \#ou, o intervalo deve ser maior que 100.

  - Valores válidos: devem corresponder à cadeia de caracteres de\[\\\*|\#\]expressão\[ regular (? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}). Isso significa que o valor deve ser uma cadeia de caracteres que comece \* com \# o caractere ou um número de 1 a 9 (o primeiro caractere não pode ser zero). Se o primeiro caractere for \* ou \#, o caractere seguinte deve ser um número de 1 a 9 (não pode ser zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo\#, "6000"\*, "92000"\*, "95551212" e "915551212"). Se o primeiro caractere não \* for ou \#, o primeiro caractere deve ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um com um número de 0 a 9 (por exemplo, "915551212", "41212", "300").

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para criar ou modificar um intervalo de grupos de recebimento de chamadas

1.  Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Use **New-CsCallParkOrbit** para criar um novo intervalo de números de grupo de recebimento de chamada. Use **set-CsCallParkOrbit** para modificar um intervalo existente de números de recebimento de chamada.
    
    Na linha de comando, execute:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Por exemplo:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    O exemplo a seguir mostra como alterar um intervalo de números de órbitas de estacionamento de chamada para chamar grupos de retirada.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > Use este cmdlet para alterar o tipo atribuído a intervalos de números somente se você especificou inicialmente o tipo incorreto e o intervalo de grupo ainda não estiver em uso. Se você alterar o intervalo de números de CallPark para GroupPickup ou vice-versa e o intervalo de números já estiver em uso, o estacionamento de chamadas ou o recebimento de chamadas de grupo deixará de funcionar para esse intervalo de números. Por exemplo, se você alterar um intervalo de números de CallPark para GroupPick, o aplicativo de estacionamento de chamadas não poderá mais usar esse intervalo de órbitas para estacionar chamadas.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira Também


[Excluir um intervalo de órbita de estacionamento de chamada no Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

