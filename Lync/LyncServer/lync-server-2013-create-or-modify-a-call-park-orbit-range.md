---
title: 'Lync Server 2013: criar ou modificar um intervalo de órbita de estacionamento de chamada'
description: 'Lync Server 2013: criar ou modificar um intervalo de órbita de estacionamento de chamada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3889f30264593bedcffb54811dd5bd844f48f0cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553837"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Criar ou modificar um intervalo de órbita de estacionamento de chamada no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Utilize um dos seguintes procedimentos para criar ou modificar um intervalo de órbitas de estacionamento de chamada.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar o painel de controle do Lync Server para criar ou modificar um intervalo de números para estacionamento de chamadas

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Recursos de Voz** e em **Estacionamento de Chamada**.

4.  Na página **Estacionamento de Chamada**, execute um dos seguintes procedimentos:
    
      - Para criar um novo intervalo de órbitas, clique em **Novo**. Em **Nome**, digite um nome de identificação para esse intervalo de números.
        
        <div>
        

        > [!NOTE]  
        > Após confirmar o intervalo de órbitas do banco de dados, não será possível alterar esse nome.

        
        </div>
    
      - Para modificar um intervalo de órbitas existente, digite todo ou parte do nome do intervalo de órbitas no campo de pesquisa. Na lista de resultados de órbitas, clique na órbita que desejar, clique em **Editar** e clique em **Mostrar detalhes**.

5.  No primeiro campo do **Intervalo numérico**, digite o número inicial do intervalo de extensões desta órbita de estacionamento de chamada e, no segundo campo **Intervalo numérico**, digite o número final do intervalo.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.</P>
    > <LI>
    > <P>O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.</P>
    > <LI>
    > <P>O intervalo da órbita deve ser único. Esse intervalo não pode se sobrepor a nenhum outro intervalo.</P>
    > <LI>
    > <P>Se o intervalo da órbita começa com um caractere * ou #, o intervalo deve ser maior que 100.</P>
    > <LI>
    > <P>Valores válidos: devem corresponder à cadeia de caracteres de expressão regular ([ \* | #]? [ 1-9] \d {0,7} ) | ([1-9] \d {0,8} ). Isso significa que o valor deve ser uma cadeira de caracteres iniciando tanto com um caractere * ou # ou um número entre 1 e 9 (o primeiro caractere não pode ser zero). Se o primeiro caractere for * ou #, o caractere seguinte deve ser um número entre 1 e 9 (não pode ser zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000", "*92000", "* 95551212" e "915551212"). Se o primeiro caractere não é * ou #, deve ser um número de 1 a 9 (não pode ser zero), seguido por oito caracteres, cada um com número de 0 a 9 (por exemplo: "915551212", "41212", "300").</P>
    > <LI>
    > <P>Você não deve ter mais que um total de 50.000 órbitas por pool. Cada intervalo de órbita geralmente abrange 100 órbitas ou menos, mas pode ser muito maior, contanto que inclua menos que 10.000 órbitas. Por exemplo, em vez de especificar um número inicial em "7000000" e um número final em "8000000", considere especificar um número inicial em "7000000" e um número final em "7000100".</P></LI></UL>

    
    </div>

6.  No **FQDN do servidor de destino**, clique no FQDN ou na ID do serviço de aplicativo que hospeda o aplicativo de Estacionamento de Chamada. Todas as chamadas estacionadas em números entre o intervalo especificado pelo número inicial e o número final no intervalo da órbita será roteado para esse servidor ou pool.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar o Windows PowerShell para criar ou modificar um intervalo de números para estacionamento de chamadas

1.  Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de órbitas. Use o **Set-CsCallParkOrbit** para modificar um intervalo de números de órbitas de estacionamento de chamada existente.
    
    Na linha de comando, execute:
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Por exemplo:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    O seguinte exemplo mostra como modificar os números em intervalo de órbitas existente
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluir um intervalo de órbita de estacionamento de chamada no Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

