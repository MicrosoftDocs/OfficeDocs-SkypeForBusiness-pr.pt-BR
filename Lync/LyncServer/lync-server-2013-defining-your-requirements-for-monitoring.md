---
title: 'Lync Server 2013: Definindo seus requisitos de monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7a81f83cddca46a50f84fb20785a59b20a3db78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Definindo seus requisitos de monitoramento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-05_

A simplificação da implantação e da instalação do monitoramento no Microsoft Lync Server 2013 também simplificou os processos envolvidos na definição dos requisitos da sua organização para monitoramento. No entanto, ainda há vários problemas importantes que devem ser resolvidos antes de começar a instalar e configurar o Lync Server 2013:

**Que tipo de dados você deseja monitorar?** O Lync Server 2013 permite que você monitore dois tipos diferentes de dados: dados de registros de detalhes de chamadas (CDR) e dados de qualidade da experiência (QoE). A gravação de detalhes da chamada fornece uma maneira de acompanhar o uso de recursos do Lync Server, como chamadas telefônicas de voz sobre IP (VoIP); mensagens instantâneas (IM); transferências de arquivos; Conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos. Essas informações ajudam você a saber quais recursos do Lync Server estão sendo usados (e quais não são) e também fornece informações sobre quando esses recursos estão sendo usados. Os dados de qualidade da experiência permitem que você mantenha um registro da qualidade das chamadas de áudio e de vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de "tremulação" (diferenças no atraso do pacote).

Se você optar por habilitar o monitoramento no Lync Server 2013, poderá habilitar o monitoramento de CDR e o monitoramento de QoE, ou poderá optar por habilitar um tipo de monitoramento e deixar o outro tipo desabilitado. Por exemplo, suponha que seus usuários usem apenas as mensagens instantâneas e a transferência de arquivos e não façam chamadas de áudio nem vídeo. Nesse caso, pode não haver motivo para habilitar o monitoramento de QoE. Da mesma forma, o Lync Server torna mais fácil habilitar e desabilitar o monitoramento após a implantação do monitoramento. Por exemplo, você pode escolher implantar o monitoramento, mas deixar o monitoramento de QoE desabilitado a princípio. Se seus usuários começarem a enfrentar problemas com chamadas de áudio e vídeo, você pode habilitar o monitoramento de QoE e usar esses dados para ajudar você a resolver os problemas.

Não há nenhuma vantagem específica (ou desvantagem) de instalar o monitoramento ao mesmo tempo em que você instala o Lync Server versus a instalação do monitoramento após a instalação do Lync Server. O ponto único a ter em mente é que, antes de instalar o monitoramento, você deve selecionar um computador para hospedar o armazenamento de monitoramento de back-end e uma versão com suporte do SQL Server deve estar instalada e configurada nesse computador para que o computador possa ser usado para monitoramento . Se você já tiver instalado o SQL Server em um computador e esse computador estiver pronto para uso, você poderá instalar o monitoramento ao mesmo tempo em que instala o Lync Server. Se você não tiver um computador back-end pronto, pode prosseguir para instalar o Lync Server por si só e instalar o monitoramento sempre que o computador back-end estiver pronto para uso.

**Quando você deseja instalar o monitoramento?** A monitoração pode ser instalada e configurada ao mesmo tempo em que você instala e configurou o Lync Server 2013; o assistente de implantação do Lync Server oferece a você a oportunidade de associar seus pools de front-end a um banco de dados de monitoramento durante a configuração. Você também pode instalar o monitoramento após a instalação do próprio Lync Server; Isso pode ser feito usando o construtor de topologias para associar seus pools e servidores de front-end a um banco de dados de monitoramento e, em seguida, publicar a topologia revisada.

**De quantos bancos de dados de monitoramento de back-end você precisa?** Um único banco de dados de monitoramento pode oferecer suporte a dezenas de milhares de usuários (para o Microsoft Lync Server 2010, estima-se que um banco de dados posicionado para monitoramento e arquivamento pode dar suporte a 240.000 usuários). Além disso, um único banco de dados de monitoramento pode ser usado por vários Pools de Front-Ends; se você tem três Pools de Front-Ends em sua organização, é possível associar todos os três ao mesmo repositório de back-end.

Isso simplesmente significa que, para muitas organizações, a capacidade do banco de dados não será o fator decisivo ao determinar o número de bancos de dados de monitoramento de back-end que serão necessários. Em vez disso, uma consideração mais importante pode ser a velocidade da rede. Suponha que você tenha três Pools de Front-Ends, mas um deles está localizado em uma conexão de rede lenta. Nesse caso, você pode usar dois bancos de dados de monitoramento: um banco de dados para atender aos dois pools com a conexão de rede boa e um banco de dados separado para atender ao pool com a conexão de rede mais lenta.

Ao planejar sua infraestrutura de monitoramento, você também deve levar em conta que o Lync Server 2013 dá suporte ao uso de bancos de dados espelho. O "espelhamento do banco de dados" possibilita manter simultaneamente duas cópias de um banco de dados, com cada banco de dados residindo em um servidor diferente. Qualquer dado de tempo é gravado no banco de dados principal, e o mesmo dado também é gravado no banco de dados espelho. Se o banco de dados primário não funcionar ou se tornar indisponível, você pode "fazer failover" para o banco de dados espelho usando um comando simples do PowerShell do Lync Server. Por exemplo:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Isso é importante para fins de planejamento porque o espelhamento exigirá o dobro do número de bancos de dados exigidos: além de cada banco de dados primário, você precisará de um segundo banco de dados para agir como o espelho.

**Seus sites do Lync Server precisam de suas próprias configurações personalizadas de monitoramento?** Ao instalar o Lync Server 2013, você também instala as coleções globais das configurações de configuração de CDR e QoE; Essas coleções globais dão a você a capacidade de aplicar as mesmas configurações de CDR e QoE para toda a sua organização. In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

No entanto, em outros momentos você pode aplicar configurações diferentes em sites diferentes. Por exemplo, talvez você queira usar o monitoramento de CDR e QoE em seu site de Redmond, mas usar apenas o monitoramento de CDR em seu site de Dublin. Da mesma forma, você pode querer manter os dados de monitoramento por 60 dias no site de Redmond, mas manter esse tipo de dados por apenas 30 dias no site de Dublin. O Lync Server 2013 permite que você crie coleções separadas das configurações de configuração de CDR e QoE no escopo do site; Isso permite que você gerencie cada site de forma diferente. Isso habilita o gerenciamento de cada site de uma forma diferente (o que inclui a habilitação e desabilitação do monitoramento, assim como a definição das configurações de gerenciamento, como por quanto tempo os dados devem ser mantidos.)

Observe que você pode tomar essa decisão antes ou depois de implantar o monitoramento. Por exemplo, é possível implantar o monitoramento e gerenciar toda a organização usando as configurações globais. Se você mudar de ideia posteriormente, é possível criar uma coleção separada de configurações para, digamos, o site de Redmond, e usar essas configurações para gerenciar o monitoramento para Redmond. As configurações aplicadas no escopo do site sempre têm prioridade em relação às configurações aplicadas no escopo global. Se você mudar de ideia novamente, basta excluir as definições de configuração aplicadas ao site de Redmond. Quando uma coleção de configurações de site for removida, a coleção global de configurações será aplicada automaticamente para o site.

</div>

<span> </span>

</div>

</div>

</div>

