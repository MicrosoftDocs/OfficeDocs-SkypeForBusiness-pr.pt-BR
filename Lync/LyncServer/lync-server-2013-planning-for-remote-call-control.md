---
title: 'Lync Server 2013: planejamento para controle de chamada remota'
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
ms.openlocfilehash: 7a2faff08d5517809d4cfb11d00711a146accc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Planejando o controle de chamada remota no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-05_

No Lync Server 2013, o suporte para cenários de controle de chamada remota permite que os usuários controlem seus telefones de PBX (central privada de comutação telefônica) usando o Lync 2013 em seus computadores desktop. Esta seção descreve os recursos de controle de chamada remota e os requisitos para a implantação do controle de chamada remota.

A integração entre um PBX e o Lync Server 2013 torna possível que os usuários habilitados para controle de chamada remota usem a interface de usuário do Lync 2013 (UI) para controlar as chamadas em seus telefones PBX das seguintes maneiras:

<div>


> [!NOTE]  
> Por fim, os recursos do PBX que hospeda o telefone PBX de um usuário determinam os recursos de controle de chamada remota disponíveis para o usuário.



</div>

  - Fazer uma chamada de saída

  - Atender uma chamada recebida

  - Atender uma chamada com uma mensagem instantânea
    
    <div>
    

    > [!NOTE]  
    > Ou seja, quando o número de telefone do chamador pode ser associado a um endereço de mensagem instantânea na GAL (lista de endereços global) da sua organização, na lista de contatos do Lync do receptor ou em uma organização de um parceiro federado.

    
    </div>

  - Transferir uma chamada

  - Encaminhar uma chamada de entrada

  - Colocar chamadas em espera

  - Alternar entre várias chamadas simultâneas

  - Atender uma segunda chamada enquanto está em uma chamada (isso é, chamada em espera)

  - Discar dígitos DTMF

  - Na janela Conversa, digite observações no programa de anotações Microsoft Office OneNote

Além disso, quando um usuário é habilitado para controle de chamada remota, o Lync 2013 fornece ao usuário as seguintes informações de chamada:

  - Identificação de um chamador por nome quando o número de telefone do chamador existe na lista de contatos de um cliente de mensagens e colaboração do Microsoft Office Outlook habilitado para controle de chamada remota, lista de contatos do Lync ou GAL da sua organização.

  - Chamadas de entrada e saída antigas, que são salvas na pasta Histórico da Conversa no Outlook.

  - Notificações de chamadas perdidas, que são enviadas para a pasta caixa de entrada do Outlook do usuário, mas são geradas somente se o Lync estiver em execução quando a chamada de entrada for recebida.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Controle de Chamada Remota e Enterprise Voice

Embora os recursos de controle de chamada remota sejam separados dos recursos do Enterprise Voice e os usuários não possam ser habilitados para ambos, o Enterprise Voice oferece um subconjunto de recursos que também estão disponíveis para os usuários que estão habilitados para controle de chamada remota. Se o Enterprise Voice for implantado, os usuários habilitados para controle de chamada remota poderão usar o Lync para acessar os seguintes recursos do Enterprise Voice:

  - Fazer e receber chamadas de áudio para outro cliente Lync

  - Ingressar na parte de áudio de uma conferência criada por um usuário habilitado para o Enterprise Voice

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Tarefas de implantação para o controle de chamada remota no Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

