---
title: 'Lync Server 2013: Posicionamento de dados do Servidor SQL e do arquivo de log'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a528ba7a348ebb5c8f865a795f8b1f1c1bc30cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Posicionamento de dados do Servidor SQL e do arquivo de log para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Durante o planejamento e a implantação do Microsoft SQL Server 2012 ou do Microsoft SQL Server 2008 R2 SP1 para seu pool Front-end do Lync Server 2013, uma consideração importante é o posicionamento de dados e arquivos de log em discos rígidos físicos para fins de desempenho. A configuração de disco recomendada é implementar um conjunto de RAID 1 + 0 usando 6 eixos. Colocar todos os arquivos de banco de dados e log que são usados pelo pool de front-end e os serviços e funções de servidor associadas (ou seja, servidor de arquivamento e monitoramento, serviço de grupo de resposta do Lync Server, serviço de estacionamento de chamadas do Lync Server) para o conjunto de drives RAID usando o Lync Server O assistente de implantação fará com que uma configuração que tenha sido testada para obter um bom desempenho. Os arquivos de banco de dados e o que são responsáveis são detalhados na tabela a seguir.

<div>


> [!NOTE]  
> Se as suas políticas e configurações do SQL Server exigirem uma instalação mais especializada, os arquivos de banco de dados e de log poderão ser instalados em qualquer local predefinido usando o Shell de gerenciamento do Lync Server. Consulte <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync server 2013</A> para obter mais detalhes.



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Arquivos de dados e log para o repositório de gerenciamento central

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Arquivos de banco de dados do repositório de gerenciamento central</th>
<th>Finalidade de log ou arquivo de dados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XDS. ldf</p></td>
<td><p>Arquivo de log de transações para o repositório de gerenciamento central</p></td>
</tr>
<tr class="even">
<td><p>XDS. MDF</p></td>
<td><p>Mantém a configuração da topologia atual do Lync Server 2013, conforme definido e publicado pelo construtor de topologias</p></td>
</tr>
<tr class="odd">
<td><p>Lis. MDF</p></td>
<td><p>Arquivo de dados do serviço de informações de localização</p></td>
</tr>
<tr class="even">
<td><p>Lis. ldf</p></td>
<td><p>Log de transação para o arquivo de dados do local Information Service</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Dados e arquivos de log para o usuário, a conferência e o catálogo de endereços

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Principais arquivos de banco de dados do Lync Server 2013</th>
<th>Finalidade de log ou arquivo de dados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. MDF</p></td>
<td><p>Dados persistentes do usuário (por exemplo, listas de controle de acesso (ACLs), contatos, conferências agendadas)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Log de transação para dados RTC</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. MDF</p></td>
<td><p>Mantém dados do usuário transitórios (dados de tempo de execução de presença)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Log de transação para dados do RTCDyn</p></td>
</tr>
<tr class="odd">
<td><p>RTCAb. MDF</p></td>
<td><p>O banco de dados do catálogo de endereços de comunicação em tempo real (RTC) é o repositório do SQL Server onde as informações do serviço de catálogo de endereços são armazenadas</p></td>
</tr>
<tr class="even">
<td><p>RTCAb. ldf</p></td>
<td><p>Log de transação para o serviço de catálogo de endereços</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal. mdb</p></td>
<td><p>Hospeda o diretório de conferências</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds. MDF</p></td>
<td><p>Mantém o backup dos dados do usuário</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds. ldf</p></td>
<td><p>Log de transação para dados do Rtcxds</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Dados e arquivos de log para estacionamento de chamada e grupo de resposta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Banco de dados de aplicativos</th>
<th>Finalidade de log ou arquivo de dados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn. MDF</p></td>
<td><p>Banco de dados de informações dinâmicas para o aplicativo parque de chamadas</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn. ldf</p></td>
<td><p>Log de transação para o arquivo de dados do aplicativo de estacionamento de chamada</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. MDF</p></td>
<td><p>Arquivo de dados do serviço de grupo de resposta do Lync Server para a configuração dos serviços</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>Arquivo de log de transação para a configuração de aplicativo de grupo de resposta</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. MDF</p></td>
<td><p>Arquivo de dados do serviço de grupo de resposta para operações de tempo de execução</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Log de transação para o arquivo de dados do tempo de execução do serviço de grupo de resposta</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Arquivos de dados e log para servidor de arquivamento e monitoramento

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Arquivar e monitorar arquivos de banco de dados</th>
<th>Finalidade de log ou arquivo de dados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. MDF</p></td>
<td><p>Repositório de dados para o processo de registro de detalhes de chamadas (CDR) do servidor de monitoramento</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Log de transação para dados de registro de detalhes de chamadas (CDR)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. MDF</p></td>
<td><p>Arquivo de dados de qualidade da experiência armazenados do servidor de monitoramento</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Log de transações para monitorar dados</p></td>
</tr>
<tr class="odd">
<td><p>LcsLog. MDF</p></td>
<td><p>Arquivo de dados para a retenção de mensagens instantâneas e dados de conferência em um servidor de arquivamento</p></td>
</tr>
<tr class="even">
<td><p>LcsLog. ldf</p></td>
<td><p>Log de transações para arquivar dados</p></td>
</tr>
</tbody>
</table>


Neste tópico, as referências são feitas em disco e em conjunto de RAID. Observe que, na configuração de recursos do SQL Server, fazer referência a um disco significa um único dispositivo de hardware. Uma unidade de disco rígido com duas partições, uma contendo arquivos de log e a outra partição que contém os arquivos de dados, não é igual a dois discos, cada um dedicado a arquivos de log ou de dados.

Em referência a conjuntos RAID, há várias tecnologias RAID diferentes de vários fornecedores. E, com a proliferação de redes de área de armazenamento (SAN), os conjuntos de RAID dedicados a um sistema único são mais raros. Você deve consultar seu fornecedor de RAID ou SAN para determinar qual é a melhor configuração para o seu layout de disco ao configurar o desempenho do SQL Server com o Lync Server 2013.

Observe também que nem todas as unidades de disco são criadas igualmente; alguns têm melhor desempenho do que outros. Mesmo os drives do mesmo fabricante podem variar em desempenho devido à velocidade rotacional, tamanho do cache de hardware e outros fatores.

</div>

<span> </span>

</div>

</div>

</div>

