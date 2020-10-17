---
title: 'Lync Server 2013: Iniciando o processo de planejamento'
description: 'Lync Server 2013: Iniciando o processo de planejamento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa46d660ca60538f87c570dd2d7667afd23c609
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552297"
---
# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Iniciando o processo de planejamento do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-24_

Embora o planejamento de uma implantação de comunicações unificadas local possa parecer intimidador, o Lync Server fornece duas ferramentas valiosas para ajudá-lo a:

  - **A ferramenta de planejamento** é um assistente que apresenta uma série de perguntas sobre sua organização, os recursos do Lync Server que você deseja habilitar e suas necessidades de planejamento de capacidade. Em seguida, ele cria uma topologia de implantação recomendada com base nas suas respostas e produz um diagrama do Microsoft Visio dessa implantação.

  - O **Construtor de topologias** é um componente de instalação do Lync Server. Use o construtor de topologias para criar, ajustar e publicar sua topologia planejada. Ele também valida sua topologia antes de iniciar as instalações do servidor. Quando você instala o Lync Server em servidores individuais, os servidores lêem a topologia publicada como parte do processo de instalação e o programa de instalação implanta o servidor conforme indicado na topologia.

<div>

## <a name="lync-server-planning-tool"></a>Ferramenta de planejamento do Lync Server

A ferramenta de planejamento leva suas respostas às perguntas da ferramenta e gera uma topologia com base nas diretrizes e nas práticas recomendadas do Lync Server. Ele também fornece vários modos de exibição de uma implantação com base nas suas respostas. Ele mostra um modo de exibição global de todos os sites (ou seja, incluindo sites centrais e sites de filial) e exibições detalhadas mostrando os servidores e outros componentes em cada site.

A execução da ferramenta de planejamento não compromete você com nenhuma implantação específica ou inicia nenhum processo. Na verdade, a execução da ferramenta de planejamento mesmo antes de ter um plano de firma em mente pode ser uma maneira bastante orientada de compreender os tipos de perguntas que você precisa pensar no seu processo de planejamento.

Você pode executar a ferramenta de planejamento várias vezes, respondendo a perguntas de forma diferente e comparando os resultados. Se você tiver um design com o qual você está mais satisfeito, mas precisar fazer alterações no, poderá retornar à ferramenta de planejamento, carregar o design e fazer as alterações. É necessário cerca de 15 minutos para concluir a ferramenta de planejamento uma vez.

Depois de estar satisfeito, você poderá usar a ferramenta de planejamento para criar um diagrama da implantação planejada. Você pode usar esse diagrama ao criar a implantação no construtor de topologias.

<div>


> [!NOTE]  
> A ferramenta de planejamento incluída nesta versão do Lync Server 2013 é uma versão de pré-lançamento. Observe que os números de planejamento de capacidade na ferramenta de planejamento são preliminares e não têm suporte para a versão final.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Construtor de topologias do Lync Server

Depois de decidir o plano de implantação, use o construtor de topologias para começar a implantar o. Quando terminar, você usará o construtor de topologias para validar a topologia e, em seguida, se ele passar, você poderá publicar a topologia. Quando você publica a topologia, o Lync Server coloca a topologia no repositório de gerenciamento central, que é criado neste momento, caso ainda não exista. Ao instalar o Lync Server em cada servidor em sua implantação, o servidor lê a topologia do repositório de gerenciamento central e instala-se para se ajustar à sua função na sua implantação.

Como alternativa, se você estiver familiarizado com o Lync Server e precisar de menos orientações prescritivas, poderá ignorar a ferramenta de planejamento e usar os assistentes no construtor de topologias para o design inicial da sua implantação e também para as etapas de validação e publicação.

O uso do construtor de topologias para planejar e publicar uma topologia é uma etapa obrigatória. Você não pode ignorar o construtor de topologias e instalar o Lync Server individualmente nos servidores da sua implantação. Cada servidor deve ler a topologia de uma topologia validada e publicada no repositório de gerenciamento central.

</div>

<div>

## <a name="high-level-planning-process"></a>Processo de planejamento de High-Level

Recomendamos o seguinte processo geral para usar a documentação e a ferramenta de planejamento para planejar a implantação do Lync Server.

1.  Se você estiver familiarizado com versões anteriores do Lync Server, leia os [novos recursos no Lync server 2013](lync-server-2013-new-features.md) para se familiarizar com os novos recursos e requisitos no lync Server 2013.

2.  Leia os outros tópicos nesta seção da documentação: [noções básicas de topologia que você deve saber antes de planejar o Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), as [topologias de referência no Lync Server 2013](lync-server-2013-reference-topologies.md), as [decisões iniciais de planejamento do Lync Server 2013](lync-server-2013-initial-planning-decisions.md)e [clientes para Lync Server 2013](lync-server-2013-clients.md). Observe as decisões de planejamento representadas em [topologias de referência no Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Agora que você está mais familiarizado com os recursos do Lync Server e os tipos de perguntas que devem ser respondidas, execute a ferramenta de planejamento e visualize a topologia resultante e seus detalhes. Certifique-se de que a topologia atenda aos requisitos exclusivos para sua organização.

4.  Se houver cargas de trabalho ou recursos específicos nos quais você está interessado ou precisar de mais informações, leia as seções apropriadas de [planejamento do Lync Server 2013](lync-server-2013-planning.md).

5.  Execute a ferramenta de planejamento novamente. Você pode começar com a implantação que você criou na etapa 3 e modificar os resultados ou recomeçar desde o início.
    
    Se necessário, execute a ferramenta de planejamento uma terceira vez e repita até que esteja satisfeito com a saída.

6.  Depois de finalizar o plano de topologia, use a ferramenta de planejamento para criar e imprimir um diagrama do Visio da sua topologia. Você pode usar essa impressão ao trabalhar com o construtor de topologias para inserir sua topologia.

7.  Antes de começar a implantação, leia [determinando os requisitos de sistema do Lync server 2013](lync-server-2013-determining-your-system-requirements.md) e [determinando seus requisitos de infraestrutura para o Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) para se familiarizar com os pré-requisitos e a infraestrutura necessária para o Lync Server. Além disso, certifique-se de ter lido todas as seções de [planejamento do Lync Server 2013](lync-server-2013-planning.md) que se aplicam às cargas de trabalho e aos recursos que você planeja implantar.

</div>

<div>

## <a name="migrating-from-previous-versions"></a>Migrando de versões anteriores

Se você estiver migrando para o Lync Server a partir de uma versão anterior, consulte a documentação de [migração](migration.md) para obter instruções específicas para sua migração e implantação.

</div>

</div>

<span> </span>

</div>

</div>

</div>

