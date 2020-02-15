---
title: 'Lync Server 2013: posicionamento de arquivos de log e dados do SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b15af558ed6082d28b7ae918d72dd7da94b1e499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Posicionamento de arquivos de log e dados do SQL Server para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Durante o planejamento e a implantação do Microsoft SQL Server 2012 ou do Microsoft SQL Server 2008 R2 SP1 para seu pool de front-ends do Lync Server 2013, uma consideração importante é o posicionamento de dados e arquivos de log em discos rígidos físicos para desempenho. A configuração de disco recomendada é implementar um conjunto de RAID 1 + 0 usando 6 eixos. Colocar todos os arquivos de banco de dados e de log usados pelo pool de front-ends e por funções e serviços associados do servidor (ou seja, servidor de arquivamento e monitoramento, serviço de grupo de resposta do Lync Server, serviço de estacionamento de chamadas do Lync Server) para o conjunto de drives RAID usando o Lync Server O assistente de implantação resultará em uma configuração que foi testada para um bom desempenho. Os arquivos de banco de dados e suas responsabilidades são detalhados na tabela a seguir.

<div>


> [!NOTE]  
> Se suas políticas e configurações do SQL Server exigem uma instalação mais especializada, o banco de dados e os arquivos de log podem ser instalados em qualquer local predefinido usando o Shell de gerenciamento do Lync Server. Consulte <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync server 2013</A> para obter mais detalhes.



</div>

### <a name="data-and-log-files-for-central-management-store"></a>Arquivos de dados e de log para o Repositório de Gerenciamento Central

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Arquivos de banco de dados do repositório de gerenciamento central</th>
<th>Objetivo do arquivo de dados ou log</th>
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
<td><p>Arquivo de dados do serviço de informações de local</p></td>
</tr>
<tr class="even">
<td><p>Lis. ldf</p></td>
<td><p>Log de transações para o arquivo de dados do serviço de informações de local</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>Arquivos de dados e de log de Usuário, Conferência e Catálogo de Endereços

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Principais arquivos do banco de dados do Lync Server 2013</th>
<th>Objetivo do arquivo de dados ou log</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTC. MDF</p></td>
<td><p>Dados persistentes do usuário (por exemplo, listas de controle de acesso (ACLs), contatos, conferências agendadas)</p></td>
</tr>
<tr class="even">
<td><p>RTC. ldf</p></td>
<td><p>Log de transações para dados RTC</p></td>
</tr>
<tr class="odd">
<td><p>RTCDyn. MDF</p></td>
<td><p>Mantém dados de usuário temporários (dados de tempo de execução de presença)</p></td>
</tr>
<tr class="even">
<td><p>RTCDyn. ldf</p></td>
<td><p>Log de transações para dados de RTCDyn</p></td>
</tr>
<tr class="odd">
<td><p>RTCAb. MDF</p></td>
<td><p>O banco de dados do catálogo de endereços RTC (comunicação em tempo real) é o repositório do SQL Server onde as informações do serviço de Catálogo de Endereços são armazenadas</p></td>
</tr>
<tr class="even">
<td><p>RTCAb. ldf</p></td>
<td><p>Log de transação para o serviço Catálogo de Endereços</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal. mdb</p></td>
<td><p>Hospeda o diretório de conferência</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds. MDF</p></td>
<td><p>Mantém o backup dos dados do usuário</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds. ldf</p></td>
<td><p>Log de transações para dados de Rtcxds</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>Arquivos de dados e log para o Estacionamento de Chamada e o Grupo de Resposta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Banco de dados de aplicativos</th>
<th>Objetivo do arquivo de dados ou log</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn. MDF</p></td>
<td><p>Banco de dados de informações dinâmicas para o aplicativo de estacionamento de chamada</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn. ldf</p></td>
<td><p>Log de transações para o arquivo de dados de aplicativo de estacionamento de chamada</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig. MDF</p></td>
<td><p>Arquivo de dados do serviço Grupo de Resposta do Lync Server para a configuração dos serviços</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig. ldf</p></td>
<td><p>Arquivo de log de transações para a configuração do aplicativo de grupo de resposta</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn. MDF</p></td>
<td><p>Arquivo de dados do serviço Grupo de Resposta para operações de tempo de execução</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn. ldf</p></td>
<td><p>Log de transação do arquivo de dados de tempo de execuçã do serviço Grupo de Resposta</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>Arquivos de dados e de log para o Servidor de Arquivamento e o Monitoring Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Arquivos de banco de dados de Arquivamento e Monitoramento</th>
<th>Objetivo do arquivo de dados ou log</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr. MDF</p></td>
<td><p>Repositório de dados do processo de registro de detalhes das chamadas (CDR) do servidor de monitoramento</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr. ldf</p></td>
<td><p>Log de transação dos dados CDR (registro de detalhes da chamada)</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics. MDF</p></td>
<td><p>Arquivo de dados de qualidade da experiência armazenado do servidor de monitoramento</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics. ldf</p></td>
<td><p>Log de transação dos dados de Monitoramento</p></td>
</tr>
<tr class="odd">
<td><p>LcsLog. MDF</p></td>
<td><p>Arquivo de dados para a retenção de mensagens instantâneas e dados de conferência em um servidor de arquivamento</p></td>
</tr>
<tr class="even">
<td><p>LcsLog. ldf</p></td>
<td><p>Log de transação dos dados de Arquivamento</p></td>
</tr>
</tbody>
</table>


Neste tópico, são feitas referências ao disco e ao conjunto RAID. Observe que na configuração de recursos do SQL Server, referir-se a um disco significa um dispositivo de hardware único. Um disco rígido com duas partições, uma que mantém os arquivos de log e a outra partição que contém os arquivos de dados, não é o mesmo que dois discos, cada um dedicado a arquivos de log ou de dados.

Em referência aos conjuntos RAID, há diversas tecnologias RAID diferentes de vários fornecedores. Além disso, com a proliferação de redes SAN, os conjuntos RAID dedicados a um único sistema estão mais raros. Você deve consultar seu fornecedor de RAID ou SAN para determinar qual é a melhor configuração para o seu layout de disco ao configurar o desempenho do SQL Server com o Lync Server 2013.

Observe também que nem todas as unidades de disco são criadas igualmente; algumas têm melhor desempenho melhor que outras. Mesmo as unidades do mesmo fabricante podem variar em desempenho devido a velocidade de rotação, tamanho do cache de hardware e outros fatores.

</div>

<span> </span>

</div>

</div>

</div>

