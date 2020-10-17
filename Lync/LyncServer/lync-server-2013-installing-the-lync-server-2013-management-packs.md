---
title: 'Lync Server 2013: instalando os pacotes de gerenciamento do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ff5b636c4cb2eaea2b3f7caa5681a26a8a59dc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534808"
---
# <a name="installing-the-lync-server-2013-management-packs"></a>Instalando os pacotes de gerenciamento do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Sozinho, o System Center Operations Manager tem a capacidade de monitorar apenas uma pequena parte do sistema operacional Windows. No entanto, você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento, software que determina quais itens o System Center Operations Manager pode monitorar, incluindo como esses itens devem ser monitorados e como os alertas devem ser acionados e relatados. O Microsoft Lync Server 2013 inclui dois pacotes de gerenciamento do System Center Operations Manager que oferecem os seguintes recursos:

  - O pacote de gerenciamento de componente e usuário (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) acompanha os problemas do Lync Server registrados em logs de eventos, registrados por contadores de desempenho ou registrados nos bancos de dados de registro de detalhes de chamadas (CDR) ou da qualidade da experiência (QoE). Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS (Short Message Service). SMS é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro.
    
    <div>
    

    > [!NOTE]  
    > Para obter mais informações sobre como configurar a notificação do Operations Manager, consulte Configuring Notification na biblioteca do TechNet em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> .

    
    </div>

  - O pacote de monitoramento ativo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Lync Server, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado na rede telefônica pública comutada (PSTN). Esses testes são conduzidos usando os cmdlets de transação sintéticas do Lync Server. Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagem instantânea entre um par de usuários de teste. Um alerta será gerado em caso de falha nessa conversa de mensagens simulada.

Os dois pacotes de gerenciamento incluídos no Lync Server 2013 incluem um grande número de aprimoramentos nos pacotes de gerenciamento usados com o Microsoft Lync Server 2010. Por exemplo, o pacote de gerenciamento do componente do Lync Server 2013 não está limitado ao monitoramento do Lync Server. Além de monitorar os logs de eventos e os contadores de desempenho do Lync Server, o pacote de gerenciamento de componente também pode rastrear o desempenho e emitir alertas para itens cruciais, como:

  - **Serviços de informações da Internet (IIS)**     Os alertas serão emitidos se o serviços de informações da Internet ficar offline. Isso é importante porque os serviços Web do Lync Server dependem do IIS.

  - **Uso**     do processo Os alertas serão emitidos se os recursos do sistema (como memória disponível) começarem a ser executados em baixa. Esses alertas serão emitidos mesmo se o Lync Server não for responsável pelo alto uso do sistema.

  - Eventos de falha do **computador**     Os alertas serão emitidos no caso de um problema de hardware ou software que ameaça a viabilidade de um servidor. Por exemplo, os administradores do Lync Server serão notificados se um servidor parece estar em perigo de ocorrer uma falha no disco rígido.

Os novos pacotes de gerenciamento também dispõem de relatórios avançados. Os novos relatórios do Lync Server 2013 incluem:

  - **Relatório de disponibilidade de cenário de ponta a ponta**     Este relatório detalha a disponibilidade/tempo de atividade dos serviços principais do Lync Server, como registro ou presença.

  - **Relatório**     de capacidade Usando informações de contador de desempenho, este relatório mostra tendências para componentes do sistema, como disponibilidade de memória e uso do processador.

  - **Relatório**     de componente Este relatório lista os principais geradores de alerta agrupados pelo componente do Lync Server.

Além desses relatórios predefinidos, os pacotes de gerenciamento do Lync Server 2013 relatam automaticamente alertas para a confiabilidade da chamada (métricas medidas por registro de detalhes das chamadas) e Estados de QoE (métricas medidas por qualidade da experiência). Se você tiver habilitado a gravação de detalhes da chamada, poderá revisar os alertas de confiabilidade de chamada ao concluir o seguinte procedimento no console do System Center Operations Manager:

  - Expanda **Monitoramento**, **Integridade do Microsoft Lync Server 2013**, **Confiabilidade de chamada e qualidade de mídia**, e clique em **Confiabilidade de chamada**.

Para exibir os alertas de qualidade da experiência, conclua este procedimento no console do System Center Operations Manager:

  - Expanda **Monitoramento**, **Integridade do Microsoft Lync Server 2013**, **Confiabilidade de chamada e qualidade de mídia**, e, em seguida, expanda **Qualidade de mídia**.

Os pacotes de gerenciamento do Lync Server 2013 agora usam a descoberta de nível de máquina em vez do mecanismo de descoberta central usado no Microsoft Lync Server 2010. Isso significa que cada agente do System Center é basicamente descoberto e relata sua existência com o servidor de gerenciamento central. O uso da descoberta no nível da máquina simplifica a administração da infraestrutura do System Center e também permite diferentes versões dos pacotes de gerenciamento do Lync Server (por exemplo, pacotes de gerenciamento do Lync Server 2010 e pacotes de gerenciamento do Lync Server 2013) para coexistir.

</div>

<span> </span>

</div>

</div>

</div>

