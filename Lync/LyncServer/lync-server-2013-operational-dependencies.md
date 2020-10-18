---
title: 'Lync Server 2013: dependências operacionais'
description: 'Lync Server 2013: dependências operacionais.'
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
ms.openlocfilehash: 4e240981f5dfded7c27f123c8483794ea3ffedff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579187"
---
# <a name="operational-dependencies-in-lync-server-2013"></a>Dependências operacionais no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-05-15_

A arquitetura de referência discutida neste documento ajudará a garantir que você tenha uma implantação do Lync Server 2013 que não só seja dimensionada para os requisitos da organização, mas seja arquitetada de acordo com as práticas recomendadas da Microsoft. Seja que, como pode ser a implementação do Lync Server 2013 é um serviço dinâmico e como qualquer outro serviço na empresa ainda requer o monitoramento e o gerenciamento proativo para manter alto nível de disponibilidade de serviço e qualidade de serviço para a empresa.

À medida que o Lync Server 2013 se torna muito ingerido na empresa diária da organização, é importante que o serviço seja gerenciado pelo gerenciamento de nível de serviço preciso e tangível. A arquitetura do sistema do Lync pode se tornar complexa e muito integrada e, para manter o gerenciamento de nível de serviço efetivo e estabelecer SLAs para o Lync Server 2013, torna-se essencial entender as dependências do sistema em outras plataformas e servidores. Igualmente importante é observar quais serviços comerciais, como os aplicativos integrados de voz e UC, são dependentes do Lync.

O Lync Server 2013 deve ser estabelecido observando todas as dependências mencionadas. O mapa de serviços permitirá que você formule um SLA entre o Lync e seu serviço dependente e forneça um local inicial para negociação de SLA.

A tabela a seguir lista os serviços de dependência típicos para uma infraestrutura do Lync. Cada uma dessas tecnologias deve ter seu próprio monitoramento proativo.

### <a name="typical-dependency-services"></a>Serviços de dependência típicos

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
<td><p>Gerenciamento do sistema – monitoramento e distribuição</p></td>
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
<td><p>Infraestrutura de telefonia – IP-PBX e gateways</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Serviços de nuvem</p></td>
<td></td>
</tr>
</tbody>
</table>


Presume-se que a organização seja operacionalmente desenvolvida em exercer funções básicas de gerenciamento de nível de serviço, como alteração, incidentes e gerenciamento de versão, conforme prescrito pelo MOF. A solução Lync deve ser adotada por essas funções e se tornar sujeita aos mesmos processos de gerenciamento operacional.

A criação das informações obtidas acima agora tem uma compreensão maior sobre o que pode impactar o serviço Lync na empresa. Para ajudar a garantir a disponibilidade e a qualidade do serviço do Lync Server 2013, as seguintes ferramentas de monitoramento devem acompanhar a implantação da arquitetura de referência:

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
<td><p>Implante pelo menos uma função de servidor de monitoramento do Lync Server 2013 por site central e configure o pacote de relatórios de QoE (qualidade da experiência).</p>
<p>Consulte a documentação de implantação do Lync Server 2013 para obter mais detalhes:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Implantando o monitoramento no Lync Server 2013</a></p></td>
<td><p>Sites centrais</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Compartilhamento de Internet de cada pool para sua instância mais próxima da função de servidor de monitoramento.</p></td>
<td><p>Sites centrais</p>
<p>Sites de filial</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 com o pacote de gerenciamento do Microsoft Lync Server 2013 (MP) importado.</p>
<p>O pacote de gerenciamento implementa o log de eventos tradicional e a instrumentação baseada em contador de desempenho é utilizada, além de habilitar a instrumentação recentemente disponível no Lync Server 2013.</p></td>
<td><p>Sites centrais</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Certifique-se de que a descoberta central para a descoberta de funções e componentes que precisam ser monitoradas seja automaticamente concluída com base em um script de descoberta central que lê o documento de topologia publicado no banco de dados de gerenciamento central.</p></td>
<td><p>Site central</p>
<p>Site de filial</p>
<p>Site de borda</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Implantar agentes do System Centre Operations Manager 2007 em todos os servidores implantados que executam o Lync Server.</p></td>
<td><p>Site central</p>
<p>Site de filial</p>
<p>Site de borda</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Certifique-se de que os alertas priorizados estão configurados para notificação:</p>
<p>Alertas de alta prioridade</p>
<p>Alertas de prioridade média</p>
<p>Outros alertas.</p></td>
<td><p>Site central</p>
<p>Site de filial</p>
<p>Site de borda</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Configure o monitoramento de porta para sua implantação.</p></td>
<td><p>Site central</p>
<p>Site de filial</p>
<p>Site de borda</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Configurar o monitoramento de URL para sua implantação</p></td>
<td><p>Site central</p></td>
</tr>
<tr class="odd">
<td><p>Integração do Lync e do System Center Operations Manager</p></td>
<td><p>Implantar a confiabilidade das chamadas e a qualidade da mídia MonitoringCall confiabilidade e monitoramento de qualidade de mídia use o computador do Monitoring Server como o nó do inspetor para monitorar a confiabilidade da chamada e a qualidade de mídia do Lync Server. Esses dois recursos consultam os bancos de dados do Monitoring Server para fazer a análise.</p></td>
<td><p>Site central</p>
<p>Site de filial</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Garantir que os limites de aviso de qualidade de mídia estejam configurados com precisão. A tabela a seguir indica a pontuação máxima média de opinião da rede por codec. Em produção, essas pontuações devem ser monitoradas por um período definido e os limites aceitáveis devem ser estabelecidos com base nas pontuações específicas da organização NMOS.</p></td>
<td><p>Site central</p>
<p>Site de filial</p></td>
</tr>
<tr class="odd">
<td><p>Inspetor de transações sintéticas do Lync Server 2013</p></td>
<td><p>Implantar um Lync Server dedicado para ser um inspetor de transações sintéticas.</p>
<p>As transações sintéticas são cmdlets do Windows PowerShell do Lync Server 2013 que são automaticamente disparados pelo pacote de gerenciamento em um intervalo predefinido. Eles são executados em um nó de Inspetor de transação sintética que é um servidor designado pelo administrador responsável pela descoberta e execução de STs para cada pool.</p>
<p>Não recomendamos o uso de um servidor do Microsoft Lync Server 2013 existente como um nó do Inspetor de transações sintéticas. Isso se deve aos altos requisitos de uso de CPU/memória para executar o STs. Use um novo computador servidor (ou um servidor virtual) para o nó do Inspetor de transações sintéticas.</p></td>
<td><p>Site central</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Implantando o nó Inspetor de transações sintéticas.</p>
<p>Consulte o documento de MonitoringCS_withSCOM.docx da documentação do UCTAP Connect.</p></td>
<td><p>Site central</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>Pontuação máxima de MOS de rede por codec

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
<th>NMOS máximo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC-chamada UC</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4.10</p></td>
</tr>
<tr class="even">
<td><p>UC-chamada UC</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Chamada de conferência</p></td>
<td><p>Siren</p></td>
<td><p>3,72</p></td>
</tr>
<tr class="even">
<td><p>UC-chamada PSTN</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>UC-chamada PSTN</p></td>
<td><p>G-711</p></td>
<td><p>3,61</p></td>
</tr>
</tbody>
</table>


Acima e acima das atividades anteriores de monitoramento do Pro-active, as tarefas de manutenção devem ser executadas para sites centrais, de borda e de filial, de forma diária, semanal e mensal, conforme definido no guia de operações do Lync RA.

</div>

<span> </span>

</div>

</div>

</div>

