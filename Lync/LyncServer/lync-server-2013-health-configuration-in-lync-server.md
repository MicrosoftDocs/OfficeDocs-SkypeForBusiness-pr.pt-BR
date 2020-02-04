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
ms.openlocfilehash: 14a4da3ec3f06dfb573ef7e9422bdd6b751db636
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Configuração de integridade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Entre vários sites, artigos da base de dados de conhecimento Microsoft e ferramentas do Lync Server Resource Kit, administradores que encontram problemas ao executar o Lync Server nunca estão longe de uma maneira de solucionar esses problemas.

Obviamente, não há nenhuma maneira de garantir que você nunca encontrará problemas com o Lync Server 2013 porque o Lync Server pode ser afetado por muitas coisas, como falhas de rede e falhas de hardware, que o próprio produto não pode controlar. Ao implementar o monitoramento de integridade, os administradores podem identificar possíveis problemas antes que eles se transformem em problemas reais. Por exemplo, os administradores podem usar o monitoramento do Lync Server para identificar tendências e tendências. Por exemplo, um aumento constante no número de conferências de áudio/vídeo pode sugerir a necessidade de adicionar capacidade Antes de o sistema ficar sobrecarregado.

De forma semelhante, os administradores podem usar o System Center Operations Manager para fazer coisas como problemas em alertas em tempo real quando ocorrem eventos especificados e para executar transações sintéticas que testem proativamente o sistema. As transações sintéticas são usadas no Lync Server para verificar se os usuários podem concluir com êxito tarefas comuns, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado na rede telefônica pública comutada (PSTN). Por exemplo, a execução periódica desses testes pode alertá-lo sobre possíveis problemas com os usuários que fazem logon no Lync Server, além de oferecer a você uma chance de corrigir o problema antes que sua equipe de suporte seja inundada com chamadas de usuários que não conseguem fazer uma conexão. Ao usar o System Center Operations Manager para executar essas transações sintéticas, os administradores podem monitorar rotineiramente a implantação do Lync Server continuamente por 24 horas por dia, sem ter que fazer muitas nada além de responder a qualquer alerta que possa ser emitido.

<div>


> [!NOTE]  
> Para o Lync Server 2013, o pacote de gerenciamento do System Center Operations Manager também é capaz de detectar problemas "externos" que podem afetar negativamente o Lync Server. Por exemplo, os administradores podem ser notificados se os serviços de informações da Internet (IIS) estiverem offline, os recursos do sistema em um computador do Lync Server ficarão abaixo de um valor especificado ou um computador com o Lync Server sofrer uma falha de hardware.



</div>

A configuração de integridade no Lync Server 2013 é criada com base no System Center Operations Manager e com o uso de pacotes de gerenciamento do Lync Server. Esses pacotes de gerenciamento incluem vários novos recursos e aprimoramentos, incluindo:

  - **Disponibilidade do cenário de qualquer local.** O pacote de gerenciamento do Lync Server 2010 introduziu o conceito de monitoramento da disponibilidade do cenário do usuário final com transações sintéticas. No Lync Server 2013, esses agentes têm transações mais sintéticas e podem ser executados em uma variedade de locais na empresa, de locais geográficos remotos fora da empresa, em filiais do escritório e no Lync Server 2010 implantações para adicionar cobertura a implantações de bordas legadas.

  - **Logs de transações sintéticas.** Quando uma transação sintética falha, os administradores têm acesso aos logs HTML para ajudar a determinar o que falhou. Isso inclui compreender qual ação falhou, a latência de cada ação, a linha de comando usada para executar o teste e o erro encontrado.

  - **Maior cobertura de confiabilidade de chamadas.** O pacote de gerenciamento do Lync Server 2010 introduziu alertas de confiabilidade de chamadas para detectar problemas de conectividade graves que afetam as chamadas de áudio de usuários finais. Os pacotes de gerenciamento do Lync Server 2013 adicionam cobertura para mensagens instantâneas ponto a ponto (IM) e outros recursos básicos de conferência para maximizar a cobertura e, ao mesmo tempo, reduzir o ruído.

  - **Monitoramento de dependências.** Os cenários do Lync Server podem falhar devido a diversos fatores externos, como o IIS offline, recursos de memória e CPU limitados e problemas de disco. Os novos pacotes de gerenciamento verificam várias dependências críticas para garantir que os administradores tenham conhecimento do impacto.

  - **Relatórios avançados.** Um conjunto de relatórios para ajudar os administradores a estimar a disponibilidade do cenário, planejar a capacidade e ver quais componentes estão apresentando a maioria dos problemas.

