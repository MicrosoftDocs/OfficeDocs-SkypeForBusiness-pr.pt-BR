---
title: 'Lync Server 2013: testar definições de configuração do tronco SIP'
description: 'Lync Server 2013: testar as definições de configuração do tronco SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d44fe2ef5123bec31fafaff2d811a501e5cca4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558267"
---
# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a>Testar as definições de configuração do tronco SIP no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:

  - Se o bypass de mídia deve ser habilitado nos troncos.

  - As condições nas quais os pacotes RTCP são enviados.

  - Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala o Microsoft Lync Server 2013, uma coleção global de definições de configuração do tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN). Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar que um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.

As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration). Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a>Para testar as definições de configuração do tronco SIP

  - Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

