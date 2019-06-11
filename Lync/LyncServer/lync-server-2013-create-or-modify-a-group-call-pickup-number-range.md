---
title: 'Lync Server 2013: criar ou modificar um intervalo de números de tira de chamada em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a82f9cdc02052bf08dba3e9529871eff2b01211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Create or modify a Group Call Pickup number range in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-30_

Utilize o procedimento a seguir para criar ou modificar o intervalo de números de um grupo de atendimento de chamadas na tabela de órbita de estacionamento de chamadas.

<div>


> [!NOTE]  
> Você deve usar o Shell de gerenciamento do Lync Server para criar, modificar, remover e exibir os intervalos de números de retirada de chamadas em grupo na tabela órbita do estacionamento de chamada. Os intervalos de números de retirada de chamadas em grupo não estão disponíveis no painel de controle do Lync Server.



</div>

<div>


> [!IMPORTANT]  
> O intervalo de números do grupo de recebimento de chamadas deve receber um tipo de GroupPickup. Os usuários são habilitados para o recebimento de chamadas em grupo apenas se o número do grupo ao qual eles estão atribuídos for o tipo GroupPickup.



</div>

Os intervalos de números de grupo de atendimento de chamadas precisam estar de acordo com as regras a seguir:

  - O número inicial do intervalo deve ser menor ou igual ao número final.

  - O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.

  - O intervalo de números precisa ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

  - Se o intervalo de números começar com o \* caractere \#ou, o intervalo deve ser maior do que 100.

  - Valores válidos: devem corresponder à cadeia de caracteres de\[\\\*|\#\]expressão\[ regular (? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}). Isso significa que o valor deve ser uma cadeia de caracteres que comece \* com \# o caractere ou ou um número de 1 a 9 (o primeiro caractere não pode ser zero). Se o primeiro caractere for \* ou \#, o seguinte caractere deve ser um número de 1 a 9 (não pode ser zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo\#, "6000"\*, "92000"\*, "95551212" e "915551212"). Se o primeiro caractere não \* for ou \#, o primeiro caractere deve ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um dos números de 0 a 9 (por exemplo, "915551212", "41212", "300").

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>Para criar ou modificar um intervalo de grupo de atendimento de chamadas

1.  Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de grupo de atendimento de chamadas. Use o **Set-CsCallParkOrbit** para modificar um intervalo existente de números de atendimento de chamadas.
    
    Na linha de comando, execute:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Por exemplo:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    O exemplo a seguir mostra como trocar um intervalo de números de órbitas de estacionamento de chamadas para grupos de atendimento de chamadas.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > Use esse cmdlet para mudar o tipo atribuído aos intervalos de números somente se você tiver especificado inicialmente o tipo incorreto e somente caso o intervalo de grupo ainda não esteja em uso. Se você alterar o intervalo de números de CallPark para GroupPickup ou vice-versa e o intervalo de números já estiver em uso, o estacionamento de chamada ou o atendimento de chamada em grupo irá parar de funcionar para aquele intervalo de números. Por exemplo, se você alterar um intervalo de números de CallPark para GroupPick, o aplicativo de estacionamento de chamadas não poderá mais usar esse intervalo de órbitas para estacionar chamadas.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluir uma faixa de opções do parque de chamadas no Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

