---
title: 'Lync Server 2013: monitorando o desempenho do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9610dddfa9748b7d28dfe040a36214f3f969826
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a>Monitorar o desempenho do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-15_

O desempenho do Lync Server 2013 é afetado por vários fatores, como perfis de usuário, arquitetura do sistema, software, componentes de hardware, pontos de integração de terceiros, como gateways e equipamento de telefonia, conectividade e desempenho de rede, Windows A configuração e o desempenho do serviço Active Directory além da funcionalidade do sistema operacional Windows.

No núcleo de uma implantação do Lync Server 2013, o desempenho é o software do servidor e o hardware em que ele é implementado. Como exemplo, um servidor front-end deve ter recursos de hardware suficientes para lidar com a carga de usuário esperada (de curto prazo). Se for necessário ter um servidor front-end para fornecer serviços aos usuários do 10000, um servidor configurado adequadamente deve atender aos requisitos de carga esperados para ajudar a garantir a melhor experiência de usuário final possível.

Portanto, o desempenho do monitoramento do servidor é extremamente importante para avaliar se a infraestrutura de servidor implementada tem recursos de hardware adequados para os requisitos do dia-a-dia da carga de pico. O monitoramento do desempenho do servidor ajuda a identificar gargalos do sistema, permitindo que os administradores apliquem uma ação corretiva antes que a experiência do usuário final seja afetada. Os dados de desempenho devem ser usados para o planejamento de capacidade a longo prazo.

Embora informações detalhadas sobre todos os objetos de desempenho e contadores a serem observados estejam vinculadas ao [monitoramento do Lync Server 2013 com o System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), alguns contadores de desempenho que você deve seguir podem fornecer aos administradores uma visualização rápida do desempenho do sistema:

  - Para acompanhar a integridade geral do sistema do servidor front-end, um bom ponto de partida é verificar\\o tempo do processador%. O valor deve estar sempre abaixo de 80%.

  - Para controlar o desempenho da instância do software de banco de dados back-end do SQL Server usada pelo pool de front-end, monitore os seguintes contadores de desempenho:
    
    LC: USrv – 00 – DBStore\\USrv – 002 – latência da fila (mseg)
    
    LC: USrv – 00 – DBStore\\USrv – 0 04 – latência de SPROC (mseg)
    
    O servidor saudável em estado Steady deve mostrar \<os valores de latência de 100 ms. O mecanismo de limitação irá se envolver quando a latência atingir 12 segundos, o que significa que o servidor front-end inicia as solicitações de limitação para o back-end. Isso faz com que os clientes comecem a receber uma mensagem de erro do 503 Server Busy.

  - Para acompanhar o tempo de processamento no servidor front-end, monitore o seguinte contador:
    
    LC: SIP-07-gerenciamento\\de carga SIP-000-média de manutenção do tempo para mensagens de entrada
    
    Esse é outro mecanismo de limitação dos servidores front-end, desta vez que é iniciado quando o tempo de processamento no front-end é alto. Se o tempo médio de processamento for superior a seis segundos, o servidor entrará no modo de limitação e só permitirá uma transação pendente por conexão do cliente.

  - Para acompanhar problemas de memória no servidor back-end SQL, monitore o seguinte contador:
    
    Expectativa de vida da\\página do Gerenciador de buffer do SQL Server
    
    Um valor baixo, abaixo de 3600 segundos (juntamente com gravações de alta latência/s e páginas de ponto de verificação/s) indica a pressão de memória.

<div>

## <a name="additional-counters-to-view"></a>Contadores adicionais para exibir

Há vários contadores-chave que são bons indicadores de integridade geral do servidor front-end. Esta não é uma lista abrangente e não se destina a identificar a causa básica. Esses contadores permitirão executar uma verificação rápida na integridade do seu servidor. Recomendamos verificar esses contadores em cada um dos servidores do pool. É importante entender quais são esses valores de contador quando o servidor está íntegro. Uma linha de base é necessária para entender o que mudou quando a experiência do usuário é degradada.

O servidor front-end pode indicar problemas que podem ser causados por afunilamentos em outro lugar do sistema. Isso significa que é o melhor lugar para começar a examinar a integridade geral do sistema.

Dois contadores adicionais a serem revisados primeiro são os seguintes:

LC: USrv-00-DBStore\\USrv-002-latência da fila (mseg)

LC: USrv-00-DBStore\\USrv-004-SPROC latência (mseg)

O contador latência da fila representa o tempo que uma solicitação gastou na fila para o back-end e a latência SPROC representa o tempo gasto pelo back-end para processar a solicitação. Se, por qualquer motivo, disco, memória, rede e processador no back-end estiverem em problemas, o contador de latência da fila será alto.

Também pode ser alto se houver alta latência de rede entre o front-end e o back-end. O que é latência de fila aceitável?

