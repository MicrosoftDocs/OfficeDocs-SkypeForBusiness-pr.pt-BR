---
title: 'Lync Server 2013: Iniciar serviços nos servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee5e58f316acde9e1aadeee80cfccb6ee1b189be
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Iniciar serviços em servidores para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-09-03_

Para concluir com êxito este procedimento, você deve estar conectado como um usuário que seja membro do grupo RTCUniversalServerAdmins ou com as permissões delegadas corretas. Para obter detalhes sobre como delegar permissões, consulte o tópico [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Após instalar o repositório de configuração local em seus servidores, instalar os componentes do Lync Server 2013 e configurar certificados em um servidor front-end ou servidor front-end, você deve iniciar os serviços do Lync Server 2013 no servidor. Use o procedimento a seguir para iniciar os serviços em cada servidor de front-end em sua implantação.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Para iniciar os serviços em um servidor Standard Edition ou front-end

1.  No assistente de implantação do Lync Server, na página **Lync server 2013** , clique em **executar** ao lado de **etapa 4: Iniciar serviços**.

2.  Na página **Iniciar serviços** , clique em **Avançar** para iniciar os serviços do Lync Server no servidor.

3.  Na página **Executando comandos**, após todos os serviços serem iniciados com sucesso, clique em **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > O comando para iniciar os serviços no servidor é o melhor método para relatar que os serviços foram realmente iniciados. Talvez ele não reflita o estado real do serviço. Recomendamos o uso da etapa <STRONG>Status do Serviço (Opcional)</STRONG> imediatamente após <STRONG>Iniciar Serviços</STRONG> para abrir o MMC (Console de Gerenciamento da Microsoft) e confirmar se os serviços foram iniciados com êxito. Se algum serviço do Lync Server não tiver começado, clique com o botão direito do mouse no serviço no MMC e, em seguida, clique em <STRONG>Iniciar</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

