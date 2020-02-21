---
title: 'Lync Server 2013: visão geral do estacionamento de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1624042b07bc024d837e55ffac402cb2f158922f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Visão geral do estacionamento de chamada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

O aplicativo de estacionamento de chamada do Lync Server 2013 permite que os usuários do Enterprise Voice realizem qualquer um dos seguintes procedimentos:

  - Colocar uma chamada em espera e, em seguida, recuperar a chamada do mesmo telefone ou de outro telefone.

  - Colocar uma chamada em espera para transferi-la para um departamento ou área geral (por exemplo, para um departamento de vendas ou um depósito onde há um telefone de área comum).

  - Colocar uma chamada em espera e manter o telefone de resposta original livre para outras chamadas.

Quando um usuário armazena uma chamada, o Lync Server transfere a chamada para um número temporário, chamado de *órbita*, onde a chamada é mantida até que seja recuperada ou o tempo limite se esgote. O Lync Server envia a órbita para o usuário que estaciona a chamada. Para recuperar a chamada estacionada, o usuário pode discar o número de órbita ou clicar no botão ou link de órbita na janela de conversa.

O usuário que estaciona uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas (IM) ou um sistema de paginação, para comunicar o número de órbita a outra pessoa. O usuário que estacionau a chamada pode deixar a janela de conversa aberta para receber uma notificação quando a chamada é recuperada.

Como os intervalos de órbita são globalmente exclusivos, é possível recuperar chamadas de qualquer site do Lync Server ou telefone PBX se o roteamento for configurado adequadamente. Se ninguém recuperar a chamada dentro de um período configurável, a chamada tocará de volta para a pessoa que o estacionasse. Se essa pessoa não atender ao retorno de toque, a chamada será transferida para um destino de fallback, como um operador, se configurada. Você pode configurar o número de vezes que a chamada toca antes de ser transferida de uma a dez vezes. Se ninguém responder a uma chamada transferida, a chamada será desconectada. A órbita é liberada quando a chamada é recuperada ou desconectada.

Ao implantar o estacionamento de chamadas, você precisa reservar intervalos de números de ramal para o estacionamento de chamadas. Essas extensões precisam ser extensões virtuais: extensões que não têm nenhum usuário ou telefone atribuído a elas. Em seguida, você configura a tabela de órbita de estacionamento de chamada com os intervalos de números de ramal e especifica qual serviço de aplicativo hospeda o aplicativo de estacionamento de chamada que lida com cada intervalo. Cada pool de front-ends tem uma tabela de estacionamento de chamada no servidor back-end correspondente, que é usado para gerenciar chamadas estacionadas no pool. A lista de intervalos de órbita é armazenada no repositório de gerenciamento central e é usada para rotear órbitas para o pool de destino. Cada pool do Lync Server onde o aplicativo de estacionamento de chamada é implantado e configurado pode ter um ou mais intervalos de órbita. Os intervalos de órbita devem ser globalmente exclusivos na implantação do Lync Server.

Você também define outras configurações de estacionamento de chamadas, como onde as chamadas são redirecionadas se o tempo limite se esgotarem e se a pessoa no telefone ouvirá música enquanto estacionada. Você também pode especificar o arquivo de música a ser tocado enquanto a chamada está em espera.

<div>


> [!NOTE]  
> Arquivos de música em espera personalizados para estacionamento de chamadas não são incluídos no backup como parte do processo de recuperação de desastres do Lync Server 2013 e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados. Mantenha sempre uma cópia de backup separada dos arquivos de música em espera personalizados que você carregou para o estacionamento de chamadas.



</div>

O aplicativo de estacionamento de chamada é um componente do Enterprise Voice. Quando você implanta o Enterprise Voice, o aplicativo de estacionamento de chamada é instalado e ativado automaticamente. No entanto, antes de poder usar o estacionamento de chamada, o administrador do Enterprise Voice deve configurá-lo e habilitá-lo para os usuários por meio da política de voz.

</div>

<span> </span>

</div>

</div>

</div>

