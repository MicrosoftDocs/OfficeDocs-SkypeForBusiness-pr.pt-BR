---
title: 'Lync Server 2013: Iniciando o processo de planejamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582769109a3792ddc2efdbef5d4a557b781c39b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Iniciando o processo de planejamento para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-24_

Ao planejar uma implantação de comunicação unificada local pode parecer intimidante, o Lync Server oferece duas ferramentas importantes para ajudá-lo a:

  - **A ferramenta de planejamento** é um assistente que apresenta uma série de perguntas sobre sua organização, os recursos do Lync Server que você deseja habilitar e suas necessidades de planejamento de capacidade. Em seguida, ele cria uma topologia de implantação recomendada com base nas suas respostas e produz um diagrama do Microsoft Visio dessa implantação.

  - O **Construtor** de topologias é um componente de instalação do Lync Server. Você usa o construtor de topologias para criar, ajustar e publicar sua topologia planejada. Ele também valida sua topologia antes de começar as instalações do servidor. Quando você instala o Lync Server em servidores individuais, os servidores lêem a topologia publicada como parte do processo de instalação, e o programa de instalação implanta o servidor conforme direcionado na topologia.

<div>

## <a name="lync-server-planning-tool"></a>Ferramenta de planejamento do Lync Server

A ferramenta de planejamento leva suas respostas às perguntas na ferramenta e gera uma topologia com base nas diretrizes do Lync Server e nas práticas recomendadas. Ele também fornece vários modos de exibição de uma implantação com base nas suas respostas. Ele mostra uma exibição global de todos os sites (ou seja, incluindo sites centrais e sites de filiais) e modos de exibição detalhados que mostram os servidores e outros componentes em cada site.

Executar a ferramenta de planejamento não compromete você a realizar uma implantação específica nem iniciará processos. Na verdade, executar a ferramenta de planejamento mesmo antes de ter um plano de confirmação em mente pode ser uma maneira bastante orientada para compreender os tipos de perguntas que você precisa pensar no processo de planejamento.

Você pode executar a ferramenta de planejamento várias vezes, responder a perguntas de maneira diferente e comparar os resultados. Se você tiver um design com o qual está mais satisfeito, mas precisar fazer alterações, poderá retornar à ferramenta de planejamento, carregar o design e fazer as alterações. É preciso cerca de 15 minutos para concluir a ferramenta de planejamento uma vez.

Depois de estar satisfeito, você pode usar a ferramenta de planejamento para criar um diagrama de sua implantação planejada. Você pode usar esse diagrama ao criar a implantação no construtor de topologias.

<div>


> [!NOTE]  
> A ferramenta de planejamento incluída nesta versão do Lync Server 2013 é uma versão de pré-lançamento. Observe que os números do planejamento de capacidade na Ferramenta de Planejamento são preliminares e não são aceitos na versão final.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Construtor de topologias do Lync Server

Depois de decidir em seu plano de implantação, você usará o construtor de topologias para começar a implantar. Ao terminar, você usa o construtor de topologias para validar a topologia e, em seguida, se ele passar, você poderá publicar a topologia. Quando você publica a topologia, o Lync Server coloca a topologia no repositório central de gerenciamento, que é criado no momento, caso ainda não exista. Quando você instala o Lync Server em cada servidor na sua implantação, o servidor lê a topologia do repositório de gerenciamento central e se instala para se encaixar em sua função na sua implantação.

Como alternativa, se você estiver familiarizado com o Lync Server e precisar de menos orientação prescritiva, ignore a ferramenta de planejamento e use os assistentes no construtor de topologias para o design inicial da sua implantação e também para as etapas de validação e publicação.

Usar o construtor de topologias para planejar e publicar uma topologia é uma etapa obrigatória. Você não pode ignorar o construtor de topologias e instalar o Lync Server individualmente nos servidores da sua implantação. Cada servidor deve ler a topologia de uma topologia publicada validada no repositório de gerenciamento central.

</div>

<div>

## <a name="high-level-planning-process"></a>Processo de planejamento de alto nível

Recomendamos o seguinte processo geral para usar a documentação e a ferramenta de planejamento para planejar a implantação do Lync Server.

1.  Se você estiver familiarizado com versões anteriores do Lync Server, leia os [novos recursos do Lync server 2013](lync-server-2013-new-features.md) para se familiarizar com os novos recursos e requisitos do lync Server 2013.

2.  Leia os outros tópicos desta seção da documentação: [noções básicas de topologia que você precisa saber antes de planejar o Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), topologias de [referência no Lync Server 2013](lync-server-2013-reference-topologies.md), [decisões iniciais de planejamento para o Lync Server 2013](lync-server-2013-initial-planning-decisions.md)e [ Clientes para Lync Server 2013](lync-server-2013-clients.md). Observe as decisões de planejamento representadas em [topologias de referência no Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Agora que você está mais familiarizado com os recursos do Lync Server e os tipos de perguntas que devem ser respondidas, execute a ferramenta de planejamento e veja a topologia resultante e seus detalhes. Certifique-se de que a topologia atenda aos requisitos exclusivos da sua organização.

4.  Se houver alguma carga de trabalho ou recurso em particular no qual você esteja interessado ou precisar de mais informações, leia as seções apropriadas de [planejamento para o Lync Server 2013](lync-server-2013-planning.md).

5.  Execute a ferramenta de planejamento novamente. Você pode começar com a implantação criada na etapa 3 e modificar os resultados ou começar do início.
    
    Se necessário, execute a ferramenta de planejamento uma terceira vez e repita até que você esteja satisfeito com a saída.

6.  Depois de finalizar o plano de topologia, use a ferramenta de planejamento para criar e imprimir um diagrama do Visio da sua topologia. Você pode usar esta cópia impressa enquanto trabalha com o construtor de topologias para inserir sua topologia.

7.  Antes de começar a implantação, leia [determinação dos requisitos do sistema do Lync server 2013](lync-server-2013-determining-your-system-requirements.md) e [determinação dos requisitos de infraestrutura do Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) para se familiarizar com os pré-requisitos e a infraestrutura necessária para o Lync Server. Além disso, certifique-se de ter lido todas as seções de [planejamento do Lync Server 2013](lync-server-2013-planning.md) que se aplicam às cargas de trabalho e aos recursos que você planeja implantar.

</div>

<div>

## <a name="migrating-from-previous-versions"></a>Migrando de versões anteriores

Se você estiver migrando para o Lync Server de uma versão anterior, consulte a documentação de [migração](migration.md) para obter instruções específicas para sua migração e implantação.

</div>

</div>

<span> </span>

</div>

</div>

</div>

