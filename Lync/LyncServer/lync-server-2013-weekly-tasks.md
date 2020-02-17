---
title: 'Lync Server 2013: tarefas semanais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87d3f87b37b8c0fe29c4dee76467a9e07931551a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a>Tarefas semanais no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-08-17_

Tarefas semanais geralmente estão relacionadas à coleta e análise de logs e relatórios.

<div>

## <a name="archive-event-logs"></a>Arquivar logs de eventos

Se os logs de eventos não estiverem configurados para substituir eventos conforme necessário, eles devem ser arquivados e excluídos regularmente. Esta ação é especialmente importante para logs de segurança, que podem ser necessários ao investigar tentativas de violação de segurança.

Sua organização terá que definir políticas e procedimentos para o arquivamento de logs.

</div>

<div>

## <a name="create-reports"></a>Criar relatórios

Criar relatórios de status para ajudar no planejamento de capacidade, análises de SLA e análise de desempenho. Use dados diários do log de eventos e do monitor do sistema para criar relatórios sobre o disco, memória e uso da CPU. Use o System Center Operations Manager para gerar relatórios de disponibilidade e tempo de atividade.

Sua organização terá que definir políticas e procedimentos para relatórios de status.

</div>

<div>

## <a name="incident-reports"></a>Relatórios de incidentes

Realize uma auditoria semanal dos relatórios de incidentes da sua organização relacionados ao Lync Server. Essa auditoria deve incluir o seguinte:

  - Os incidentes gerados acima, resolvidos e pendentes.

  - Soluções para incidentes não resolvidos.

  - Atualizando relatórios para incluir novos tíquetes de problema.

  - Atualização de um repositório de documentos para guias de solução de problemas e postagem de panes sobre interrupções.

Como o sistema de controle de incidentes da sua organização é uma opção independente do Lync Server, instruções específicas ou ponteiros não estão disponíveis. Consulte a documentação do sistema que sua organização escolheu.

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>Verificar os logs e o desempenho do IIS

