---
title: 'Lync Server 2013: dependências operacionais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26e7de821dee778d4b0b1e9aa105669635abaf6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Dependências operacionais no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-05-15_

A arquitetura de referência abordada neste documento ajudará a garantir que você tenha uma implantação do Lync Server 2013 que não só pode ser dimensionada para os requisitos da organização, mas é arquitetada de acordo com as práticas recomendadas da Microsoft. Seja que, como pode ser a implementação do Lync Server 2013 é um serviço dinâmico e como qualquer outro serviço da empresa, ainda exige monitoramento e gerenciamento proativo para manter o alto nível de disponibilidade do serviço e a qualidade do serviço para os negócios.

Como o Lync Server 2013 se torna profundamente refinado na empresa diária da organização, é importante que o serviço seja gerenciado pelo gerenciamento de nível de serviço preciso e tangível. A arquitetura do sistema do Lync pode se tornar complexa e muito integrada e para manter o gerenciamento de nível de serviço efetivo e estabelecer SLAs para o Lync Server 2013 se torna importante compreender as dependências do sistema em outras plataformas e servidores. Igualmente importante é observar quais serviços comerciais, como aplicativos integrados de voz e UC, se dependem do Lync.

O Lync Server 2013 deve ser estabelecido anotando todas as dependências mencionadas. O mapa de serviços permitirá que você formule um SLA entre o Lync e seu serviço dependente e forneça um local inicial para a negociação de SLA.

A tabela a seguir lista os serviços de dependência típicos para uma infraestrutura do Lync. Cada uma dessas tecnologias deve ter seu próprio monitoramento proativo.

