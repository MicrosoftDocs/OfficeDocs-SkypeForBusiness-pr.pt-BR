---
title: 'Lync Server 2013: visão geral do aplicativo comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0bceaef7a165f4594d825a80b93ee167b68c85a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520808"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Visão geral do aplicativo comunicado no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-13_

Ao implantar o aplicativo de comunicado, você precisa configurar uma tabela de número não atribuído que determina a ação a ser tomada quando alguém discar um número não atribuído. A tabela de número não atribuído contém intervalos de números de telefone válidos para a organização e especifica qual aplicativo de anúncio lida com cada intervalo. Quando um chamador disca um número de telefone válido para sua organização, mas não é atribuído a qualquer pessoa, o Lync Server pesquisa o número na tabela de roteamento de número não atribuído, identifica o intervalo no qual o número cairá e roteia a chamada para o aplicativo de anúncio especificado para esse intervalo. O aplicativo de anúncio responde à chamada e reproduz uma mensagem de áudio (se você a configurou para isso) e, em seguida, desconecta a chamada ou a transfere para um destino predeterminado, como para um operador. Você pode usar os cmdlets do Shell de gerenciamento do Lync Server para configurar várias mensagens de áudio ou para transferir destinos.

Como você configura a tabela de número não atribuído depende de como você deseja usá-la. Se você possui números específicos que não estão mais em uso e deseja reproduzir mensagens que são personalizadas para cada número, é possível inserir estes números específicos na tabela de número não atribuído. Por exemplo, se você alterou o número do seu atendimento ao cliente, é possível inserir o número do serviço antigo e associá-lo com um anúncio que oferece o novo número. Se você deseja reproduzir uma mensagem geral para qualquer pessoa que ligar para um número não atribuído, como funcionários que deixaram a organização, é possível inserir intervalos para todas as extensões válidas em sua organização. A tabela de número não atribuído é invocada sempre que um ligador chama um número que não está atribuído atualmente.

No Lync Server 2013, o aplicativo de anúncio é instalado automaticamente com o aplicativo grupo de resposta. Os aplicativos de anúncio e de grupo de resposta são componentes padrão de uma implantação do Enterprise Voice: quando você implanta o Enterprise Voice, esses dois aplicativos são implantados automaticamente.

</div>

<span> </span>

</div>

</div>

</div>

