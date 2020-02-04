---
title: 'Lync Server 2013: planejando o controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c07674be037c7d2fe06d6e2811dcd3264cc6db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Planejando o controle de chamada remota no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-05_

No Lync Server 2013, o suporte para cenários de controle de chamada remota permite que os usuários controlem seus telefones PBX (Private Branch Exchange) usando o Lync 2013 em seus computadores desktop. Esta seção descreve os recursos de controle de chamada remota e os requisitos para a implantação do controle de chamada remota.

A integração entre um PBX e o Lync Server 2013 torna possível aos usuários habilitados para controle de chamada remota usar a interface do usuário do Lync 2013 para controlar chamadas em seus telefones PBX das seguintes maneiras:

<div>


> [!NOTE]  
> Por fim, os recursos do PBX que hospedam o telefone PBX de um usuário determinam os recursos de controle de chamada remota que estarão disponíveis para esse usuário.



</div>

  - Fazer uma chamada de saída

  - Atender uma chamada de entrada

  - Atender uma chamada de entrada com uma mensagem instantânea
    
    <div>
    

    > [!NOTE]  
    > Ou seja, quando o número de telefone do chamador pode ser associado a um endereço de mensagem instantânea na GAL (lista de endereços global) da sua organização, na lista de contatos do Lync do chamador ou na organização de um parceiro federado.

    
    </div>

  - Transferir uma chamada

  - Encaminhar uma chamada de entrada

  - Fazer chamadas em espera

  - Alternar entre várias chamadas simultâneas

  - Atender uma segunda chamada enquanto já estiver em uma chamada (ou seja, chamada em espera)

  - Discar dígitos de multifrequência (DTMF) de Tom duplo

  - Na janela de conversa, digite anotações no programa de anotações do Microsoft Office OneNote

Além disso, quando um usuário está habilitado para controle de chamada remota, o Lync 2013 fornece ao usuário as seguintes informações de chamada:

  - Identificação de um chamador por nome quando o número de telefone do chamador existe na lista de contatos de um cliente de colaboração e mensagens do Microsoft Office Outlook habilitado para controle de chamada remota, lista de contatos do Lync ou GAL da sua organização.

  - Chamadas de entrada e saída passadas, que são salvas na pasta Histórico de conversas no Outlook.

  - Notificações de chamada perdida, que são enviadas para a pasta caixa de entrada do Outlook do usuário, mas são geradas apenas se o Lync estiver sendo executado quando a chamada de entrada for recebida.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Controle de chamada remota e Enterprise Voice

Embora os recursos de controle de chamada remota sejam separados das funcionalidades do Enterprise Voice e os usuários não podem ser habilitados para ambos, o Enterprise Voice fornece um subconjunto de recursos que também estão disponíveis para os usuários que estão habilitados para controle de chamada remota. Se o Enterprise Voice for implantado, os usuários habilitados para controle de chamada remota poderão usar o Lync para acessar os seguintes recursos da Enterprise Voice:

  - Fazer e receber chamadas de áudio para outro cliente do Lync

  - Ingressar na parte de áudio de uma conferência criada por um usuário habilitado para o Enterprise Voice

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Tarefas de implantação de controle de chamada remota no Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

