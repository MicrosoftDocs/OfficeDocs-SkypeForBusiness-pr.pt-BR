---
title: 'Lync Server 2013: instalando relatórios de monitoramento do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5908e4eb8f18ef464a4c69cc31bffdc33a10416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a>Instalando relatórios de monitoramento do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-02-27_

Os relatórios de monitoramento do Microsoft Lync Server 2013 fornecem uma grande quantidade de informações sobre a qualidade e a quantidade das sessões de comunicação que ocorrem em sua organização. No entanto, os relatórios de monitoramento não são instalados automaticamente quando você instala o Lync Server 2013; em vez disso, você deve instalar os relatórios de monitoramento separadamente e somente após o Lync Server ter sido instalado no computador.

<div>


> [!NOTE]  
> Recomenda-se a instalação dos relatórios de monitoramento no mesmo computador em que o banco de dados de monitoramento está instalado. Isso simplifica o processo de atribuição de permissões para acessar os relatórios: a com a instalação dos relatórios de monitoramento no computador que hospeda o repositório de monitoramento, você não precisará configurar permissões que permitam que um banco de dados em um computador interaja com os Reporting Services em execução em outro computador.



</div>

Os relatórios de monitoramento do Lync Server incluem mais de 30 relatórios projetados para fornecer informações detalhadas sobre conferências, sessões ponto a ponto de mensagens instantâneas, registros de usuário, aplicativo de grupo de resposta e muito mais. Para a versão do 2013, os relatórios de monitoramento do Lync Server incluem uma série de aprimoramentos:

  - **Novos relatórios de qualidade de voz**. Esses novos relatórios incluem o [relatório de comparação de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), que compara a qualidade entre os diferentes tipos de chamadas (por exemplo, entre chamadas com fio e chamadas sem fio); e o [relatório de tempo de ingresso em conferência no Lync Server 2013](lync-server-2013-conference-join-time-report.md), que fornece informações sobre o tempo necessário para que os usuários ingressem em uma conferência.

  - **Relatórios aprimorados para analisar e solucionar problemas de sessões de vídeo e compartilhamento de aplicativos.** O [relatório de Resumo de qualidade de mídia no Lync server 2013](lync-server-2013-media-quality-summary-report.md) fornece uma maneira de analisar chamadas de compartilhamento de aplicativos e vídeo, enquanto o [relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) detalha o desempenho dos servidores que geram essas chamadas. As métricas de compartilhamento de aplicativos e vídeo também são reportadas pelo [relatório detalhe da sessão ponto a ponto no Lync server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) e no [relatório detalhe da conferência no Lync Server 2013](lync-server-2013-conference-detail-report.md).

  - **Desempenho de relatórios aprimorado**. Inclui tempos menores de resposta e recuperação de dados, bem como navegação mais rápida e fácil pelos relatórios.

Encontre mais informações sobre os relatórios individuais na documentação dos relatórios de monitoramento.

<div>


> [!NOTE]  
> Há outro novo relatório – subrelatório de detalhes da chamada de QoE – incluído no Lync Server 2013. Porém, seu uso é principalmente interno e o acesso a ele não pode ser feito diretamente.



</div>

Há duas maneiras de instalar os relatórios de monitoramento do Lync Server: você pode usar o assistente de implantação do Lync Server ou pode usar um script do Windows PowerShell incluído nos arquivos de instalação do Lync Server 2013. Independente do método usado para instalar os relatórios, primeiro você deve certificar-se de:

  - Ter o direito de adicionar uma função de banco de dados a uma conta de usuário no banco de dados de monitoramento.

  - Possuir a função Gerenciador de Conteúdo no SQL Server Reporting Services. Essa função concede o direito de implantar relatórios no SQL Server Reporting Services.

Para instalar os relatórios de monitoramento usando o Assistente de Implantação, siga as etapas a seguir:

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Assistente de implantação do Lync Server**.

2.  No Assistente de Implantação, clique em **Implantar Relatórios de Monitoramento** para iniciar o assistente Implantar Relatórios de Monitoramento.

3.  No assistente Implantar Relatórios de Monitoramento, na página **Especificar Banco de Dados de Monitoramento**, certifique-se de que o nome de domínio totalmente qualificado do computador que hospeda o repositório de monitoramento apareça na lista suspensa **Banco de dados de monitoramento** (caso tenha vários repositórios de monitoramento, será necessário selecionar o servidor correto na lista suspensa). Verifique se a instância correta do SQL Server aparece na caixa **Instância do SSRS (SQL Server Reporting Services)** (por exemplo, **atl-sql-001.litwareinc.com/archinst**) e clique em **Avançar**.

4.  Na página **especificar credenciais** , na caixa **nome do usuário** , digite o nome do domínio e o nome de usuário da conta a ser usada ao acessar os relatórios de monitoramento (por exemplo, **\\litwareinc kenmyer**). Se você não usar esse formato (nome de\\usuário do domínio), ocorrerá um erro.
    
    Digite a senha da conta do usuário na caixa **Senha** e, em seguida, clique em **Próximo**. Observe que não são necessários direitos especiais para esta conta. A conta receberá automaticamente o logon necessário e as permissões do banco de dados quando a configuração for concluída.

