---
title: 'Lync Server 2013: Implantando monitoramento'
description: 'Lync Server 2013: Implantando o monitoramento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1821198ddd0b4164f6932122aa9cf00ac34aada
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561537"
---
# <a name="deploying-monitoring-in-lync-server-2013"></a>Implantando o monitoramento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-12-17_

Alterações importantes foram feitas na infraestrutura de monitoramento do Microsoft Lync Server 2013, começando com o fato de que a função de servidor de monitoramento foi preterida. Em vez de separar funções Servidor de Monitoramento (o que normalmente exigia que as organizações definissem computadores dedicados para agir como servidores de Monitoramento), os serviços de monitoramento são agora colocados em cada servidor de Front End. Juntamente com outras coisas, essa alteração ajuda a:

  - Diminuir o número de funções de servidor necessárias ao implementar o Lync Server 2013. Neste caso, reduzir a função de servidor Servidor de Monitoramento também ajuda a reduzir custos, eliminando a necessidade de manter servidores dedicados para monitoramento.

  - Reduzir a complexidade da instalação e administração do Lync Server. Colocando automaticamente os serviços de monitoramento em cada servidor de Front End, não é mais necessário instalar, configurar e gerenciar a função Servidor de Monitoramento.

<div>


> [!NOTE]  
> A função de servidor de arquivamento também foi preterida no Lync Server 2013. Como os serviços de monitoramento, os serviços de arquivamento do Lync Server 2013 agora estão posicionados em cada servidor front-end. Isso é importante observar simplesmente porque o monitoramento e o arquivamento frequentemente compartilham a mesma instância de banco de dados do SQL Server.



</div>

Como você pode esperar, essas alterações têm um grande impacto sobre como os serviços de monitoramento são instalados e gerenciados. Por exemplo, como a função de servidor de monitoramento não existe mais, o nó do Monitoring Server foi removido do construtor de topologias do Lync Server; por sua vez, isso significa que você não usa mais o assistente de novo servidor de monitoramento do construtor de topologias para adicionar um novo servidor de monitoramento à sua topologia. (Esse assistente não existe mais.) Em vez disso, você geralmente implementará serviços de monitoramento em sua topologia executando as duas etapas a seguir:

1.  Habilitar o monitoramento ao mesmo tempo você configura um novo pool do Lync Server. (No Lync Server 2013, o monitoramento é habilitado ou desabilitado em um pool por pool.) Observe que você pode habilitar o monitoramento de um pool sem realmente coletar dados de monitoramento, um processo explicado na seção Configuring Call Detail Recording and Quality of Experience Settings desta documentação.

2.  Associando um repositório de monitoramento (ou seja, um banco de dados de monitoramento) ao novo pool. Observe que um único repositório pode ser associado a vários pools. Dependendo do número de usuários hospedados em seus pools de registradores, isso significa que não é necessário configurar um banco de dados de monitoramento separado para cada um dos seus pools. Em vez disso, um único repositório de monitoramento pode ser usado por vários pools.

Embora normalmente seja mais fácil habilitar o monitoramento ao mesmo tempo em que o novo pool é criado, também é possível criar um novo pool com o monitoramento desabilitado. Se o fizer, você pode usar o Construtor de Topologias mais tarde para habilitar o serviço: o Construtor de Topologias fornece uma maneira de habilitar ou desabilitar o monitoramento para um pool ou de associar um pool a um repositório de monitoramento diferente. Tenha em mente que embora não exista mais uma função Servidor de Monitoramento, ainda será necessário criar um ou mais repositórios de monitoramento: bancos de dados de backend usados para armazenar os dados reunidos pelo serviço de monitoramento. Esses bancos de dados de backend podem ser criados usando o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012.

<div>


> [!NOTE]  
> Se o monitoramento tiver sido habilitado para um pool, você poderá desabilitar o processo de coleta de dados de monitoramento sem ter que alterar sua topologia: o Shell de gerenciamento do Lync Server oferece uma maneira de desabilitar (e depois reabilitar) a coleta de dados da chamada (registro de detalhes das chamadas) ou de QoE (qualidade da experiência). Para mais informações, consulte a seção Como Configurar o Registro de Detalhes de Chamadas e Configurações de Qualidade de Experiência deste documento.



</div>

Outro aprimoramento importante do monitoramento no Lync Server 2013 é o fato de que os relatórios de monitoramento do Lync Server agora dão suporte a IPv6: os relatórios que usam o campo endereço IP exibirão endereços IPv4 ou IPv6, dependendo de: 1) a consulta SQL que está sendo usada; e 2) onde ou não o endereço IPv6 é armazenado no banco de dados de monitoramento.

<div>


> [!NOTE]  
> Certifique-se de que o tipo de inicialização do serviço do SQL Server Agent seja automático e que o serviço SQL Server Agent esteja em execução para a instância SQL que está mantendo os bancos de dados de monitoramento, para que os trabalhos de manutenção do SQL Server de monitoramento padrão possam ser executados em sua base agendada sob o controle do serviço do SQL Server Agent.



</div>

Esta documentação o orienta durante o processo de instalação e configuração de relatórios de monitoramento e monitoramento do Lync Server 2013. A documentação fornece instruções passo a passo que o ajudarão a:

  - Habilitar o monitoramento na sua topologia e associar um repositório de monitoramento a um pool de Front End.

  - Instale o SQL Server Reporting Services e os relatórios de monitoramento do Lync Server. Relatórios de Monitoramento são relatórios pré-configurados que fornecem visões diferentes das informações armazenadas em um banco de dados de monitoramento.

  - Configurar o registro de detalhes de chamadas (CDR) e a coleta de dados de Qualidade de Experiência (QoE). A gravação de detalhes da chamada oferece uma maneira de controlar o uso de recursos do Lync Server, como chamadas telefônicas de voz sobre IP (VoIP); mensagens instantâneas (IM); transferências de arquivos; Conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos. Métricas de QoE rastreiam a qualidade de chamadas de áudio/vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, ruídos de fundo e o volume de "tremulação" (diferenças no intervalo de pacotes).

  - Limpar manualmente registros de CDR e/ou QoE do banco de dados de monitoramento.

</div>

<span> </span>

</div>

</div>

</div>

