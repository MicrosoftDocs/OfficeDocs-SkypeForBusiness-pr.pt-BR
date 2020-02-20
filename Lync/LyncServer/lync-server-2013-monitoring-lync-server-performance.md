---
title: 'Lync Server 2013: monitorando o desempenho do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb8f57d25f02102cd407a320ffc11f3e8ff9497c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a>Monitorar o desempenho do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-15_

O desempenho do Lync Server 2013 é afetado por vários fatores, como perfis de usuário, arquitetura do sistema, software, componentes de hardware, pontos de integração de terceiros, como gateways e equipamentos de telefonia, conectividade e desempenho da rede, Windows Configuração e desempenho do serviço do Active Directory além da funcionalidade do sistema operacional Windows.

No núcleo de um desempenho de implantações do Lync Server 2013 é o software do servidor e o hardware em que ele é implementado. Por exemplo, um servidor front-end deve ter recursos de hardware suficientes para lidar com a carga de usuário esperada (de curto prazo). Se for necessário ter um servidor front-end para fornecer serviços a 10000 usuários, um servidor configurado adequadamente deverá atender aos requisitos de carga esperados para ajudar a garantir a melhor experiência possível para o usuário final.

Portanto, o desempenho do Monitoring Server é extremamente importante para avaliar se a infraestrutura de servidor implementada tem recursos de hardware adequados para os requisitos de carga de pico diários. O monitoramento do desempenho do servidor ajuda a identificar gargalos no sistema, permitindo que os administradores apliquem ações corretivas antes da experiência do usuário final ser afetada. Os dados de desempenho devem ser usados para o planejamento de capacidade de longo prazo.

Enquanto informações detalhadas sobre todos os objetos de desempenho e contadores a serem observados estão vinculadas ao [monitoramento do Lync Server 2013 com o System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), alguns contadores de desempenho que você deve seguir podem fornecer aos administradores uma rápida visualização do desempenho do sistema:

  - Para controlar a integridade geral do sistema do servidor front-end, um bom ponto de partida é verificar\\o processador% tempo do processador. O valor deve estar sempre abaixo de 80%.

  - Para acompanhar o desempenho da instância do software de banco de dados back-end do SQL Server usada pelo pool de front-ends, monitore os seguintes contadores de desempenho:
    
    LC: USrv – 00 – DBStore\\USrv – 002 – latência de fila (MS)
    
    LC: USrv – 00 – DBStore\\USrv – 0 04 – latência de SPROC (MS)
    
    O servidor íntegro em estado Steady deve mostrar \<100 valores de latência MS. O mecanismo de limitação se deparará quando a latência atingir 12 segundos, o que significa que o servidor front-end inicia as solicitações de limitação para o back-end. Isso faz com que os clientes comecem a receber uma mensagem de erro do servidor 503 que esteja ocupado.

  - Para controlar o tempo de processamento no servidor front-end, monitore o seguinte contador:
    
    LC: SIP-07-gerenciamento\\de carga SIP-000-tempo médio de retenção para mensagens de entrada
    
    Este é outro mecanismo de limitação nos servidores front-end, desde o momento em que o tempo de processamento no front-end é alto. Se o tempo médio de processamento for de mais de seis segundos, o servidor entrará no modo de limitação e permitirá apenas uma transação pendente por conexão do cliente.

  - Para rastrear problemas de memória no servidor back-end SQL, monitore o seguinte contador:
    
    Expectativa de vida da\\página do Gerenciador de buffer do SQL Server
    
    Um valor baixo, abaixo de 3600 segundos (junto com gravações de alta latência/s e páginas de ponto de verificação/seg) indica pressão de memória.

<div>

## <a name="additional-counters-to-view"></a>Contadores adicionais para exibir

Há vários contadores principais que são bons indicadores de integridade geral do servidor front-end. Esta não é uma lista abrangente e não se destina a identificar a causa raiz. Esses contadores permitirão realizar uma verificação rápida da integridade do servidor. Recomendamos verificar esses contadores em cada um dos servidores do pool. É importante entender quais são esses valores de contador quando o servidor está íntegro. É necessário ter uma linha de base para entender o que mudou quando a experiência do usuário é reduzida.

O servidor front-end pode indicar problemas que podem ser causados por afunilamentos em qualquer lugar no sistema. Isso significa que esse é o melhor lugar para começar a verificar a integridade geral do sistema.

Dois contadores adicionais a serem revisados primeiro são os seguintes:

LC: USrv-00-DBStore\\USrv-002-latência de fila (MS)

LC: USrv-00-DBStore\\USrv-004-SPROC latência (msec)

O contador de latência de fila representa o tempo que uma solicitação gastou na fila para o back-end e a latência SPROC representa o tempo necessário para que o back-end processe a solicitação. Se, por qualquer motivo, disco, memória, rede e processador no back-end estiverem em problemas, o contador de latência de fila será alto.

Também pode ser alto se houver alta latência de rede entre o front-end e o back-end. Então, o que é latência de fila aceitável?

