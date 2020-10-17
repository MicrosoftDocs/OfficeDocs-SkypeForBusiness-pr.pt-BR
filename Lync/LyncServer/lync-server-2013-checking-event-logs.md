---
title: 'Lync Server 2013: verificando logs de eventos'
description: 'Lync Server 2013: verificando logs de eventos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6617bde846fd38ab3282fd023b16e0a921f48920
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570977"
---
# <a name="checking-event-logs-in-lync-server-2013"></a>Verificar logs de eventos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-08-06_

Você pode usar o [Visualizador de eventos do Windows](https://go.microsoft.com/fwlink/p/?linkid=314067) para exibir logs de eventos e obter informações sobre falhas de serviço, erros de replicação no AD DS e avisos sobre recursos do sistema, como memória virtual e espaço em disco. O Visualizador de eventos está incluído no Windows Server 2008 e 2012.

Na ferramenta de log do Lync Server 2013, quando você finaliza a sessão de depuração, clique em **analisar arquivos de log** para exibir os arquivos de log usando a ferramenta Snooper.

O Visualizador de eventos mantém logs sobre eventos de aplicativo, segurança e sistema no computador. O Lync Server 2013 e os avisos de relatório do Windows e as condições de erro para os logs de eventos. Portanto, revise os logs de eventos diariamente.

Use o Visualizador de eventos para:

  - Exibir e gerenciar logs de eventos.

  - Obter informações sobre problemas de hardware, software e sistema que devem ser resolvidos.

  - Identificar tendências que exigem ação futura.

Um servidor que esteja executando o Lync Server em um sistema operacional Windows Server registra eventos em quatro tipos de logs:

  - **Logs**     de aplicativos O log de aplicativo contém eventos registrados por aplicativos ou programas. Os desenvolvedores determinam quais eventos registrar. Por exemplo, um programa de banco de dados pode gravar um erro de arquivo no log de aplicativo. A maioria dos eventos relacionados ao Lync Server 2013 aparece no log de aplicativo.

  - **Logs**     de segurança O log de segurança registra eventos como tentativas de logon válidas e inválidas, além de eventos relacionados ao uso de recursos, como criar, abrir ou excluir arquivos ou outros objetos. Por exemplo, se a auditoria de logon estiver habilitada, as tentativas de fazer logon no sistema são registradas no log de segurança.

  - **Logs**     do sistema O log do sistema contém eventos registrados pelos componentes de sistema do Windows. Por exemplo, a falha de um driver ou de outro componente de sistema para carregar durante a inicialização é registrada no log do sistema. Os tipos de eventos registrados pelos componentes do sistema são pré-determinados pelo servidor.

  - **Lync Server 2013**     A ferramenta de registro em log registra eventos significativos relacionados a autenticação, conexões e ações do usuário. Após habilitar o log de diagnóstico, você pode exibir as entradas de log no Visualizador de eventos.

<div>


> [!NOTE]  
> Não é recomendável usar as configurações de log máximo, a menos que você seja instruído a fazer isso por meio dos serviços de suporte ao cliente da Microsoft. O registro em log máximo esvazia recursos significativos e pode dar muitos "falsos positivos", ou seja, erros que são registrados apenas no log máximo, mas são realmente esperados e não têm uma causa de preocupação. Recomendamos também que você não habilite o log de diagnóstico permanentemente. Use-o somente durante a solução de problemas.



</div>

Em cada log do Visualizador de eventos, o Lync Server 2013 registra informações sobre eventos, avisos e erros. Monitore esses logs em detalhes para controlar os tipos de transações sendo realizadas nos servidores do Lync Server 2013. Você deve arquivar periodicamente os logs ou usar a substituição automática para evitar ficar sem espaço. Como os arquivos de log podem ocupar uma quantidade de espaço finita, aumente o tamanho do log (por exemplo, 50 MB) e defina-o para que seja substituído para que o servidor do Lync Server 2013 possa continuar a gravar novos eventos.

Você também pode automatizar a administração de logs de eventos usando as seguintes ferramentas e tecnologias:

  - O System Center Operations Manager monitora a integridade e o uso de servidores do Lync Server 2013. O pacote de gerenciamento do Lync Server 2013 para o Operations Manager estende o Operations Manager fornecendo monitoramento especializado para servidores que executam o Lync Server 2013.

  - O pacote de gerenciamento do Lync Server 2013 para o Operations Manager monitora a edição Standard e Enterprise do Lync Server 2013. Este lançamento também incorpora o pacote de gerenciamento da qualidade da experiência (QoE) que era anteriormente um pacote de gerenciamento separado.

Os tipos monitorados são entradas de log de eventos, contadores de desempenho e monitoramento de estado do QoE. Esta versão do pacote de gerenciamento monitora apenas o Lync Server 2013 e o 2010 e não pode ser usada para monitorar o Office Communications Server 2007.

O pacote de gerenciamento fornece os seguintes recursos:

  - Alertas que indicam serviço que afeta eventos

  - Alertas indicando configuração e outros problemas de impacto que não são de serviço

  - Monitoramento de estado dos serviços do Lync Server

  - Conhecimento do produto: causa e resolução de problemas identificados

Para obter mais informações sobre o pacote de gerenciamento do Lync Server 2013, consulte [Monitoring Lync server 2013 com System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Pente**     de eventos A ferramenta Event Comb coleta eventos específicos dos logs de eventos de vários computadores em um local central. Ele permite que você informe somente as IDs de evento ou as fontes de eventos que ele especifica. Para obter mais informações sobre o Event Comb, consulte o site de [ferramentas de gerenciamento e bloqueio de conta](https://go.microsoft.com/fwlink/?linkid=35607) .

**Disparadores**     de eventos No Windows Server 2012, você pode "anexar uma tarefa a este evento" dentro do Visualizador de eventos do Windows — onde um administrador pode executar um programa, enviar uma mensagem de email ou exibir uma mensagem na tela. Para obter mais informações sobre esse recurso, consulte o tópico Windows Server 2008 R2 [executar uma tarefa em resposta a um determinado evento](https://technet.microsoft.com/library/cc748900.aspx). Você também pode usar ferramentas de linha de comando, como ' Eventtrigger.exe ', para criar e consultar logs de eventos e associar programas a determinados eventos registrados. Usando Eventtriggers.exe, você pode criar disparadores de eventos que executam programas quando ocorrem eventos específicos.

<div>

## <a name="see-also"></a>Confira também


[Visualizador de eventos do Windows](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

