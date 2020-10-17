---
title: 'Lync Server 2013: definindo seus requisitos de monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f116fec331c252934c42e624c36813218d8f9ca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504318"
---
# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Definindo seus requisitos de monitoramento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-05_

A simplificação da implantação e da instalação do monitoramento no Microsoft Lync Server 2013 também simplificava os processos envolvidos na definição dos requisitos de sua organização para monitoramento. No entanto, ainda há vários problemas importantes que devem ser abordados antes de você começar a instalar e configurar o Lync Server 2013:

**Que tipo de dados você deseja monitorar?** O Lync Server 2013 permite monitorar dois tipos diferentes de dados: dados de registro de detalhes de chamada (CDR) e dados de qualidade da experiência (QoE). A gravação de detalhes da chamada oferece uma maneira de rastrear o uso de recursos do Lync Server, como chamadas telefônicas de voz sobre IP (VoIP); mensagens instantâneas (IM); transferências de arquivos; Conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos. Essas informações ajudam você a saber quais recursos do Lync Server estão sendo usados (e quais não são) e também fornece informações sobre quando esses recursos estão sendo usados. Os dados de qualidade da experiência permitem manter um registro da qualidade das chamadas de áudio e vídeo feitas em sua organização, incluindo coisas como o número de pacotes de rede perdidos, ruído de fundo e a quantidade de "tremulação" (diferenças no atraso do pacote).

Se você optar por habilitar o monitoramento no Lync Server 2013, poderá habilitar o monitoramento de CDR e o monitoramento de QoE, ou poderá optar por habilitar um tipo de monitoramento e deixar o outro tipo desabilitado. Por exemplo, suponha que seus usuários apenas utilizem mensagem instantânea e transferência de arquivos e não realizem chamadas de áudio ou vídeo. Neste caso, pode não haver motivo para habilitar o monitoramento QoE. Da mesma forma, o Lync Server facilita a habilitação e desabilitação do monitoramento após a implantação do monitoramento. Por exemplo, você pode escolher implantar o monitoramento, mas deixar inicialmente o monitoramento QoE desabilitado. Se seus usuários começam a enfrentar problemas com chamadas de áudio e vídeo, habilite o monitoramento QoE e use estes dados para ajudar você a resolver problemas.

Não há nenhuma vantagem específica (ou desvantagem) de instalar o monitoramento ao mesmo tempo em que você instala o Lync Server vs. instalando o monitoramento após a instalação do Lync Server. O único ponto a lembrar é que, antes de instalar o monitoramento, você deve selecionar um computador para hospedar o repositório de monitoramento de backend e uma versão suportada do SQL Server deve ser instalada e configurada neste computador antes de que possa ser usado para monitoramento. Se você já tiver instalado o SQL Server em um computador e se ele estiver pronto para uso, você poderá instalar o monitoramento ao mesmo tempo em que instalar o Lync Server. Se você não tiver um computador de back-end pronto, você pode prosseguir para instalar o Lync Server sozinho e, em seguida, instalar o monitoramento sempre que o computador back-end estiver pronto para uso.

**Quando você deseja instalar o monitoramento?** O monitoramento pode ser instalado e configurado ao mesmo tempo em que você instala e configurou o Lync Server 2013; o assistente de implantação do Lync Server fornecerá a oportunidade de associar seus pools de front-ends a um banco de dados de monitoramento durante a configuração. Como alternativa, você pode instalar o monitoramento depois que o Lync Server for instalado; Isso pode ser feito usando o construtor de topologias para associar seus pools de front-ends e servidores a um banco de dados de monitoramento e, em seguida, publicando a topologia revisada.

**Quantos bancos de dados de monitoramento de backend você precisa?** Um único banco de dados de monitoramento pode dar suporte a dezenas de milhares de usuários (para o Microsoft Lync Server 2010, estima que um banco de dados posicionado para monitoramento e arquivamento pode suportar 240.000 usuários). Além disso, um único banco de dados de monitoramento pode ser usado por vários pools de front-end; se você possui três pools de front-end na sua organização, é possível associar todos os três pools com o mesmo repositório de backend.

Isto apenas simplifica que, para muitas organizações, a capacidade do banco de dados não será o fator decisivo ao determinar o número de bancos de dados de monitoramento de backend que serão necessários. Ao invés disso, uma consideração mais importante pode ser a velocidade da rede. Suponha que você possui três pools de front-end, mas um destes pools está localizado em uma conexão de rede lenta. Neste caso, você pode desejar usar dois bancos de dados de monitoramento: um banco de dados para serviço dos dois pools com boa conexão de rede e um banco de dados separado para serviço do pool com a conexão de rede mais lenta.

Ao planejar sua infraestrutura de monitoramento, você também deve levar em conta que o Lync Server 2013 suporta o uso de bancos de dados espelho. "Espelhamento do banco de dados" oferece uma forma de manter simultaneamente duas cópias de um banco de dados, cada banco de dados residindo em um servidor diferente. Qualquer dado de tempo é gravado no banco de dados primário que o mesmo dado também é gravado no banco de dados de espelho. Se o banco de dados primário falhar ou se tornar indisponível, você poderá "fazer failover" para o banco de dados espelho usando um comando simples do Lync Server PowerShell. Por exemplo:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Isto é importante para fins de planejamento porque o espelhamento exigirá o dobro do número exigido de bancos de dados: além de cada banco de dados primário, você precisará de um segundo banco de dados para agir como o espelho.

**Os seus sites do Lync Server precisam de suas próprias configurações de monitoramento personalizadas?** Ao instalar o Lync Server 2013, você também instala as coleções globais das definições de configuração de CDR e QoE; Essas coleções globais oferecem a capacidade de aplicar as mesmas configurações de CDR e QoE para toda a sua organização. Em vários casos, isto pode ser suficiente: frequentemente, digamos, se você tiver o monitoramento CDR habilitado para todos os seus usuários.

No entanto, pode haver momentos quando você deseja aplicar configurações diferentes para sites diferentes. Por exemplo, talvez você deseje usar o monitoramento CDR e QoE em seu site Redmond, mas usar apenas o monitoramento CDR em seu site Dublin. Da mesma forma, você pode desejar manter os dados de monitoramento por 60 dias no site Redmond, mas precisa apenas manter este tipo de dados por 30 dias no site Dublin. O Lync Server 2013 permite que você crie coleções separadas das definições de configuração de CDR e QoE no escopo do site; Isso permite que você gerencie cada site de forma diferente. (Isto inclui a habilitação e desabilitação do monitoramento, assim como a definição das configurações de gerenciamento como quanto tempo os dados devem ser mantidos.)

Observe que você pode tomar esta decisão antes de implantar o monitoramento ou após implantar o monitoramento. Por exemplo, é possível implantar o monitoramento e gerenciar toda a organização usando as configurações globais. Se você mudar de ideia posteriormente, é possível criar um conjunto separado de configurações para, digamos, o site Redmond, e usa estas configurações para gerenciar o monitoramento para Redmond. (As configurações aplicadas no escopo do site sempre têm precedência sobre as configurações aplicadas no escopo global.) Se você mudar de ideia novamente, basta excluir as definições de configuração aplicadas ao site Redmond. Quando um conjunto de configurações de site é removido, o conjunto global de configurações será aplicado automaticamente para este site.

</div>

<span> </span>

</div>

</div>

</div>

