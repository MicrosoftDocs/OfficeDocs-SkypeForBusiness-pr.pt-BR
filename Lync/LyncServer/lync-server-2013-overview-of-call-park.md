---
title: 'Lync Server 2013: visão geral do parque de chamadas'
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
ms.openlocfilehash: c5deeff873b37c0056bf03c598c39e448cba4379
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Visão geral do estacionamento de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

O aplicativo do Lync Server 2013 Call Park permite que os usuários do Enterprise Voice realizem qualquer um destes procedimentos:

  - Colocar uma chamada em espera e recuperá-la no mesmo telefone ou em outro.

  - Colocar uma chamada em espera para transferi-la para um departamento ou área geral, por exemplo, um departamento de vendas ou um depósito onde há um telefone de área comum.

  - Colocar uma chamada em espera e manter o telefone original livre para outras chamadas.

Quando um usuário representa uma chamada, o Lync Server transfere a chamada para um número temporário, chamado de *órbita*, em que a chamada é mantida até ser recuperada ou expirada. O Lync Server envia a órbita para o usuário que estaciona a chamada. Para recuperar a chamada estacionada, o usuário pode discar o número de órbita ou clicar no link de órbita ou na janela de Conversação.

O usuário que estacionou uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas ou um sistema de paginação, para comunicar o número de órbita para outra pessoa. O usuário que estacionou a chamada pode deixar a janela de Conversação aberta para receber notificações quando a chamada for recuperada.

Como os intervalos de órbita são globalmente exclusivos, é possível recuperar chamadas de qualquer site do Lync Server ou de um telefone PBX se o roteamento estiver configurado apropriadamente. Se ninguém recuperar a chamada dentro do tempo configurável, a chamada tocará novamente para a pessoa que a estacionou. Se essa pessoa não atender, a chamada será transferida para um destino de fallback, como um operador, se assim estiver configurado. Você pode configurar o número de vezes que a chamada toca antes de ser transferida, entre uma a dez vezes. Se ninguém atender a chamada transferida, ela será desconectada. A órbita é liberada quando a chamada é recebida ou desconectada.

Quando você implanta o Estacionamento de Chamada, precisa reservar intervalos de números de extensão para estacionar as chamadas. Essas extensões precisam ser extensões virtuais: extensões que não têm nenhum usuário ou telefone atribuído. Você configura a tabela de órbitas do estacionamento de chamada com os intervalos de números de extensões e especifica qual serviço de Aplicativo hospeda o aplicativo de Estacionamento de Chamada que lida com cada intervalo. Cada pool de front-ends tem uma tabela parque de chamadas no servidor back-end correspondente usado para gerenciar chamadas estacionadas no pool. A lista de intervalos de órbita é armazenada no repositório de gerenciamento central e é usada para rotear órbitas para o pool de destino. Cada pool do Lync Server onde o aplicativo de estacionamento de chamada é implantado e configurado pode ter um ou mais intervalos de órbita. As faixas órbitas devem ser globalmente exclusivas entre a implantação do Lync Server.

Você também define outras configurações de Estacionamento de Chamada, como para onde as chamadas são redirecionadas quando atingem o tempo limite e se a pessoa ao telefone ouve música enquanto aguarda. Você também pode especificar o arquivo de música a ser reproduzido enquanto a chamada está em espera.

<div>


> [!NOTE]  
> Os arquivos personalizados de música em espera para o estacionamento de chamadas não fazem backup como parte do processo de recuperação de desastres do Lync Server 2013 e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados. Mantenha sempre uma cópia de backup separada dos arquivos de música de espera personalizados que você enviar ao Estacionamento de Chamada.



</div>

O aplicativo Estacionamento de Chamada é um componente do Enterprise Voice. Ao implantar o Enterprise Voice, o aplicativo de estacionamento de chamada é instalado e ativado automaticamente. No entanto, antes de poder usar o parque de chamadas, o administrador do Enterprise Voice deve configurá-lo e habilitá-lo para os usuários por meio da política de voz.

</div>

<span> </span>

</div>

</div>

</div>

