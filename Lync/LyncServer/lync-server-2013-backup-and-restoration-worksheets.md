---
title: 'Lync Server 2013: planilhas de restauração e backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 161a8577558705c773974b1cc733337b29b6dbd5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532618"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Planilhas de backup e restauração para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-18_

O plano de backup e restauração da sua organização deve conter detalhes sobre como e quando você faz backup de dados e configurações. Você pode usar as planilhas apresentadas aqui para ajudá-lo a documentar essas informações para sua implantação específica e para os requisitos de backup e restauração da sua organização.

Use as planilhas a seguir para registrar as informações necessárias para fazer backup e restaurar o banco de dados, o repositório de arquivos e as informações de configurações de um pool do Lync Server ou servidor Standard Edition. Mantenha uma ou mais cópias dessas planilhas em um local seguro para que elas fiquem prontamente acessíveis se você precisar restaurar o Lync Server.

<div>


> [!NOTE]  
> As planilhas desta seção abrangem apenas as informações necessárias para restaurar os dados e as configurações dos bancos de dados e servidores do Lync Server. Se você precisar documentar outras informações de restauração, como as informações para reinstalação de sistemas operacionais e outros softwares, use os planos de implantação e os planos de backup e restauração da sua organização para atender a esses requisitos.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>Planilha de backup e restauração de banco de dados

Use a tabela a seguir para registrar as informações necessárias para fazer backup e restaurar os bancos de dados do Lync Server.

### <a name="database-information-for-backup-and-restoration"></a>Informações de banco de dados para backup e restauração

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Database</th>
<th>Nome do servidor (FQDN)</th>
<th>Agendamento de backup</th>
<th>Ferramenta de backup do banco de dados</th>
<th>Conjunto de backup</th>
<th>Destino do backup</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Banco de dados RTC no servidor back-end para dados de usuário</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsUserData</strong></p></td>
<td><p>Tdomínio</p>
<p>Validade</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>LcsLog (nome padrão) banco de dados no servidor de banco de dados de arquivamento</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Ferramenta de gerenciamento do SQL Server</p></td>
<td><p>Tdomínio</p>
<p>Validade</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Banco de dados LcsCdr no servidor do banco de dados de monitoramento para registros de detalhes de chamada (CDRs)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Ferramenta de gerenciamento do SQL Server</p></td>
<td><p>Tdomínio</p>
<p>Validade</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Banco de dados do QoEMetrics no Monitoring Database Server para dados de qualidade da experiência (QoE)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Ferramenta de gerenciamento do SQL Server</p></td>
<td><p>Tdomínio</p>
<p>Validade</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Banco de dados de chat persistente</p></td>
<td></td>
<td></td>
<td><p>Ferramenta de gerenciamento do SQL Server ou cmdlet <strong>Export-CsPersistentChatData</strong></p></td>
<td><p>Tdomínio</p>
<p>Validade</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Não é necessário backup ou restauração dos seguintes bancos de dados:

  - RTCDyn. Os dados do usuário transitório neste banco de dados não são necessários para a restauração do serviço.

  - RTCAb. O banco de dados do catálogo de endereços é automaticamente recriado a partir da lista de endereços global (GAL) nos serviços de domínio do Active Directory.

  - Rgsdyn. Os dados do serviço do grupo de resposta transitória neste banco de dados não são necessários para a restauração do serviço.

  - Cpsdyn. As informações dinâmicas para o aplicativo de estacionamento de chamadas não são necessárias para a restauração do serviço.

  - MgcComp. O banco de dados de conformidade para chat persistente não é necessário para a restauração do serviço.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Planilha de backup e restauração do repositório de arquivos

Use a tabela a seguir para registrar as informações necessárias para fazer backup e restaurar os repositórios de arquivos. Repositórios de arquivos contêm dados como metadados de conteúdo de reunião, reunião de logs de conformidade, logs de atualização para atualizações de dispositivo e arquivos de áudio para o grupo de resposta, estacionamento de chamada e aplicativos de anúncio.

### <a name="file-store-information-for-backup-and-restoration"></a>Informações do repositório de arquivos para backup e restauração

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Conteúdo</th>
<th>Nome do servidor (FQDN)</th>
<th>Agendamento de backup</th>
<th>Ferramenta de backup do sistema de arquivos</th>
<th>Compartilhamento de arquivos para backup *</th>
<th>Destino do backup</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Repositório de arquivos do Lync Server</p></td>
<td></td>
<td></td>
<td><p>Ferramenta de backup padrão, como Robocopy</p></td>
<td><p>No servidor de arquivos para Enterprise Edition. No Standard Edition por padrão, para a implantação do Standard Edition. Normalmente, um por site.</p></td>
<td></td>
<td><p>Não faça o backup dos arquivos com o nome <strong>Meeting.Active</strong>. Esses arquivos estão em uso e são bloqueados durante o andamento da reunião.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Planilha de backup e restauração de configurações

Use a tabela a seguir para registrar as informações necessárias para fazer backup e restaurar as configurações.

### <a name="settings-information-for-backup-and-restoration"></a>Informações de configuração para backup e restauração

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Database</th>
<th>Nome do servidor (FQDN)</th>
<th>Agendamento de backup</th>
<th>Ferramenta de backup</th>
<th>Nome do arquivo de configuração (. xml)</th>
<th>Localização do backup</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Banco de dados XDS no repositório de gerenciamento central para configuração de topologia (global)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsConfiguration</strong></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Lis o banco de dados no repositório de gerenciamento central para informações de local de E9-1-1 (global)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsLisConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Banco de dados do RgsConfig no servidor back-end para configuração de grupo de resposta (pool)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsRgsConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