Em 12 segundos, os servidores front-end iniciam solicitações de limitação para os servidores de back-end. Isso significa que os servidores começam a retornar o servidor muito ocupado – 503 erros para os clientes. Um servidor saudável deve ter menos de 100 ms DBStore latência de fila no estado Steady, mas, durante o tempo em que o servidor acabou de ficar online e os usuários estão todos fazendo logon ao mesmo tempo, esse contador pode ser muito alto e você pode até ver vários segundos.

Você pode ter uma configuração de balanceamento de carga, onde você tem um pool implantado com vários servidores front-end e um balanceador de carga que é configurado para "número mínimo de conexões". Nesse caso, se um servidor front-end for reiniciado, todos os usuários que tentarem se reconectar serão apontados para o servidor reiniciado, porque esse servidor terá menos conexões em comparação com os outros membros do pool. Durante esse período, o servidor front-end correspondente pode ser sobrecarregado enquanto os outros membros do pool não são.

Recomendamos que você execute a manutenção fora do expediente para reduzir o desempenho, pois os usuários não estarão competindo a se conectar ao servidor ao mesmo tempo.

Se os dois contadores de desempenho anteriores forem altos, o afunilamento mais provável é o servidor back-end do SQL. Os próximos componentes a serem confirmados são os seguintes:

  - A CPU do SQL Server está muito alta? Por exemplo, é maior que 80%?

  - A latência de disco é alta?

Em um mundo ideal, você tem RAM suficiente para os bancos de dados do RTC e do RTCDYN na memória. Em seguida, a única razão pela qual o servidor está acessando o disco é gravar nos arquivos de log e esvaziar os bancos de dados. Os testes mostraram que 12 GB de RAM são suficientes para implantações de usuário de 100.000. Isso pressupõe que os bancos de dados do RTC e do RTCDYN tenham menos de 12 GB. Se os bancos de dados forem maiores que isso, talvez você precise de memória adicional.

Você pode determinar se o SQL Server requer RAM adicional examinando o contador de desempenho de expectativa de vida da página do Gerenciador de buffer do SQL Server. Um valor menor que 3.600 indica pressão de memória. Você também deve ver pouco ou nenhuma leitura em sua unidade de banco de dados se você tiver memória suficiente, pois o SQL Server só deve ser gravado no banco de dados.

Há um mecanismo de limitação adicional em um servidor front-end do Lync Server 2013 que é iniciado se o tempo de processamento do servidor for alto. A limitação de latência do DBStore só será habilitada se a latência para o SQL Server for alta. Um exemplo no qual essa limitação está habilitada é se o servidor front-end estiver vinculado à CPU.

Se o tempo médio de processamento **(LC: SIP-07-Load\\Management SIP-000-tempo médio de retenção para mensagens de entrada)** no servidor exceder seis segundos, o servidor entra no modo de limitação e só fornece aos usuários uma transação pendente por conexão do cliente. Depois que o tempo de processamento cai para três segundos, o servidor descarta o modo de limitação e oferece aos usuários até 20 transações pendentes por conexão do cliente. Sempre que o número de transações em uma conexão específica exceder o limite acima, a conexão será marcada como fluxo controlado. O resultado é o servidor não publica os recebimentos nele, e o contador de **conexões controladas por fluxo de\\SIP-01-Peers** é incrementado. Se uma conexão permanecer em um Estado controlado por fluxo por mais de um minuto, o servidor a fechará. Ele faz isso de forma ociosa. Quando ele tem uma oportunidade de verificar a conexão, ele determina se ele foi limitado por muito tempo e o fechará se tiver mais de um minuto.

Estes são os dois mecanismos de limitação e há um contador de desempenho que resume o que, se houver, a limitação do servidor está executando.

**LC: SIP-04-respostas\\sip-053-local 503/seg**

  - O termo "local" no contador anterior se refere a respostas geradas localmente.

  - O código 503 corresponde ao servidor indisponível, onde você não deve ver nenhum código 503 em um servidor saudável. Durante o período após um servidor ser colocado online, você pode ver alguns códigos de 503. Quando todos os usuários entram novamente e o servidor retorna a um estado estável, não deve haver nenhum código 503 adicional.

**LC: SIP-04-respostas\\sip-074-local 504/seg**

Este contador de desempenho indica problemas de conectividade com outros servidores e pode indicar falhas de conexão ou atrasos na conexão. Se você estiver vendo erros 504, o contador de desempenho a seguir deve ser verificado.

**LC: SIP-01-Peers\\SIP-017-envios pendentes**

Este contador indica o número de solicitações e respostas enfileiradas de saída. Se esse contador for alto, o problema provavelmente não está no servidor local. Observe que esse contador pode ser alto se houver problemas de latência de rede. Ele também pode indicar problemas com o adaptador de rede local, mas é mais provável que seja causado por um problema em um servidor remoto. Esse contador provavelmente seria alto em um servidor de diretor quando o pool com o qual ele está tentando se comunicar está sobrecarregado. A chave com esse contador é examinar as instâncias, e não apenas o total.

</div>

</div>

<span> </span>

</div>

</div>

</div>

