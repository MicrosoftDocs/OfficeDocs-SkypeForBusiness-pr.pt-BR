---
title: 'Lync Server 2013: verificando logs de eventos'
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
ms.openlocfilehash: 862d419d9db5d8465b3507c40fde32acd01bb659
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Verificar logs de eventos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-08-06_

Você pode usar o [Visualizador de eventos do Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) para exibir logs de eventos e obter informações sobre falhas de serviço, erros de replicação no AD DS e avisos sobre recursos do sistema, como memória virtual e espaço em disco. O Visualizador de eventos está incluído no Windows Server 2008 e no 2012.

Na ferramenta de log do Lync Server 2013, quando você terminar a sessão de depuração, clique em **analisar arquivos de log** para ver os arquivos de log usando a ferramenta de rastreamento.

O Visualizador de eventos mantém registros sobre eventos de aplicativo, segurança e sistema no computador. O Lync Server 2013 e o Windows reportam avisos e condições de erro para os logs de eventos. Portanto, examine os logs de eventos diariamente.

Use o Visualizador de eventos para:

  - Exibir e gerenciar logs de eventos.

  - Obter informações sobre hardware, software e problemas do sistema que devem ser resolvidos.

  - Identifique tendências que exigem uma ação futura.

Um servidor que esteja executando o Lync Server em um sistema operacional Windows Server registra eventos em quatro tipos de logs:

  - **Registros de aplicativos**   o log do aplicativo contém eventos registrados por aplicativos ou programas. Os desenvolvedores determinam quais eventos registrar. Por exemplo, um programa de banco de dados pode gravar um erro de arquivo no log do aplicativo. A maioria dos eventos relacionados ao Lync Server 2013 aparecem no log do aplicativo.

  - **Logs de segurança**   o log de segurança registra eventos como, por exemplo, tentativas de logon válidas e não válidas, além de eventos relacionados ao uso de recursos, como criar, abrir ou excluir arquivos ou outros objetos. Por exemplo, se a auditoria de logon estiver habilitada, as tentativas de fazer logon no sistema serão gravadas no log de segurança.

  - **Registros do sistema**   o log do sistema contém eventos registrados pelos componentes de sistema do Windows. Por exemplo, a falha de um driver ou outro componente do sistema a ser carregado durante a inicialização é gravada no log do sistema. Os tipos de eventos registrados pelos componentes do sistema são predeterminados pelo servidor.

  - **Lync Server 2013**   a ferramenta de log registra eventos significativos relacionados a autenticação, conexões e ações do usuário. Depois de habilitar o log de diagnóstico, você pode exibir as entradas do log no Visualizador de eventos.

<div>


> [!NOTE]  
> Não recomendamos que você use as configurações de registro em log máximo, a menos que seja instruído a fazer isso pelos serviços de suporte ao cliente da Microsoft. O registro em log máximo esvazia recursos significativos e pode dar muitos "falsos positivos", ou seja, erros que são registrados apenas no máximo de logs, mas são realmente esperados e não são uma causa da preocupação. Também recomendamos que você não habilite o log de diagnóstico permanentemente. Use-o somente durante a solução de problemas.



</div>

Em cada log de visualizador de eventos, o Lync Server 2013 registra eventos informativos, de aviso e de erro. Monitore esses logs de perto para controlar os tipos de transações que estão sendo conduzidos nos servidores do Lync Server 2013. Você deve arquivar periodicamente os logs ou usar a substituição automática para evitar ficar sem espaço. Como os arquivos de log podem ocupar uma quantidade finita de espaço, aumente o tamanho do log (por exemplo, para 50 MB) e defina-o para substituir para que o servidor do Lync 2013 possa continuar a gravar novos eventos.

Você também pode automatizar a administração do log de eventos usando as seguintes ferramentas e tecnologias:

  - O System Center Operations Manager monitora a integridade e o uso dos servidores do Lync Server 2013. O pacote de gerenciamento do Lync Server 2013 para Operations Manager estende o Operations Manager fornecendo monitoramento especializado para servidores que executam o Lync Server 2013.

  - O pacote de gerenciamento do Lync Server 2013 para Operations Manager monitora a edição Standard e Enterprise do Lync Server 2013. Esta versão também incorpora o pacote de gerenciamento de qualidade da experiência (QoE) que anteriormente era um pacote de gerenciamento separado.

Os tipos monitorados são entradas do log de eventos, contadores de desempenho e monitoramento de estado de QoE. Esta versão do pacote de gerenciamento só monitora o Lync Server 2013 e o 2010 e não pode ser usada para monitorar o Office Communications Server 2007.

O pacote de gerenciamento fornece os seguintes recursos:

  - Alertas que indicam serviço que afeta eventos

  - Alertas que indicam configuração e outros problemas de impacto não relacionado ao serviço

  - Monitoramento de estado dos serviços do Lync Server

  - Conhecimento do produto: causa e resolução de problemas identificados

Para obter mais informações sobre o pacote de gerenciamento do Lync Server 2013, consulte [monitorando o Lync server 2013 com o System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Event Comb**   a ferramenta Event Comb coleta eventos específicos dos logs de eventos de vários computadores em um local central. Ele permite que você relate apenas as identificações de evento ou fontes de evento que ele especifica. Para obter mais informações sobre o Event Comb, consulte o site de [ferramentas de gerenciamento e bloqueio de conta](http://go.microsoft.com/fwlink/?linkid=35607) .

**Gatilhos de evento**   no Windows Server 2012 você pode "anexar uma tarefa a este evento" dentro do Visualizador de eventos do Windows, onde um administrador pode executar um programa, enviar uma mensagem de email ou exibir uma mensagem na tela. Para obter mais informações sobre esse recurso, consulte o tópico sobre o Windows Server 2008 R2 [executar uma tarefa em resposta a um determinado evento](http://technet.microsoft.com/en-us/library/cc748900.aspx). Você também pode usar ferramentas de linha de comando, como ' EventTrigger. exe ', para criar e consultar logs de eventos e associar programas a determinados eventos registrados. Usando Eventtriggers. exe, você pode criar gatilhos de eventos que executam programas quando ocorrem eventos específicos.

<div>

## <a name="see-also"></a>Confira também


[Visualizador de eventos do Windows](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

