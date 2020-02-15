---
title: Perguntas frequentes sobre a ferramenta de desempenho e stress do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9de9555f9f009558b700a32ca6e58059eb5ea990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Perguntas frequentes sobre a ferramenta de desempenho e stress do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Perguntas Frequentes

Aqui estão algumas perguntas frequentes sobre a ferramenta de estresse e desempenho do Lync Server 2013.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>Posso executar o LyncPerfTool. exe em produção?

Não recomendamos isso. Essa ferramenta afetará o desempenho do servidor, segurança e experiência do usuário.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>Estou fazendo logon em meus usuários pela primeira vez. Por que os servidores estão sendo executados em alta carga?

Na primeira vez que os usuários fazem logon, há operações adicionais que ocorrem. Como resultado, o desempenho no servidor back-end do Microsoft SQL Server será degradado. Recomendamos que você execute um teste curto que faça logon em todos os usuários e reinicie os clientes antes de medir os resultados. Não há suporte para mais de 12 sessões de logon de usuário simultâneas por segundo, mas isso depende da configuração do hardware.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meus clientes estão ficando sem memória. O que devo fazer?

Se os seus clientes estiverem ficando sem memória, você precisa reduzir o número de usuários por computador.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>Meus clientes estão em 100% de CPU o tempo todo. O que devo fazer?

Se os seus clientes estiverem em execução com uma CPU muito alta depois que todos os usuários estiverem conectados, você precisará reduzir o número de usuários por computador. Altos picos de CPU são aceitos, mas se estiverem estáveis, você precisará reduzir a carga.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>Posso executar a ferramenta no próprio servidor?

Não. Este cenário não é suportado e pode falhar devido a uma incompatibilidade binária. Além disso, como o ponto é medir o consumo de recursos no servidor, a execução da ferramenta não renderizaria as medições sem sentido.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Posso executar o LyncPerfTool. exe em um servidor virtual ou no Microsoft Hyper-V Server 2008/2012?

Sim.

</div>

<div>

## <a name="what-does-mpop-mean"></a>O que significa MPOP?

MPOP significa vários pontos de presença. Destina-se a simular o cenário em que os usuários estão conectados ao Lync 2013 de várias máquinas. Observe que, no LyncPerfTool. exe, cada ponto de extremidade usa o perfil padrão (ou seja, o perfil não é dividido entre os dois pontos de presença).

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Iniciei o LyncPerfTool. exe, mas nada aconteceu. O que está acontecendo?

Verifique o contador total de pontos de extremidade ativos nos clientes para ver se os usuários estão se conectando. Se os usuários não estiverem se conectando, verifique a configuração do Lync Server 2013. Esse problema geralmente ocorre porque o nome do servidor, o prefixo do usuário ou a senha está incorreto. Observe que os clientes externos devem especificar o proxy de acesso como o valor TargetServer. Verifique a porta no arquivo de configuração.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>Como saber se algo está acontecendo?

Os vários contadores de desempenho do LyncPerfTool indicam se os usuários estão se conectando e executando ações. No entanto, uma maneira fácil de verificar é fazer logon em uma das contas usando o Lync 2013 e executando a ação desejada.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Possuo ferramentas de planejamento de capacidade do Live Communications Server 2007 R2 e/ou o Lync Server 2010 instalado. Isso é tudo certo?

Não. Há problemas de interoperabilidade, e você deve desinstalar todas as versões anteriores deste produto.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>As ferramentas de estresse e desempenho definirão a topologia do servidor de informações de chamadas do CAA?

Não. As ferramentas apenas criam usuários, contatos e listas de distribuição e simulam a carga do usuário.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual é o número máximo de usuários que as ferramentas dão suporte?

Nós criamos até um total de 80.000 usuários e executamos testes totalizando 30.000 usuários, usando essas ferramentas. Sugerimos um máximo de 120.000 usuários, embora as limitações técnicas permitam um valor maior, dependendo do hardware do cliente e do servidor disponível.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

