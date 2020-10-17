---
title: 'Lync Server 2013: monitorando o sistema operacional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d6cad561761b7387cb4c268229f76b52f4bd24b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500628"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a>Monitorando o sistema operacional no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-01-26_

Você deve monitorar o desempenho de todos os servidores e componentes no Lync Server 2013. Obviamente, um dos componentes mais importantes é o próprio sistema operacional. O Lync Server 2013 suporta edições x64 do:

  - Windows Server 2008 R2

  - Windows Server 2012 e Windows Server 2012 R2

A maneira mais transparente de monitorar um sistema operacional é usar o pacote de gerenciamento do sistema operacional Windows Server. Ele fornece os princípios básicos de monitoramento, como desempenho, integridade e disponibilidade para computadores que executam o Windows Server 2012, o Windows Server 2012 R2 e o Windows Server 2008 R2.

Ao detectar, alertar e responder automaticamente a eventos importantes e indicadores de desempenho, esses pacotes de gerenciamento reduzem os tempos de resolução de problemas e aumentam a disponibilidade e o desempenho geral dos sistemas que executam os sistemas operacionais Windows Server.

Além de pacotes de gerenciamento do Windows Server relevantes para o System Center Operations Manager, as seguintes ferramentas e recursos do sistema podem ser usados para monitorar a integridade do sistema operacional (dependendo da versão do sistema operacional).

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

O Windows Server 2008 R2 inclui os seguintes recursos e ferramentas adicionais para ajudar os administradores com o monitoramento e o gerenciamento básicos do sistema operacional:

  - O **Monitor de recursos do Windows** é uma poderosa ferramenta para entender como os recursos do sistema são usados por processos e serviços. Além de monitorar o uso de recursos em tempo real, um monitor de recursos pode ajudar a analisar processos sem resposta, identificar quais aplicativos estão usando arquivos e controlar processos e serviços.

  - O **componente de análise de confiabilidade** é um agente de caixa de entrada que fornece informações detalhadas sobre o uso e a confiabilidade do sistema. Essas informações são expostas por meio de uma interface WMI para torná-la disponível para consumo por sistemas de leitores portáteis. Ao expor o componente de análise de confiabilidade por meio de uma interface WMI, os desenvolvedores podem monitorar e analisar aplicativos, aumentando a confiabilidade e o desempenho.

  - O **Windows Server 2008 R2** usa o componente de análise de confiabilidade interno para calcular um índice de confiabilidade, que fornece informações sobre a estabilidade e o uso geral do sistema ao longo do tempo. O componente de análise de confiabilidade também mantém o controle de qualquer alteração importante no sistema que provavelmente influenciará a estabilidade, como as atualizações do Windows e as instalações de aplicativos.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Monitor de desempenho e confiabilidade do Windows Server 2008

O monitor de confiabilidade e desempenho do Windows é um snap-in do MMC que combina a funcionalidade de ferramentas autônomas anteriores, incluindo logs e alertas de desempenho, supervisor de desempenho do servidor e monitor do sistema. Ele fornece uma interface gráfica para personalizar a coleta de dados de desempenho e as sessões de rastreamento de eventos.

Também inclui o monitor de confiabilidade, um snap-in do MMC que rastreia alterações no sistema e as compara às alterações na estabilidade do sistema e fornece uma exibição gráfica de sua relação.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Monitor de desempenho e confiabilidade do Windows

Enquanto o monitor de confiabilidade e desempenho do Windows combina funcionalidades de algumas ferramentas autônomas antigas, como logs e alertas de desempenho, e o monitor de sistema e o supervisor de desempenho do servidor, ele também fornece uma nova funcionalidade ao Windows Server 2008 e ao Windows Server 2008 R2, como o seguinte:

  - Conjuntos de coletores de dados

  - Exibição de recurso

  - Monitor de confiabilidade

  - Assistentes e modelos para a criação de logs

**Conjunto de coletores de dados** agrupa coletores de dados em elementos reutilizáveis para uso com diferentes cenários de monitoramento de desempenho. Após um grupo de coletores de dados ser armazenado como um conjunto de coletores de dados, operações como agendamento podem ser aplicadas ao conjunto inteiro por meio de uma única alteração de propriedade. O monitor de confiabilidade e desempenho do Windows inclui modelos de conjunto de coletores de dados padrão para ajudar os administradores do sistema a começar a coletar imediatamente os dados de desempenho específicos para uma função de servidor ou um cenário de monitoramento.

A home page do monitor de confiabilidade e desempenho do Windows é a nova tela do **modo de exibição de recursos** , que fornece uma visão geral gráfica em tempo real de uso de CPU, disco, rede e memória. Ao expandir cada um desses elementos monitorados, os administradores do sistema podem identificar quais processos estão usando quais recursos. Nas versões anteriores do Windows, esses dados em tempo real, específicos do processo, estavam disponíveis apenas na forma limitada no Gerenciador de tarefas.

O **Monitor de confiabilidade** calcula um índice de estabilidade do sistema que reflete se problemas inesperados reduziram a confiabilidade do sistema. Um gráfico do índice de estabilidade ao longo do tempo identifica rapidamente datas quando os problemas começaram a ocorrer. O relatório de estabilidade do sistema fornecido fornece detalhes para ajudar a solucionar problemas de causa da confiabilidade reduzida. Exibindo alterações no sistema (instalação ou remoção de aplicativos, atualizações no sistema operacional ou adição ou modificação de drivers) lado a lado com falhas (falhas de aplicativo, panes no sistema operacional ou falhas de hardware), uma estratégia para lidar com os problemas pode ser desenvolvida rapidamente.

A adição de contadores a arquivos de log e agendamento de início, parada e duração podem ser realizadas por meio de uma **interface de assistente**. Além disso, salvar essa configuração como um modelo permite que os administradores do sistema coletem o mesmo log em outros computadores sem repetir os processos de seleção e agendamento de coletor de dados. Os recursos de logs e alertas de desempenho foram incorporados ao monitor de confiabilidade e desempenho do Windows para uso com qualquer conjunto de coletores de dados.

</div>

</div>

<span> </span>

</div>

</div>

</div>

