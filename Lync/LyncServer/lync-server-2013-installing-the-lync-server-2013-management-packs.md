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
ms.openlocfilehash: ffc102eccdbaa941e2691df88899c0cc01348838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>Instalar os pacotes de gerenciamento do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Por si só, o System Center Operations Manager tem a capacidade de monitorar apenas uma pequena parte do sistema operacional Windows. No entanto, você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento, software que determina quais itens o System Center Operations Manager pode monitorar, incluindo como esses itens devem ser monitorados e como os alertas devem ser disparado e reportado. O Microsoft Lync Server 2013 inclui dois pacotes de gerenciamento do System Center Operations Manager que fornecem os seguintes recursos:

  - O componente e o pacote de gerenciamento de usuários (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) controla problemas do Lync Server gravados em logs de eventos, registrados por contadores de desempenho, ou registrados nos registros de detalhes de chamadas (CDR) ou na qualidade da experiência (QoE) bancos. Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS (serviço de mensagens curtas). SMS é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro.
    
    <div>
    

    > [!NOTE]  
    > Para obter mais informações sobre como configurar a notificação do Operations Manager, consulte Configurando a notificação na biblioteca do TechNet em <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.

    
    </div>

  - O pacote de monitoramento ativo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Lync Server, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado no telefone público comutado rede (PSTN). Esses testes são conduzidos usando cmdlets de transação sintéticas do Lync Server. Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagens instantâneas entre um par de usuários de teste. Se essa conversa de mensagens simulada falhar, um alerta será gerado.

Os dois pacotes de gerenciamento incluídos no Lync Server 2013 incluem uma grande quantidade de aprimoramentos nos pacotes de gerenciamento usados com o Microsoft Lync Server 2010. Por exemplo, o pacote de gerenciamento do componente do Lync Server 2013 não está limitado ao monitoramento próprio do Lync Server. Além de monitorar os logs de eventos e os contadores de desempenho do Lync Server, o pacote de gerenciamento de componentes também pode controlar o desempenho de itens cruciais e emitir alertas para itens cruciais, como:

  - **Os alertas dos serviços de informações da Internet (IIS)**   serão emitidos se os serviços de informações da Internet ficarão offline. Isso é importante, pois os serviços Web do Lync Server dependem do IIS.

  - ****   Alertas de uso de processo serão emitidos se os recursos do sistema (como a memória disponível) começarem a ser baixados. Esses alertas serão emitidos mesmo se o Lync Server não for responsável pelo alto uso do sistema.

  - ****   Os alertas de eventos de falha do computador serão emitidos em caso de um problema de hardware ou software que ameaça a viabilidade de um servidor. Por exemplo, os administradores do Lync Server serão notificados se um servidor parecer estar em perigo de ocorrer uma falha no disco rígido.

Os novos pacotes de gerenciamento também apresentam relatórios avançados. Os novos relatórios do Lync Server 2013 incluem:

  - **Relatório de disponibilidade do cenário de ponta a ponta**   este relatório detalha a disponibilidade/tempo de atividade dos serviços principais do Lync Server, como registro ou presença.

  - **Relatório de capacidade**   usando informações de contador de desempenho, esse relatório mostra tendências para componentes do sistema, como disponibilidade da memória e uso do processador.

  - **Relatório de componente**   este relatório lista os principais geradores de alertas agrupados pelo componente do Lync Server.

Além desses relatórios predefinidos, os pacotes de gerenciamento do Lync Server 2013 automaticamente relatam alertas para a confiabilidade das chamadas (métricas medidas por gravação de detalhes de chamadas) e Estados de QoE (métricas medidas por qualidade de experiência). Se você tiver habilitado a gravação de detalhes da chamada, poderá revisar os alertas de confiabilidade da chamada completando o procedimento a seguir no console do System Center Operations Manager:

  - Expanda **monitoramento**, expanda **integridade do Microsoft Lync Server 2013**, expanda a **confiabilidade da chamada e a qualidade da mídia**e clique em **chamar confiabilidade**.

Para ver os alertas de qualidade da experiência, conclua este procedimento no console do System Center Operations Manager:

  - Expanda **monitoramento**, expanda **integridade do Microsoft Lync Server 2013**, expanda a **confiabilidade da chamada e a qualidade da mídia**e expanda qualidade da **mídia**.

Os pacotes de gerenciamento do Lync Server 2013 agora usam a descoberta em nível de máquina em vez do mecanismo de descoberta central usado no Microsoft Lync Server 2010. Isso significa que cada agente do System Center essencialmente descobre e relata sua existência ao servidor central de gerenciamento. O uso da descoberta no nível da máquina simplifica a administração da infraestrutura do sistema central e também permite diferentes versões dos pacotes de gerenciamento do Lync Server (por exemplo, pacotes de gerenciamento do Lync Server 2010 e pacotes de gerenciamento do Lync Server 2013) para exist.

</div>

<span> </span>

</div>

</div>

</div>

