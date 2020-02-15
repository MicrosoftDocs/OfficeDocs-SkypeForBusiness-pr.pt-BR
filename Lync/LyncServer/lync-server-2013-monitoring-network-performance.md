---
title: 'Lync Server 2013: monitorando o desempenho da rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524499737ae1e52a36a80fbc636f005b687a6a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Monitorando o desempenho da rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-04-27_

O Lync Server 2013 é uma tecnologia de comunicação em tempo real que depende fortemente da rede para habilitar a comunicação entre usuários, através de mensagens instantâneas (IM), chamadas de voz ou comunicação de vídeo. Portanto, é importante monitorar o desempenho da rede continuamente para ajudar a garantir que a modalidade de comunicação escolhida pelo usuário ofereça a melhor experiência possível.

O desempenho da rede pode ser medido em dois níveis:

  - **Desempenho geral da rede**   esse nível de medição de desempenho permitirá que uma organização crie uma visão geral de sua rede e, em geral, é implementada por meio de sistemas de monitoramento de rede de terceiros. Esses sistemas receberão dados de desempenho e capacidade de dispositivos de rede remotas, como roteadores e comutados por toda a rede para permitir que os administradores determinem a integridade de um determinado componente de rede em qualquer ocasião do dia.

  - **Desempenho do servidor individual**   esse nível de medição de desempenho está limitado a um servidor específico e ajudará os administradores no gauging o desempenho de rede de um servidor específico para ajudar na solução de problemas de um problema específico de desempenho ou para medir o desempenho do respectivo servidor em um determinado período como parte de um processo de planejamento de capacidade.

Você pode monitorar a rede usando as ferramentas descritas nas seções a seguir.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Ferramentas para monitoramento geral do desempenho da rede

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

O System Center Operations Manager oferece gerenciamento de serviço de ponta a ponta que é fácil de personalizar e estender para níveis de serviço aprimorados em um ambiente de ti. Isso permite que as operações e as equipes de gerenciamento de ti identifiquem e resolvam os problemas que afetam a integridade dos serviços de ti distribuídos. O gerenciamento de serviços de ponta a ponta não é restrito a ambientes baseados em Microsoft. Suporte para serviços Web para gerenciamento (WS-Management), SNMP (protocolo de gerenciamento de rede simples) e soluções de parceiros permitem que sistemas que não executam sistemas operacionais e hardware da Microsoft sejam incluídos no monitoramento de serviços no System Center Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>Soluções de gerenciamento de rede do System Center Operations Manager 2012 e de terceiros

**EMC Smarts**   EMC Solutions for Operations Manager ajuda a resolver rapidamente problemas que afetam os níveis de serviço. Usando o EMC Solutions for Operations Manager, você pode gerenciar e monitorar toda a sua cadeia de serviços de ti com uma solução integrada e automatizada. Você identificará facilmente as causas raiz dos problemas de desempenho e disponibilidade e os resolverá mais rapidamente, reduzindo os efeitos e os custos. Os principais benefícios incluem o seguinte:

  - Foco de gerenciamento avançado e fácil de usar para fornecer o valor estratégico de negócios, em vez de classificar e filtrar manualmente os alertas confusos.

  - **Resolução mais rápida**   resolvem problemas de ti e atendem às necessidades de negócios com mais rapidez, reduzindo o efeito e o custo.

  - **Operações simplificadas**   evitam complexidade de ti combinando várias ferramentas de gerenciamento, aplicativos e terminais.

É possível encontrar mais informações aqui:

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Soluções para o Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Soluções de terceiros

**Centro de gerenciamento de rede HP (anteriormente conhecido como HP OpenView) o centro de**   [Gerenciamento de rede HP](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) oferece gerenciamento de falhas e desempenho integrados para melhorar a disponibilidade e o desempenho da rede. O centro de gerenciamento de rede é parte da solução de gerenciamento automatizado de rede HP que unifica o gerenciamento de falhas, desempenho, configuração e alteração.

**Os produtos**   de gerenciamento e automação de rede da Cisco para a empresa, a Cisco tem vários produtos de gerenciamento disponíveis, incluindo a solução de gerenciamento de LAN da CiscoWorks e o módulo de análise de rede da Cisco, para ajudar a melhorar a eficiência operacional e reduzir o tempo Para obter dados adicionais sobre esses produtos, consulte o site da Cisco [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)em.

SNMP (protocolo de gerenciamento de rede simples) SNMP é um padrão de gerenciamento de rede que define uma estratégia para gerenciar redes TCP/IP. O SNMP permite capturar informações de configuração e status sobre a rede e enviar as informações para um computador designado para monitoramento de eventos. Este protocolo de gerenciamento de rede baseado em padrões usa uma arquitetura distribuída que inclui o seguinte:

  - Vários nós gerenciados, cada um com uma entidade SNMP chamada de um agente que fornece acesso remoto à instrumentação de gerenciamento.

  - Pelo menos uma entidade SNMP conhecida como gerente que executa aplicativos de gerenciamento para monitorar e controlar os elementos gerenciados. Elementos gerenciados são dispositivos como hosts, roteadores e assim por diante. Eles são monitorados e controlados acessando suas informações de gerenciamento.

  - Um protocolo de gerenciamento, SNMP, é usado para comunicar informações de gerenciamento entre as estações de gerenciamento e os agentes. As informações de gerenciamento referem-se a uma coleção de objetos gerenciados que residem em um repositório de informações virtual, chamado de MIB (Management Information base).

<div>


> [!NOTE]  
> Os exemplos de soluções de monitoramento de rede de terceiros são fornecidos acima. Essa lista não é definitiva, e a Microsoft não favorece nenhuma solução de fornecedor específico. Consulte um provedor de serviços de rede e seu respectivo provedor de tecnologia para determinar a melhor solução de monitoramento de rede para sua organização.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Ferramentas para monitorar o desempenho da rede de servidor individual

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

O System Center Operations Manager 2012 permite que os administradores exibam o desempenho de rede de servidores individuais por meio do pacote de gerenciamento do Windows Server 2012: o pacote de gerenciamento do sistema operacional Windows Server inclui um pacote de gerenciamento de "desempenho" Isso permite que os administradores monitorem o desempenho do adaptador de rede e a integridade do adaptador.

</div>

<div>

## <a name="windows-network-monitor"></a>Monitor de rede do Windows

Coleta, exibe, analisa o uso do recurso em um servidor e mede o tráfego de rede. O monitor de rede monitora exclusivamente a atividade da rede. Ao capturar e analisar dados de rede e usar esses dados com logs de desempenho, você pode determinar o uso da rede, identificar problemas de rede e prever as necessidades futuras da rede.

Para obter mais informações sobre o monitor de rede 3,4 e sobre como instalar e configurar o monitor de rede e capturar e analisar dados, revise esta sessão: monitor de rede 3,3 visão geral. Além disso, revise o [blog do monitor de rede](http://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

