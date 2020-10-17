---
title: 'Lync Server 2013: configuração de integridade no Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0164a9e3003c130bc7b14a4312397a4559843c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528238"
---
# <a name="health-configuration-in-lync-server-2013"></a>Configuração de integridade no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Entre vários sites, artigos da base de conhecimento da Microsoft e ferramentas do Lync Server Resource Kit, os administradores que encontram problemas ao executar o Lync Server nunca estão longe de uma maneira de resolver esses problemas.

Obviamente, não há uma maneira de garantir que você nunca encontrará problemas no Lync Server 2013 porque o Lync Server pode ser afetado por muitas coisas, como falhas de rede e falhas de hardware, que o próprio produto não pode controlar. Ao implementar o monitoramento de integridade, os administradores podem identificar problemas potenciais antes que se transformem em problemas reais. Por exemplo, os administradores podem usar o monitoramento do Lync Server para identificar tendências e Tendencies. Por exemplo, um aumento contínuo no número de conferências de áudio/vídeo pode indicar uma necessidade de adicionar mais capacidade antes do sistema ficar sobrecarregado.

De modo semelhante, os administradores podem usar o System Center Operations Manager para fazer coisas como emitir alertas em tempo real quando os eventos especificados ocorrerem e executar transações sintéticas que testem proativamente o sistema. As transações sintéticas são usadas no Lync Server para verificar se os usuários podem concluir com êxito tarefas comuns, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas a um telefone localizado na rede telefônica pública comutada (PSTN). Por exemplo, a execução periódica desses testes pode alertá-lo sobre possíveis problemas com os usuários que fazem logon no Lync Server e lhe dá a oportunidade de corrigir o problema antes que a equipe de suporte seja inundada com chamadas de usuários que não podem fazer uma conexão. Usando o System Center Operations Manager para executar essas transações sintéticas, os administradores podem monitorar rotineiramente sua implantação do Lync Server continuamente por 24 horas por dia, sem ter que fazer muito nada além de responder a qualquer alerta que possa ser emitido.

<div>


> [!NOTE]  
> Para o Lync Server 2013, o pacote de gerenciamento do System Center Operations Manager também é capaz de detectar problemas "externos" que podem afetar adversamente o Lync Server. Por exemplo, os administradores podem ser notificados se o IIS (serviços de informações da Internet) ficar offline, os recursos do sistema em um computador do Lync Server estiverem abaixo de uma quantidade específica ou se um computador do Lync Server apresentar uma falha de hardware.



</div>

A configuração de integridade no Lync Server 2013 é criada sobre o System Center Operations Manager e o uso de pacotes de gerenciamento do Lync Server. Esses Pacotes de gerenciamento incluem um número de novos recursos e aprimoramentos, incluindo:

  - **Disponibilidade de cenário de qualquer local.** O pacote de gerenciamento do Lync Server 2010 introduziu o conceito de monitoramento da disponibilidade de cenário do usuário final com transações sintéticas. No Lync Server 2013, esses agentes têm mais transações sintéticas e podem ser executados a partir de uma variedade de locais dentro da empresa, de locais geográficos remotos fora da empresa, em filiais de escritório e em implantações do Lync Server 2010 para adicionar cobertura a implantações de borda herdadas.

  - **Logs de transação sintéticos.** Quando uma transação sintética falhar, os administradores têm acesso a logs HTML para ajudar a determinar onde está a falha. Isso inclui entender que ação falhou, a latência de cada ação, a linha de comando usado para executar o teste e o erro encontrado.

  - **Maior cobertura de confiabilidade de chamada.** O pacote de gerenciamento do Lync Server 2010 introduziu o alerta de confiabilidade de chamada para detectar problemas de conectividade sérios que afetam as chamadas de áudio de usuários finais. Os pacotes de gerenciamento do Lync Server 2013 adicionam cobertura para mensagens instantâneas de ponto a ponto (IM) e outros recursos básicos de conferência para maximizar a cobertura enquanto reduzem o ruído.

  - **Monitoramento de dependência.** Cenários do Lync Server podem falhar devido a uma variedade de fatores externos como o IIS offline, recursos limitados de CPU e memória e problemas de disco. Os novos pacotes de gerenciamento verificam várias dependências importantes para garantir que os administradores estejam cientes do impacto.

  - **Relatórios avançados.** Um conjunto de relatórios que ajuda os administradores a estimar a disponibilidade do cenários, planejar a capacidade e ver quais componentes têm mais problemas.

