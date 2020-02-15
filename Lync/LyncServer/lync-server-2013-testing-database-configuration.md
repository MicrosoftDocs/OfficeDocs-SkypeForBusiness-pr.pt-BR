---
title: 'Lync Server 2013: testar configuração de banco de dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45781238f7fb8aa461e050f2e8f0cbf04e45a950
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Testando a configuração do banco de dados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-07-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Agenda de verificação</p></td>
<td><p>Diariamente</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões obrigatórias</p></td>
<td><p>Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins e ter privilégios de administrador no SQL Server.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsDatabase</strong> . Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsDatabase** verifica a conectividade para um ou mais bancos de dados do Lync Server 2013. Quando executado, o cmdlet **Test-CsDatabase** lê a topologia do Lync Server, tenta se conectar a bancos de dados relevantes e, em seguida, relata o êxito ou falha de cada tentativa. Se uma conexão pode ser realizada, o cmdlet também relatará tal informação como o nome do banco de dados, a informação de versão do SQL Server e o local de qualquer banco de dados espelho instalado.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O comando mostrado no Exemplo 1 verifica a configuração do banco de dados de Gerenciamento Central.

    Test-CsDatabase -CentralManagementDatabase

O exemplo 2 verifica todos os bancos de dados do Lync Server instalados no computador atl-sql-001.litwareinc.com.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

No Exemplo 3, a verificação é realizada apenas para o banco de dados de Arquivamento instalado no computador atl-sql-001.litwareinc.com. Observe que o parâmetro SqlInstanceName está incluído para especificar a instância do SQL Server (Archinst) onde o banco de dados de Arquivamento está localizado.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

O comando mostrado no Exemplo 4 verifica os bancos de dados instalados no computador local.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se a conectividade do banco de dados estiver configurada corretamente, você receberá uma saída semelhante a essa, com a propriedade sucede marcada como **true**:

SqlServerFqdn: atl-sql-001.litwareinc.com

SQLINSTANCENAME: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

DataSource

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Êxito: true

SqlServerFqdn: atl-sql-001.litwareinc.com

SQLINSTANCENAME: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: Lis

DataSource

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

Êxito: true

Se o banco de dados estiver configurado corretamente, mas ainda estiver disponível, o campo bem-sucedido será mostrado como **falso**, e avisos e informações adicionais serão fornecidos:

SqlServerFqdn: atl-sql-001.litwareinc.com

SQLINSTANCENAME: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

DataSource

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Êxito: falso

SqlServerFqdn: atl-cs-001.litwareinc.com

SQLINSTANCENAME: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: Lis

DataSource

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

Êxito: falso

Aviso: Test-CsDatabase encontrou erros. Consulte o arquivo de log para obter um

análise detalhada e para garantir que todos os erros (2) e avisos (0) sejam tratados

antes de continuar.

Aviso: resultados detalhados podem ser encontrados em

"C:\\os\\usuários\\que\\estão\\testando o local temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6. html ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsDatabase** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Esse comando falhará se o banco de dados estiver configurado incorretamente ou ainda não tiver sido implantado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