### <a name="typical-dependency-services"></a>Serviços típicos de dependência

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Serviço de dependência</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sistemas operacionais</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Hardware do servidor</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infraestrutura de chave pública</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Serviço de nomes de domínio</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Serviços de banco de dados</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Serviços de armazenamento</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gerenciamento de sistema – monitoramento e distribuição</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Serviços de segurança-antivírus</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infraestrutura de rede-Internet</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Infraestrutura de rede – interna (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infraestrutura de telefonia – PBX IP e gateways</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Serviços de nuvem</p></td>
<td></td>
</tr>
</tbody>
</table>


Pressupõe-se que a organização seja operacionalmente amadureceda em exercer funções básicas de gerenciamento de nível de serviço, como alteração, incidentes e gerenciamento de versão, conforme prescrito pela MOF. A solução do Lync deve ser adotada por essas funções e se tornar sujeita aos mesmos processos de gerenciamento operacional.

A criação de informações obtidas acima agora tem uma compreensão maior sobre o que pode impactar o serviço do Lync na empresa. Para ajudar a garantir a disponibilidade e a qualidade do serviço do Lync Server 2013, as seguintes ferramentas de monitoramento devem acompanhar a implantação da arquitetura de referência:

### <a name="monitoring-tools"></a>Ferramentas de monitoramento

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Descrição</th>
<th>Site aplicável</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 Monitoring Server</p></td>
<td><p>Implante pelo menos uma função de servidor de monitoramento do Lync Server 2013 por site central e configure o Reporting Pack de qualidade (QoE).</p>
<p>Consulte a documentação de implantação do Lync Server 2013 para obter mais detalhes:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Implantando o monitoramento no Lync Server 2013</a></p></td>
<td><p>Sites centrais</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Compartilhamento de cada pool para a sua instância mais próxima da função de servidor de monitoramento.</p></td>
<td><p>Sites centrais</p>
<p>Sites de filiais</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 com o pacote de gerenciamento do Microsoft Lync Server 2013 (MP) importado.</p>
<p>O pacote de gerenciamento implementa a instrumentação baseada em log de eventos e com base em desempenho e contador de desempenho, além de habilitar a instrumentação recém-disponível no Lync Server 2013.</p></td>
<td><p>Sites centrais</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Verifique se a descoberta central para descoberta de funções e componentes que precisam ser monitoradas é automaticamente concluída com base em um script de descoberta central que lê o documento de topologia publicado no banco de dados de gerenciamento central.</p></td>
<td><p>Local central</p>
<p>Site de filial</p>
<p>Site de borda</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Implantar agentes do System Centre Operations Manager 2007 em todos os servidores implantados que executam o Lync Server.</p></td>
<td><p>Local central</p>
<p>Site de filial</p>
<p>Site de borda</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Certifique-se de que os alertas priorizados estejam configurados para notificação:</p>
<p>Alertas de alta prioridade</p>
<p>Alertas de prioridade média</p>
<p>Outros alertas.</p></td>
<td><p>Local central</p>
<p>Site de filial</p>
<p>Site de borda</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Configure o monitoramento de porta para a implantação.</p></td>
<td><p>Local central</p>
<p>Site de filial</p>
<p>Site de borda</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Configurar o monitoramento de URL para a implantação</p></td>
<td><p>Local central</p></td>
</tr>
<tr class="odd">
<td><p>Integração do Lync e do System Center Operations Manager</p></td>
<td><p>Implantar a confiabilidade das chamadas e a qualidade da mídia MonitoringCall confiabilidade e monitoramento de qualidade da mídia use o computador do Monitoring Server como o nó do inspetor para monitorar a confiabilidade da chamada e a qualidade da mídia do Lync Server. Esses dois recursos consultam os bancos de dados do Monitoring Server para fazer a análise.</p></td>
<td><p>Local central</p>
<p>Site de filial</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Verifique se os limites de aviso de qualidade de mídia estão configurados com precisão. A tabela a seguir indica a pontuação máxima média de opinião da rede por codec. Em produção, essas classificações devem ser monitoradas por um período definido e os limites aceitáveis devem ser estabelecidos com base nas pontuações específicas do NMOS da organização.</p></td>
<td><p>Local central</p>
<p>Site de filial</p></td>
</tr>
<tr class="odd">
<td><p>Inspetor de transação sintética do Lync Server 2013</p></td>
<td><p>Implantar um Lync Server dedicado para ser um inspetor de transação sintética.</p>
<p>As transações sintéticas são cmdlets do Windows PowerShell do Lync Server 2013 que são automaticamente disparados pelo pacote de gerenciamento em um intervalo predefinido. Eles são executados em um nó de Inspetor de transação sintética que é um servidor designado pelo administrador responsável pela descoberta e execução do STs para cada pool.</p>
<p>Não recomendamos que você use um servidor Microsoft Lync Server 2013 existente como um nó Inspetor de transação sintética. Isso se deve a altos requisitos de uso de CPU/memória para executar o STs. Use um novo computador servidor (ou um servidor virtual) para o nó Inspetor de transação sintética.</p></td>
<td><p>Local central</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Implantando o nó Inspetor de transações sintéticas.</p>
<p>Consulte o documento MonitoringCS_withSCOM. docx da documentação do UCTAP Connect.</p></td>
<td><p>Local central</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>Máximo de pontuações de rede MOS por codec

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Cenário</th>
<th>Codec</th>
<th>NMOS máx.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC – chamada UC</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4,10</p></td>
</tr>
<tr class="even">
<td><p>UC – chamada UC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Chamada de conferência</p></td>
<td><p>Siren</p></td>
<td><p>3,72</p></td>
</tr>
<tr class="even">
<td><p>UC – chamada PSTN</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>UC – chamada PSTN</p></td>
<td><p>G-711</p></td>
<td><p>3,61</p></td>
</tr>
</tbody>
</table>


Acima e acima das atividades anteriores de monitoramento do Pro-active, as tarefas de manutenção devem ser executadas para sites centrais, de periféricos e de filiais com base diária, semanal e mensal, conforme definido no guia de operações de RA do Lync.

</div>

<span> </span>

</div>

</div>

</div>

