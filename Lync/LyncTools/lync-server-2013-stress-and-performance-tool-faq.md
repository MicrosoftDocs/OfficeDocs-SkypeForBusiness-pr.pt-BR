---
title: Perguntas frequentes sobre a ferramenta de stress e desempenho do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Perguntas frequentes sobre a ferramenta de stress e desempenho do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Perguntas frequentes

Aqui estão algumas perguntas frequentes sobre a ferramenta de stress e desempenho do Lync Server 2013.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>É possível executar o LyncPerfTool. exe na produção?

Não recomendamos isso. Essa ferramenta afetará o desempenho do servidor, a segurança e a experiência do usuário.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>Estou me conectando aos meus usuários pela primeira vez. Por que os servidores estão em execução em alta carga?

Na primeira vez que os usuários fazem logon, há operações adicionais que ocorrem. Como resultado, o desempenho no servidor back-end do Microsoft SQL Server será degradado. Recomendamos que você execute um teste curto que Registre todos os usuários e reinicie os clientes antes de medir os resultados. Não há suporte para mais de 12 sessões de logon de usuários simultâneas por segundo, mas isso depende da configuração do hardware.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meus clientes estão ficando sem memória. O que devo fazer?

Se os seus clientes estiverem ficando sem memória, você precisará reduzir o número de usuários por computador.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>Meus clientes estão em 100% de CPU o tempo todo. O que devo fazer?

Se seus clientes estiverem sendo executados com uma CPU muito alta depois que todos os usuários estiverem conectados, você precisará reduzir o número de usuários por computador. Altos picos de CPU são aceitáveis, mas se estiverem estáveis, você precisará reduzir a carga.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>É possível executar a ferramenta no próprio servidor?

Não. Não há suporte para esse cenário e pode falhar devido a uma incompatibilidade binária. Além disso, como o ponto é medir o consumo de recursos no servidor, executar a ferramenta não renderizaria as medidas sem significado.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>É possível executar o LyncPerfTool. exe em um servidor virtual ou no Microsoft Hyper-V Server 2008/2012?

Sim.

</div>

<div>

## <a name="what-does-mpop-mean"></a>O que significa MPOP?

MPOP significa vários pontos de presença. Destina-se a simular o cenário em que os usuários estão conectados ao Lync 2013 de várias máquinas. Observe que em LyncPerfTool. exe, cada ponto de extremidade usa o perfil padrão (ou seja, o perfil não é dividido entre os dois pontos de presença).

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Comecei LyncPerfTool. exe, mas nada está acontecendo. O que está acontecendo?

Verifique o contador total de pontos de extremidade ativos nos clientes para ver se os usuários estão se conectando. Se os usuários não estiverem se conectando, verifique a configuração do Lync Server 2013. Geralmente, esse problema ocorre porque o nome do servidor, o prefixo do usuário ou a senha estão incorretos. Observe que os clientes externos devem especificar o proxy de acesso como o valor TargetServer. Verifique a porta no arquivo de configuração.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>Como posso saber se algo está acontecendo?

Os vários contadores de desempenho do LyncPerfTool indicam se os usuários estão se conectando e executando ações. No entanto, uma maneira fácil de verificar é fazer logon em uma das contas usando o Lync 2013 e executando a ação desejada.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Tenho ferramentas de planejamento de capacidade do Live Communications Server 2007 R2 e/ou Lync Server 2010 instaladas. Isso é tudo OK?

Não. Há problemas de interoperabilidade, e você deve desinstalar todas as versões anteriores deste produto.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>As ferramentas de stress e desempenho configuram a CAA Call Information Server Topology?

Não. As ferramentas apenas criam usuários, contatos e listas de distribuição e simulam a carga do usuário.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual é o número máximo de usuários com suporte para as ferramentas?

Criamos até um total de 80.000 usuários e executamos testes totalizando 30.000 usuários, usando essas ferramentas. Sugerimos um máximo de 120.000 usuários, embora as limitações técnicas permitam um valor mais alto, dependendo do hardware do cliente e do servidor disponível.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