5.  Na página **Especificar Grupo Somente Leitura**, informe o nome de um grupo de segurança ao qual será concedido acesso somente leitura ao SQL Server Reporting Services na caixa Grupo de usuários. Por exemplo, para conceder aos administradores acesso somente leitura aos relatórios, digite **RTCUniversalReadOnlyAdmins**. Clique em **Avançar**.

6.  Na página **Executando Comandos**, clique em **Concluir**.

Os relatórios de monitoramento também podem ser instalados do Shell de gerenciamento do Lync Server executando o script DeployReports. ps1; Este script do Windows PowerShell pode ser encontrado na mídia de instalação do Lync Server \\na\\pasta Setup ReportingSetup. Para instalar relatórios de monitoramento usando DeployReports. ps1, digite um comando semelhante ao seguinte no prompt do Shell de gerenciamento:

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

Os parâmetros usados no comando anterior são descritos na tabela a seguir:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome do parâmetro</th>
<th>Obrigatório</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>storedUserName</p></td>
<td><p>Sim</p></td>
<td><p>Conta de usuário (no formato domínio\nome_de_usuário) usada para acessar o repositório de monitoramento; por exemplo:</p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p>Essa conta deve ter permissões do SQL Server e SQL Server Reporting Services especificadas previamente. Caso contrário, o script falhará.</p></td>
</tr>
<tr class="even">
<td><p>storedPassword</p></td>
<td><p>Sim</p></td>
<td><p>Senha da conta de usuário usada para acessar o repositório de monitoramento.</p></td>
</tr>
<tr class="odd">
<td><p>readOnlyGroupName</p></td>
<td><p>Não</p></td>
<td><p>Grupo de segurança local ou domínio cujos membros receberão acesso somente leitura aos relatórios de monitoramento. Observe que o script falhará se o grupo especificado não existir. Caso decida revogar as permissões posteriormente ou se decidir conceder permissão de acesso a outros usuários ou grupos, faça isso usando o gerenciador de relatórios do SQL Server Reporting Services.</p></td>
</tr>
<tr class="even">
<td><p>reportSqlServerInstance</p></td>
<td><p>Não</p></td>
<td><p>Instância do SQL Server que hospeda o Reporting Service. A instância de relatório deve ser especificada usando o nome de domínio totalmente qualificado do servidor de relatório. Por exemplo:</p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p>Se este parâmetro não for incluído, o script partirá do pressuposto de que o Reporting Services é hospedado pela mesma instância do SQL Server que hospeda o banco de dados de monitoramento.</p></td>
</tr>
<tr class="odd">
<td><p>monitoringDatabaseId</p></td>
<td><p>Não</p></td>
<td><p>Identidade de serviço do banco de dados de monitoramento. Você pode retornar as identidades dos bancos de dados de monitoramento executando este comando:</p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


Após a instalação dos relatórios de monitoramento, você deve usar o cmdlet Set-CsReportingConfiguration para configurar a URL usada para acessar esses relatórios. Essa tarefa pode ser realizada do Shell de gerenciamento do Lync Server executando o seguinte comando do Windows PowerShell. Observe que, apesar de recomendado, não é obrigatório usar o protocolo HTTPS ao configurar a URL do relatório:

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

No comando anterior, a propriedade ReportingUrl deve ser definida como a URL do Gerenciador de Relatórios usada pelo SQL Server 2008 R2 Reporting Services. Você pode determinar a URL do Gerenciador de Relatórios concluindo as etapas a seguir no computador onde o SQL Server Reporting Services foi instalado:

1.  Clique em Iniciar, Todos os Programas, Microsoft SQL Server 2008 R2, Ferramentas de Configuração e Gerenciador de Configuração do Reporting Services.

2.  Na caixa de diálogo Conexão de Configuração do Reporting Services, certifique-se de que o nome do computador do Reporting Services apareça na caixa Nome do Servidor. Selecione a instância do SQL Server na lista suspensa Instância do Servidor de Relatório e clique em Conectar.

3.  No Gerenciador de Configuração do Reporting Services, clique na URL do Gerenciador de Relatório. Uma ou mais URLs devem aparecer no painel URL do Gerenciador de Relatório. Todas essas URLs podem ser usadas como URL de relatório, embora, mais uma vez, seja recomendado que ReportingUrl use o protocolo HTTPS.

Se tiver configurado um banco de dados de espelho para monitoramento do banco de dados, você também deverá associar os Relatórios de Monitoramento com o banco de dados de espelho. Consulte o artigo [associando relatórios de monitoramento a um banco de dados espelho ao Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) para obter detalhes.

</div>

<span> </span>

</div>

</div>

</div>

