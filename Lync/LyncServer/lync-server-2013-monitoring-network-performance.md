---
title: 'Lync Server 2013: Monitorando o desempenho da rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Monitorando o desempenho da rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-04-27_

O Lync Server 2013 é uma tecnologia de comunicação em tempo real que depende muito da rede para permitir a comunicação entre usuários, seja por meio de mensagens instantâneas (IM), chamadas de voz ou comunicação com vídeo. Portanto, é importante monitorar o desempenho da rede continuamente para ajudar a garantir que a modalidade de comunicação escolhida pelo usuário ofereça a melhor experiência possível.

O desempenho da rede pode ser medido em dois níveis:

  - **Desempenho geral da rede**   esse nível de medição de desempenho permitirá que uma organização crie uma exibição "grande" da rede e, em geral, é implementada por sistemas de monitoramento de rede de terceiros. Esses sistemas receberão dados de desempenho e capacidade de dispositivos de rede remoto, como roteadores e comutados em toda a rede, para permitir que os administradores determinem a integridade de qualquer componente de rede fornecido a qualquer hora do dia.

  - **Desempenho individual do servidor**   esse nível de medição de desempenho é limitado a um servidor específico e ajuda os administradores com o gauging o desempenho de rede de um servidor específico para ajudar a solucionar um desempenho específico problema ou para medir o desempenho do respectivo servidor em um determinado período como parte de um processo de planejamento de capacidade.

Você pode monitorar a rede usando as ferramentas descritas nas seções a seguir.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Ferramentas para monitoramento geral do desempenho de rede

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

O System Center Operations Manager fornece gerenciamento de serviços de ponta a ponta que é fácil de personalizar e estender para níveis de serviço aprimorados em um ambiente de ti. Isso permite às operações e às equipes de gerenciamento de ti identificar e resolver problemas que afetem a integridade dos serviços de ti distribuídos. O gerenciamento de serviços completo não está restrito a ambientes baseados na Microsoft. Suporte para serviços Web para gerenciamento (WS-Management), protocolo de gerenciamento de rede simples (SNMP) e soluções de parceiros permitem que sistemas que não executam sistemas operacionais e hardware da Microsoft sejam incluídos no monitoramento de serviços no System Center Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 e soluções de gerenciamento de rede de terceiros

**EMC Smarts**   EMC Solutions for Operations Manager ajudam a resolver rapidamente problemas que afetem os níveis de serviço. Ao usar o EMC Solutions for Operations Manager, você pode gerenciar e monitorar toda a sua cadeia de serviços de ti com uma solução integrada e automatizada. Você identificará facilmente as causas de desempenho e a disponibilidade dos problemas de desempenho e os resolverá mais rapidamente, o que reduz os efeitos e os custos. Os principais benefícios incluem o seguinte:

  - O gerenciamento avançado e fácil de usar se concentra em oferecer um valor estratégico para os negócios, em vez de classificar e filtrar alertas confusos manualmente.

  - **Solução mais rápida**   solucione problemas e atenda às necessidades dos negócios com mais rapidez, reduzindo o efeito e o custo.

  - **Operações simplificadas**   evitam a complexidade da ti ao combinar várias ferramentas de gerenciamento, aplicativos e terminais.

Mais informações podem ser encontradas aqui:

[Gerenciador de operações do Microsoft System Center](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Soluções para o Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Soluções de terceiros

**Centro de gerenciamento de redes HP (anteriormente conhecido como HP OpenView)** O    [centro de gerenciamento de redes HP](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) oferece gerenciamento integrado de falhas e desempenho para melhorar a disponibilidade e o desempenho da rede. O centro de gerenciamento de rede é parte da solução de gerenciamento automatizado de rede da HP que unifica o gerenciamento de falhas, desempenho, configuração e alterações.

**Gerenciamento de rede e produtos**   de automação da Cisco para empresas, a Cisco tem vários produtos de gerenciamento disponíveis, incluindo a solução de gerenciamento de LAN da CiscoWorks e o módulo de análise de rede da Cisco, para ajudar a melhorar a eficiência operacional e reduzir o tempo de inatividade da rede. Para obter dados adicionais sobre esses produtos, consulte o website da Cisco [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)em.

O protocolo de gerenciamento de rede simples (SNMP) é um padrão de gerenciamento de rede (SNMP) que define uma estratégia para gerenciar redes TCP/IP. O SNMP permite que você capture informações de configuração e status sobre a rede e envie as informações para um computador designado para monitoramento de eventos. Esse protocolo baseado em padrões de gerenciamento de rede usa uma arquitetura distribuída que inclui o seguinte:

  - Vários nós gerenciados, cada um com uma entidade SNMP chamada de agente, que fornece acesso remoto à instrumentação de gerenciamento.

  - Pelo menos uma entidade SNMP conhecida como gerente que executa aplicativos de gerenciamento para monitorar e controlar elementos gerenciados. Elementos gerenciados são dispositivos como hosts, roteadores e assim por diante. Elas são monitoradas e controladas acessando suas informações de gerenciamento.

  - Um protocolo de gerenciamento, SNMP, é usado para comunicar informações de gerenciamento entre as estações de gerenciamento e agentes. Informações de gerenciamento referem-se a uma coleção de objetos gerenciados que residem em um repositório de informações virtual chamado de uma base de informações de gerenciamento (MIB).

<div>


> [!NOTE]  
> Exemplos de soluções de monitoramento de rede de terceiros são fornecidos acima. Esta lista não é definitiva, e a Microsoft não favorece nenhuma solução específica de fornecedor. Consulte um provedor de serviços de rede e ou seu respectivo provedor de tecnologia para determinar a melhor solução de monitoramento de rede para a sua organização.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Ferramentas para monitorar o desempenho de uma rede de servidor individual

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

O System Center Operations Manager 2012 permite que os administradores visualizem o desempenho de rede de servidores individuais por meio do pacote de gerenciamento do Windows Server 2012: o pacote de gerenciamento do sistema operacional Windows Server inclui um pacote de gerenciamento de "desempenho" Isso permite que os administradores monitorem o desempenho do adaptador de rede e a integridade do adaptador.

</div>

<div>

## <a name="windows-network-monitor"></a>Monitor de rede do Windows

Coleta, exibe, analisa o uso de recursos em um servidor e mede o tráfego de rede. O monitor de rede monitora exclusivamente as atividades da rede. Ao capturar e analisar dados de rede e usar esses dados com logs de desempenho, você pode determinar o uso da rede, identificar problemas de rede e prever as necessidades futuras de rede.

Para obter mais informações sobre o monitor de rede 3,4 e sobre como instalar e configurar o monitor de rede e capturar e analisar dados, Confira esta sessão: monitor de rede 3,3 visão geral. Além disso, examine o [blog do monitor de rede](http://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

