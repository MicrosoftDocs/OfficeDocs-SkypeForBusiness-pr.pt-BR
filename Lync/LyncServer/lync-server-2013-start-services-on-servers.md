---
title: 'Lync Server 2013: Iniciar serviços nos servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c0c14aea9966e61703e85dd2aff8a2e448d5eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Iniciar serviços nos servidores para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-09-03_

Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins ou ter as permissões corretas delegadas. Para obter detalhes sobre como delegar permissões, consulte o tópico [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Depois de instalar o repositório de configuração local em seus servidores, instalar os componentes do Lync Server 2013 e configurar certificados em um servidor front-end ou servidor front-end, você deve iniciar os serviços do Lync Server 2013 no servidor. Use o procedimento a seguir para iniciar serviços em cada servidor front-end na sua implantação.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Para iniciar serviços em um servidor Standard Edition ou front-end

1.  No assistente de implantação do Lync Server, na página do **Lync server 2013** , clique em **executar** ao lado da **etapa 4: Iniciar serviços**.

2.  Na página **Iniciar serviços** , clique em **Avançar** para iniciar os serviços do Lync Server no servidor.

3.  Na página **Executando comandos**, depois que todos os serviços forem iniciados com sucesso, clique em **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > O comando para iniciar os serviços no servidor é um método de melhor esforço para informar que os serviços têm na verdade iniciado. Ele pode não refletir o estado real do serviço. Recomendamos que você use o status do serviço de etapa <STRONG>(opcional)</STRONG> imediatamente depois de <STRONG>Iniciar serviços</STRONG> para abrir o console de gerenciamento Microsoft (MMC) e confirmar se os serviços foram iniciados com êxito. Se algum serviço do Lync Server não tiver começado, você pode clicar com o botão direito do mouse no serviço do MMC e, em seguida, clicar em <STRONG>Iniciar</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

