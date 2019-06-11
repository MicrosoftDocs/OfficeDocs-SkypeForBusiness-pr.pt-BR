---
title: 'Lync Server 2013: visão geral do aplicativo Announcement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e9cedddf6dfdf714bb3d0eef0e0cd01063b89f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Visão geral do aplicativo de anúncio no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-13_

Ao implantar o aplicativo de anúncio, você precisa configurar uma tabela de número não atribuído que determine a ação a ser tomada quando alguém discar um número não atribuído. A tabela número não atribuído contém intervalos de números de telefone que são válidos para a organização e especifica qual aplicativo de anúncio manipula cada intervalo. Quando um chamador disca para um número de telefone válido para a sua organização, mas não está atribuído a ninguém, o Lync Server procura o número na tabela de roteamento de números não atribuídos, identifica o intervalo no qual o número cai e roteia a chamada para o anúncio aplicativo especificado para esse intervalo. O aplicativo de anúncio atende a chamada e reproduz uma mensagem de áudio (se você a configurou para fazer isso) e, em seguida, desconectará a chamada ou a transferirá para um destino predeterminado, por exemplo, para um operador. Você pode usar cmdlets do Shell de gerenciamento do Lync Server para configurar várias mensagens de áudio ou para transferir destinos.

A forma como você configura a tabela de número não atribuído depende de como você deseja usá-la. Se você possui números específicos que não estão mais em uso e deseja reproduzir mensagens que são personalizadas para cada número, é possível inserir esses números específicos na tabela de número não atribuído. Por exemplo, se você alterou o número do seu atendimento ao cliente, é possível inserir o número do serviço antigo e associá-lo a um anúncio que oferece o novo número. Se você deseja reproduzir uma mensagem geral para qualquer pessoa que ligar para um número não atribuído, como funcionários que deixaram a organização, é possível inserir intervalos para todas as extensões válidas em sua organização. A tabela de número não atribuído é invocada sempre que um chamador liga para um número que não está atribuído atualmente.

No Lync Server 2013, o aplicativo de anúncio é instalado automaticamente com o aplicativo de grupo de resposta. Os aplicativos de anúncio e de grupo de resposta são componentes padrão de uma implantação do Enterprise Voice: ao implantar o Enterprise Voice, esses dois aplicativos são implantados automaticamente.

</div>

<span> </span>

</div>

</div>

</div>