Em 12 segundos, os servidores front-end começam a limitação de solicitações para os servidores back end. Isso significa que os servidores começam a retornar o servidor ocupado – 503 erros para os clientes. Um servidor saudável deve ter menos de 100 mseg DBStore latências da fila no estado Steady, mas, durante o tempo em que o servidor acabou de ficar online, e todos os usuários estão se conectando ao mesmo tempo, esse contador pode ser muito alto, e você pode até mesmo ver a ocorrência de vários segundos.

Você pode ter uma configuração de carga balanceada, em que você tem um pool implantado com vários servidores front-end e um balanceador de carga que é configurado para "número mínimo de conexões". Nesse caso, se um servidor front-end for reiniciado, todos os usuários que tentarem se reconectar serão apontados para o servidor reiniciado porque o servidor terá menos conexões em comparação com os outros membros do pool. Durante esse período, o respectivo servidor front-end pode ser sobrecarregado enquanto os outros membros do pool não estão.

Recomendamos que você execute a manutenção fora do expediente para reduzir o desempenho, pois os usuários não estarão competindo a se conectar ao servidor ao mesmo tempo.

Se os dois contadores de desempenho anteriores forem altos, o afunilamento mais provável é o servidor back-end do SQL. Os próximos componentes a serem confirmados são os seguintes:

  - A CPU do SQL Server está muito alta? Por exemplo, é maior do que 80%?

  - A latência do disco é alta?

Em um mundo ideal, você tem RAM suficiente para ter os bancos de dados do RTC e do RTCDYN na memória. Em seguida, o único motivo pelo qual o servidor está acessando o disco é gravar os arquivos de log e esvaziar para os bancos de dados. Os testes mostraram que 12 GB de RAM é suficiente para implantações do usuário do 100.000. Isso pressupõe que os bancos de dados RTC e RTCDYN tamanhos totais inferiores a 12 GB. Se os bancos de dados forem maiores do que isso, você pode precisar de memória adicional.

Você pode determinar se o SQL Server exige RAM adicional examinando o contador de desempenho de expectativa de duração da página do Gerenciador de buffer do SQL Server. Um valor menor que 3.600 indica A pressão de memória. Você também deve ver pouca ou nenhuma leitura na unidade de banco de dados se tiver memória suficiente porque o SQL Server só deve estar gravando no banco de dados.

Há um mecanismo de limitação adicional em um servidor de front-end do Lync Server 2013 que é iniciado quando o tempo de processamento do servidor é alto. A limitação de latência DBStore só será habilitada se a latência do SQL Server for alta. Um exemplo no qual essa limitação está habilitada é se o servidor front-end estiver associado à CPU.

Se o tempo médio de processamento **(LC: SIP-07-gerenciamento\\de carga SIP-000-média de manutenção do tempo para mensagens de entrada)** no servidor ultrapassar seis segundos, o servidor entrará no modo de limitação e somente fornecerá uma transação pendente aos usuários por conexão do cliente. Depois que o tempo de processamento cai para três segundos, o servidor fica fora do modo de limitação e oferece aos usuários até 20 transações pendentes por conexão do cliente. Sempre que o número de transações em uma conexão específica exceder o limite acima, a conexão será marcada como fluxo controlado. O resultado é que o servidor não publica os recebimentos nele, e o contador de **conexões controladas de fluxo\\SIP-01-Peers** é incrementado. Se uma conexão permanecer em um Estado controlado por fluxo por mais de um minuto, o servidor a fechará. Ele faz isso de forma ociosa. Quando ele tem uma oportunidade para verificar a conexão, ele determina se ele foi limitado por muito tempo e o fecha se tiver mais de um minuto.

Estes são os dois mecanismos de limitação e há um contador de desempenho que resume o que, se houver, está realizando a limitação do servidor.

**LC: SIP-04-respostas\\SIP-053-respostas 503 locais/s**

  - O termo "local" no contador anterior refere-se a respostas geradas localmente.

  - O código 503 corresponde ao servidor indisponível — onde você não deve ver nenhum código 503 em um servidor saudável. Durante o período após um servidor ser colocado online, você pode ver alguns códigos do 503. Quando todos os usuários voltam a entrar e o servidor retorna a um estado estável, não há nenhum código 503 adicional.

**LC: SIP-04-respostas\\SIP-074-respostas 504 locais/s**

Esse contador de desempenho indica problemas de conectividade com outros servidores e pode indicar falhas para se conectar ou atrasar na conexão. Se você estiver vendo erros 504, o seguinte contador de desempenho deve ser verificado.

**LC: SIP-01-Peers\\SIP-017-envios pendentes**

Esse contador indica o número de solicitações e respostas enfileiradas de saída. Se esse contador for alto, o problema provavelmente não está no servidor local. Observe que esse contador pode ser alto se houver problemas de latência de rede. Ele também pode indicar problemas com o adaptador de rede local, mas é mais provável que seja causado por um problema em um servidor remoto. Esse contador provavelmente seria alto em um servidor do director quando o pool com o qual ele está tentando se comunicar está sobrecarregado. A chave com esse contador é examinar as instâncias, e não apenas o total.

</div>

</div>

<span> </span>

</div>

</div>

</div>