Os pacotes de gerenciamento também incluem uma variedade de recursos para ajudar a detectar e diagnosticar fornecer visibilidade em tempo real para a implantação de integridade do Lync Server. Esses recursos estão listados na tabela a seguir.

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
<td><p>Transações Sintéticas</p></td>
<td><p>Cmdlets do Windows PowerShell que podem ser executados em diversos locais para garantir que os cenários do usuário final, como entrada, presença, mensagens instantâneas e conferências, estejam prontamente disponíveis para os usuários finais.</p></td>
</tr>
<tr class="even">
<td><p>Alertas de confiabilidade da chamada</p></td>
<td><p>Consultas de banco de dados para registros de detalhes de chamadas (CDR). Esses registros são escritos por servidores front-end para refletir se os usuários finais puderam se conectar a uma chamada ou por que uma chamada foi encerrada. Essas consultas resultam em alertas que indicam quando uma ampla variedade de usuários finais está experimentando problemas de conectividade para chamadas ponto a ponto ou funcionalidade básica de conferência.</p></td>
</tr>
<tr class="odd">
<td><p>Alertas de qualidade de mídia</p></td>
<td><p>Consultas de banco de dados que procuram relatórios de qualidade da experiência (QoE) publicadas por clientes ao final de cada chamada. Essas consultas resultam em alertas que apontam cenários em que os usuários podem estar experimentando uma qualidade de mídia ruim durante chamadas e conferências. Os dados são criados com base em métricas-chave, como latência e perda de pacotes, que são conhecidos por contribuir diretamente para a qualidade da chamada.</p></td>
</tr>
<tr class="even">
<td><p>Integridade do componente</p></td>
<td><p>Os componentes individuais do servidor geram alertas usando logs de eventos e contadores de desempenho. Esses alertas indicam condições de falha que podem afetar seriamente um ou mais cenários de usuário final. Esses alertas também podem indicar uma variedade de outras condições de falha, incluindo serviços que não estão em execução, altas tarifas de falha, alta latência de mensagem ou problemas de conectividade.</p></td>
</tr>
<tr class="odd">
<td><p>Integridade da dependência</p></td>
<td><p>As falhas podem ocorrer por vários motivos externos. Os pacotes de gerenciamento agora monitoram e coletam dados de algumas das principais dependências externas que podem indicar problemas graves, incluindo a disponibilidade do IIS, a CPU e o uso da memória de servidores e processos e métricas de disco.</p></td>
</tr>
</tbody>
</table>


Os alertas emitidos pelo sistema foram classificados em três categorias gerais:

  - **Alertas de alta prioridade.** Esses alertas indicam condições que causarão interrupções de serviço para grupos grandes de usuários. Por exemplo, uma falha de componente em uma única máquina não é um alerta de alta prioridade porque o Lync Server 2013 tem recursos de alta disponibilidade internos. Em vez disso, alertas de alta prioridade representam problemas sérios "para ativar os administradores à noite." Paralisações detectadas por transações sintéticas e serviços offline (por exemplo, videoconferência/videoconferência) qualificadas como alertas de alta prioridade.

  - **Alertas de prioridade média.**. Esses alertas indicam condições que afetam um subconjunto de usuários ou indicam a degradação da qualidade da chamada. Isso inclui problemas como falhas de componentes, latência no estabelecimento da chamada ou qualidade de áudio reduzida em chamada. Os alertas nessa categoria são stateful e indicam o status atual do problema. Por exemplo, suponha que seus tempos de estabelecimento de chamadas ultrapassem o limite de alerta. Se o tempo de estabelecimento da chamada retornar ao normal, esses alertas serão resolvidos automaticamente no System Center Operations Manager. A expectativa para esses alertas é que um administrador irá vê-los no mesmo dia útil.

  - **Outros alertas.** Esses são alertas de componentes que podem afetar um usuário ou subconjunto específico de usuários. Por exemplo, talvez o serviço de catálogo de endereços não pudesse analisar a entrada do Active Directory de um determinado usuário. A expectativa desses alertas é que os administradores os receberão quando tiverem tempo disponível.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando o Lync Server 2013 para trabalhar com o System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Usar o log avançado de transações sintéticas no Lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Usar o Microsoft SQL Server 2008 R2 como seu banco de dados do System Center Operations Manager para o Lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