Os pacotes de gerenciamento também incluem uma variedade de recursos para ajudar a detectar e diagnosticar fornecer visibilidade em tempo real para a integridade da implantação do Lync Server. Esses recursos estão listados na seguinte tabela.

### <a name="management-pack-features"></a>Recursos do pacote de gerenciamento

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Recurso</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transações sintéticas</p></td>
<td><p>Os cmdlets do Windows PowerShell que podem ser executados de vários locais para garantir que os cenários de usuário final, como entrada, presença, IM e conferências, estejam prontamente disponíveis para os usuários finais.</p></td>
</tr>
<tr class="even">
<td><p>Alertas de confiabilidade de chamada</p></td>
<td><p>Consultas de banco de dados para CDR (Registros de detalhes de chamada). Esses registros são gravados por servidores front-end para refletir se os usuários finais foram capazes de se conectar a uma chamada ou por que uma chamada foi encerrada. Essas consultas resultam em alertas que indicam quando uma ampla variedade de usuários finais estão passando por problemas de conectividade de chamadas ponto a ponto ou a funcionalidade de conferência básica.</p></td>
</tr>
<tr class="odd">
<td><p>Alertas de qualidade de mídia</p></td>
<td><p>As consultas de banco de dados que visualizam os relatórios de Qualidade da Experiência (QoE) publicados por clientes ao fim de cada chamada. Essas consultas resultam em alertas que identificam cenários nos quais os usuários provavelmente observaram qualidade de mídia ruim durante chamadas e conferências. Os dados aproveitam métricas-chave como latência e perda de pacote, métricas que contribuem diretamente para a qualidade da chamada.</p></td>
</tr>
<tr class="even">
<td><p>Integridade do componente</p></td>
<td><p>Componentes individuais do servidor geram alertas usando logs de eventos e contadores de desempenho. Esses alertas indicam condições de falha que podem ter um impacto crítico em um ou mais cenários do usuário final. Esses alertas também podem indicar várias outras condições de falha, incluindo serviços que não estão funcionando, alta taxa de falhas, alta latência de mensagens ou problemas de conectividade.</p></td>
</tr>
<tr class="odd">
<td><p>Integridade da dependência</p></td>
<td><p>As falha podem ocorrer por vários motivos externos. Os pacotes de gerenciamento agora monitoram e coletam dados para algumas das dependência externas críticas que podem indicar vários problemas, incluindo a disponibilidade IIS, o uso da CPU e da memória por servidores e processos, além de métricas de disco.</p></td>
</tr>
</tbody>
</table>


Os alertas emitidos pelo sistema foram classificados em três categorias gerais:

  - **Alertas de alta prioridade.** Esses alertas indicam condições que resultaram em falhas no serviço para grandes grupos de usuários. Por exemplo, uma falha de componente em uma única máquina não é um alerta de alta prioridade porque o Lync Server 2013 tem recursos de alta disponibilidade internos. Em vez disso, os alertas de alta prioridade representam problemas sérios o suficiente para “tirar o sono dos administradores”. As falha detectadas por transações sintéticas e serviços offline (por exemplo, conferências de áudio/vídeo) são qualificadas como alertas de alta prioridade.

  - **Alertas de prioridade média.**. Esses alertas indicam condições que afetam um subconjunto de usuários ou indicam a degradação da qualidade da chamada. Isso inclui problemas como falhas de componentes, latência no estabelecimento da chamada ou qualidade de áudio degradada em uma chamada. Os alertas nesta categoria são têm monitoração de estado e indicam o status atual do problema. Por exemplo, considere que o tempo de estabelecimento de chamada excede o limite de alerta. Se o tempo de estabelecimento de chamadas retornar ao normal, esses alertas serão resolvidos automaticamente no System Center Operations Manager. A expectativa para esses alertas é de que um administrador os notará no mesmo dia útil.

  - **Outros alertas.** São alertas de componentes que podem afetar um usuário específico ou um subconjunto de usuários. Por exemplo, talvez o serviço de Catálogo de endereços não consiga analisar a entrada do Active Directory de determinado usuário. A expectativa para esses alertas é que que os administradores os solucionarão quando tiverem tempo disponível.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando o Lync Server 2013 para trabalhar com o System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Usando o registro avançado de transações sintéticas no Lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Usando o Microsoft SQL Server 2008 R2 como seu banco de dados do System Center Operations Manager para o Lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