Executar uma revisão semanal dos logs e desempenho dos serviços de informações da Internet (IIS). Para obter mais informações sobre como monitorar os logs e o desempenho do IIS, consulte [Windows Server 2003 serviços de informações da Internet (IIS) visão geral do log de eventos](http://go.microsoft.com/fwlink/?linkid=36077). A revisão deve incluir o seguinte:

  - Contadores de cache de serviço Web para monitorar o cache de serviço da Web.

  - Contadores ASPs (Active Server Pages) para monitorar aplicativos executados como ASPs.

</div>

<div>

## <a name="generate-database-reports"></a>Gerar relatórios de banco de dados

**Para gerar relatórios sobre o banco de dados SQL**

1.  Abra o Lync Server 2013.

2.  Na árvore do console, expanda o nó floresta, expanda **pools corporativos**e clique no pool para o qual você deseja gerar um relatório de banco de dados.

3.  No painel de detalhes, clique na guia **banco de dados** .

4.  Na guia **banco de dados** , faça o seguinte:
    
    1.  Para exibir o nome do banco de dados, expanda **configurações gerais**e exiba o nome do banco de dados.
    
    2.  Para recuperar as estatísticas de resumo do usuário atual do pool, expanda **relatórios de resumo do usuário**, clique em **ir**e exibir os resultados.
    
    3.  Para recuperar os dados atuais por usuário para um único usuário do pool, expanda **relatórios por usuário**, digite o URI do SIP do usuário, clique em **ir**e exibir os resultados.

Para recuperar as estatísticas atuais de Resumo de conferência para o pool, expanda **relatórios de Resumo de conferências**, clique em **ir**e exiba os resultados.

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>Verificar atualizações de segurança e Lync Server

Identificar quaisquer Service Packs, hotfixes ou atualizações novos. Se apropriado, teste-os em um laboratório de teste e use os procedimentos de controle de alteração para organizar a implantação nos servidores de produção. Além disso, as atualizações de componentes do Lync Server agora estão disponíveis como parte do Windows Update. Todas as atualizações de componentes do Lync Server devem ser atualizadas ao mesmo tempo em todos os servidores que estão executando o Lync Server para o qual as atualizações são aplicáveis.

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>Executar o analisador de práticas recomendadas do Lync Server 2013

A ferramenta Analisador de práticas recomendadas do Lync Server 2013 é uma ferramenta de diagnóstico que coleta informações de configuração e determina se a configuração é definida de acordo com as práticas recomendadas da Microsoft. A documentação da ferramenta é no [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).

A ferramenta compara os dados de configuração da sua implantação com um conjunto de regras predefinidas para o Lync Server e relata possíveis problemas. Para cada problema relatado, a ferramenta fornece a configuração atual no ambiente do Lync Server e a configuração recomendada.

Com o acesso à rede correto, a ferramenta pode examinar seu AD DS e servidores que estão executando o Lync Server 2013 para fazer o seguinte:

  - Realize verificações de integridade de forma proativa, verificando se a configuração está definida de acordo com as práticas recomendadas

  - Gerar uma lista de problemas, como definições de configuração subótimas ou opções não suportadas ou não recomendadas

  - Avaliar a integridade geral de um sistema

  - Ajudar a solucionar problemas específicos

  - Solicitar que você baixe as atualizações se elas estiverem disponíveis

  - Fornecer documentação online e local sobre problemas relatados e incluir dicas de solução de problemas

  - Gerar informações de configuração que possam ser capturadas para revisão posterior

Verifique se o RTCBPA. msi está instalado em todos os servidores do Lync Server 2013 e gere um relatório de verificação de integridade semanal. Anote os resultados e corrija, se necessário.

</div>

<div>

## <a name="review-sla-performance-figures"></a>Analisar os valores de desempenho do SLA

Verifique os dados principais de desempenho da semana anterior. Analise o desempenho em relação aos requisitos do SLA. Identificar tendências e itens que não atingiram seus destinos.

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>Analisar o pacote de gerenciamento do System Center Operations Manager e os relatórios de qualidade da experiência

Obtenha e revise o pacote de gerenciamento do Lync Server 2013 e os relatórios de qualidade da experiência.

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>Geração e exibição de relatórios de banco de dados para pools corporativos

**Para gerar relatórios de pool**

1.  Abra o Lync Server 2013.

2.  Na árvore do console, expanda o nó floresta, expanda **pools corporativos**e clique no pool para o qual você deseja gerar um relatório de banco de dados.

3.  No painel de detalhes, clique na guia **banco de dados** .

4.  Na guia **banco de dados** , faça o seguinte:
    
    1.  Para exibir o nome do banco de dados, expanda **configurações gerais**e exiba o nome do banco de dados.
    
    2.  Para recuperar as estatísticas de resumo do usuário atual do pool, expanda **relatórios de resumo do usuário**, clique em **ir**e exibir os resultados.
    
    3.  Para recuperar os dados atuais por usuário para um único usuário do pool, expanda **relatórios por usuário**, digite o URI do SIP do usuário, clique em **ir**e exibir os resultados.

Para recuperar as estatísticas atuais de Resumo de conferência para o pool, expanda **relatórios de Resumo de conferências**, clique em **ir**e exiba os resultados.

Para cada pool de empresas, os administradores podem usar a guia **banco de dados** para exibir o nome do banco de dados e recuperar e exibir relatórios do banco de dados.

### <a name="database-reports-and-descriptions"></a>Relatórios e descrições de bancos de dados

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Seção</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Relatórios de resumo do usuário</p></td>
<td><p>Dbanalyze/v/Report: diag [/SqlServer: valor]</p>
<p>Esta seção exibe informações de agregação sobre usuários em um pool, como o número de usuários habilitados, o número médio de contatos por usuário e o número de usuários para recursos específicos.</p>
<p>Ao usar esses relatórios, as seguintes informações podem ser úteis:</p>
<ul>
<li><p>Um usuário habilitado é um usuário habilitado para o Lync Server 2013 usando o snap-in usuários e computadores do Active Directory.</p></li>
<li><p>Um usuário ativo é um usuário que fez logon ou está registrado.</p></li>
<li><p>Os relatórios de resumo também oferecem um conjunto de informações estatísticas sobre contatos. Essas estatísticas são válidas apenas para a população de usuários que fizeram logon pelo menos uma vez e que têm pelo menos um contato. Consequentemente, você normalmente não verá um número mínimo de contatos de 0. Devido a esse comportamento, se um usuário não tiver contatos (mas estiver ativo, se o usuário tiver registrado), você poderá ver: &lt;vazio&gt; para alguns campos de estatísticas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Relatórios por usuário</p></td>
<td><p>Dbanalyze/v/Report: Disk [/SqlServer: value]</p>
<p>Ao contrário dos relatórios de resumo, que são calculados sobre uma população de usuário, eles são relatórios sobre um usuário específico.</p></td>
</tr>
<tr class="odd">
<td><p>Relatórios de Resumo de conferências</p></td>
<td><p>Dbanalyze/v/Report: conf [/SqlServer: valor]</p>
<p>Esta seção exibe informações de agregação sobre estatísticas de Resumo de conferência para o pool, como o número de conferências ativas e o número total de participantes.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>Executando analisador de utilização de largura de banda

O analisador de utilização de largura de banda é uma ferramenta que cria relatórios sobre vários modos de exibição de consumo de largura de banda pelos pontos de extremidade UC nos links WAN na rede corporativa. Esses relatórios podem ser usados para entender o padrão de consumo de largura de banda atual e para ajudar no planejamento da capacidade de largura de banda. Ele também itera na capacidade de largura de banda atribuída a vários links.

Esta ferramenta faz o seguinte:

  - Gera relatórios específicos para o uso de áudio na rede

  - Ajuda no planejamento de capacidade mais eficaz e na iteração na capacidade de largura de banda atribuída a vários links

O analisador de utilização de largura de banda pode gerar gráficos de capacidade de largura de banda e relatórios de uso. Eles são:

  - Todos os links WAN na rede corporativa

  - Filtrado por links WAN selecionados que foram escolhidos

  - Filtrado por links WAN que excederam a capacidade de link

  - Filtrado por links WAN que estavam usando a largura de banda provisionada

  - Filtrar por links WAN que atingiram níveis críticos (um uso de largura de banda maior que 90 por cento da capacidade de largura de banda do link WAN)

  - Filtrado por tipo de link WAN — links de site de rede, links entre regiões e links dentro de um site

  - Filtrado por região de rede

A documentação da ferramenta está disponível na [documentação das ferramentas do Lync Server 2013 Resource Kit](http://go.microsoft.com/fwlink/?linkid=623245).

</div>

<div>

## <a name="see-also"></a>Confira Também


[Lista de verificação de tarefas semanais](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

