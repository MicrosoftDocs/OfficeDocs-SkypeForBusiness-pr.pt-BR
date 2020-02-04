---
title: 'Lync Server 2013: Implantando o monitoramento'
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
ms.openlocfilehash: 637897bce0a160a8cc3b199ec6aee3ffd7375852
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>Implantando o monitoramento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-12-17_

Alterações importantes foram feitas na infraestrutura de monitoramento do Microsoft Lync Server 2013, começando com o fato de que a função de servidor de monitoramento foi preterida. Em vez de funções separadas de monitoração de servidor (que normalmente são necessárias às organizações para configurar computadores dedicados para atuar como servidores de monitoramento), os serviços de monitoramento são agora posicionados em cada servidor front-end. Entre outras coisas, essa alteração ajuda a:

  - Diminua o número de funções de servidor necessárias ao implementar o Lync Server 2013. Nesse caso, decrementar a função de servidor do Monitoring Server também ajuda a reduzir os custos, eliminando a necessidade de manter os servidores dedicados para monitoramento.

  - Reduzir a complexidade da instalação e da administração do Lync Server. Posicionando automaticamente os serviços de monitoramento em cada servidor front-end que você não precisa mais instalar, configurar e gerenciar a função do servidor de monitoramento.

<div>


> [!NOTE]  
> A função de servidor de arquivamento também foi substituída no Lync Server 2013. Como os serviços de monitoramento, os serviços de arquivamento do Lync Server 2013 agora são posicionados em cada servidor front-end. Isso é importante observar simplesmente porque o monitoramento e o arquivamento muitas vezes compartilham a mesma instância do banco de dados do SQL Server.



</div>

Como você pode esperar, essas alterações têm um grande impacto sobre como os serviços de monitoramento são instalados e gerenciados. Por exemplo, como a função de servidor de monitoramento não existe mais, o nó do servidor de monitoramento foi removido do construtor de topologias do Lync Server; por sua vez, isso significa que você não usa mais o novo assistente do construtor de topologias para adicionar um novo servidor de monitoramento à sua topologia. (Esse assistente não existe mais.) Em vez disso, você geralmente implementará serviços de monitoramento na sua topologia completando as duas etapas a seguir:

1.  Habilitar o monitoramento ao mesmo tempo em que você configura um novo pool do Lync Server. (No Lync Server 2013, o monitoramento é habilitado ou desabilitado em uma base de pool por pool.) Observe que você pode habilitar o monitoramento de um pool sem coletar dados de monitoramento, um processo explicado na seção como configurar a gravação de detalhes da chamada e as configurações de qualidade da experiência desta documentação.

2.  Associando um repositório de monitoramento (ou seja, um banco de dados de monitoramento) ao novo pool. Observe que um único repositório pode ser associado a vários pools. Dependendo do número de usuários hospedados em seus pools de registradores, isso significa que não é necessário configurar um banco de dados de monitoramento separado para cada um dos seus pools. Em vez disso, um único repositório de monitoramento pode ser usado por vários pools.

Embora normalmente seja mais fácil habilitar o monitoramento ao mesmo tempo em que o novo pool é criado, também é possível criar um novo pool com o monitoramento desabilitado. Se o fizer, você pode usar o Construtor de Topologias mais tarde para habilitar o serviço: o Construtor de Topologias fornece uma maneira de habilitar ou desabilitar o monitoramento para um pool ou de associar um pool a um repositório de monitoramento diferente. Lembre-se de que, mesmo que não haja mais uma função de servidor de monitoramento, você ainda precisará criar uma ou mais lojas de monitoramento: bancos de dados back-end usados para armazenar os dados coletados pelo serviço de monitoramento. Esses bancos de dados back-end podem ser criados usando o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012.

<div>


> [!NOTE]  
> Se o monitoramento tiver sido habilitado para um pool, você poderá desabilitar o processo de coleta de dados de monitoramento sem precisar alterar a topologia: o Shell de gerenciamento do Lync Server permite que você desative (e, em seguida, habilite novamente) registro de detalhes da chamada (CDR) ou qualidade coleta de dados da experiência (QoE). Para obter mais informações, consulte a seção Como Configurar o Registro de Detalhes das Chamadas e Configurações de Qualidade da Experiência deste documento.



</div>

Outro aprimoramento importante para monitorar no Lync Server 2013 é o fato de que os relatórios de monitoramento do Lync Server agora dão suporte a IPv6: os relatórios que usam o campo endereço IP exibirão endereços IPv4 ou IPv6, dependendo de: 1) a consulta SQL sendo usada; e 2) onde ou não o endereço IPv6 está armazenado no banco de dados de monitoramento.

<div>


> [!NOTE]  
> Verifique se o Tipo de inicialização do serviço SQL Server Agent é Automático e se o serviço SQL Server Agent está sendo executado para a Instância SQL que está mantendo os bancos de dados de Monitoramento para que os Trabalhos de manutenção do SQL Server de monitoramento padrão possam ser executados com base em seu agendamento sob o controle do Serviço SQL Server Agent.



</div>

Esta documentação descreve o processo de instalação e configuração de relatórios de monitoramento e monitoramento para o Lync Server 2013. A documentação fornece instruções passo a passo que o ajudarão a:

  - Habilitar o monitoramento na sua topologia e associar um repositório de monitoramento a um Pool de Front-Ends.

  - Instale os relatórios do SQL Server Reporting Services e do Lync Server Monitoring. Relatórios de Monitoramento são relatórios pré-configurados que fornecem visões diferentes das informações armazenadas em um banco de dados de monitoramento.

  - Configurar a coleta de dados de registro de detalhes de chamadas (CDR) e qualidade da experiência (QoE). A gravação de detalhes da chamada fornece uma maneira de acompanhar o uso de recursos do Lync Server, como chamadas telefônicas de voz sobre IP (VoIP); mensagens instantâneas (IM); transferências de arquivos; Conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos. Métricas de QoE acompanham a qualidade de chamadas de áudio e vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, ruídos de fundo e o volume de "tremulação" (diferenças no atraso de pacotes).

  - Limpar manualmente registros de CDR e/ou QoE do banco de dados de monitoramento.

</div>

<span> </span>

</div>

</div>

</div>

