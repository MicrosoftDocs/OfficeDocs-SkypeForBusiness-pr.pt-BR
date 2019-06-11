---
title: 'Lync Server 2013: configuração do banco de dados de teste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805b62e234f7a5469d3af3677ba81478fb3abc8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Testar a configuração do banco de dados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-07-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Cronograma de verificação</p></td>
<td><p>Diário</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões necessárias</p></td>
<td><p>Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins e precisam ter privilégios de administrador no SQL Server.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsDatabase</strong> . Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsDatabase** verifica a conectividade de um ou mais bancos de dados do Lync Server 2013. Quando executado, o cmdlet **Test-CsDatabase** lê a topologia do Lync Server, tenta se conectar a bancos de dados relevantes e, em seguida, relata o êxito ou falha de cada tentativa. Se for possível fazer uma conexão, o cmdlet também reportará essas informações como o nome do banco de dados, as informações de versão do SQL Server e o local de todos os bancos de dados espelhados instalados.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O comando mostrado no exemplo 1 verifica a configuração do banco de dados de gerenciamento central.

    Test-CsDatabase -CentralManagementDatabase

O exemplo 2 verifica todos os bancos de dados do Lync Server instalados no computador atl-sql-001.litwareinc.com.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

No exemplo 3, a verificação é realizada somente para o banco de dados de arquivamento instalado no computador atl-sql-001.litwareinc.com. Observe que o parâmetro SQLINSTANCENAME está incluído para especificar a instância do SQL Server (Archinst) em que o banco de dados de arquivamento está localizado.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

O comando mostrado no exemplo 4 verifica os bancos de dados instalados no computador local.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se a conectividade do banco de dados estiver configurada corretamente, você receberá uma saída semelhante a isso, com a propriedade sucede marcada como **verdadeira**:

SqlServerFqdn: atl-sql-001.litwareinc.com

SQLINSTANCENAME: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

Inclusão

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Êxito: verdadeiro

SqlServerFqdn: atl-sql-001.litwareinc.com

SQLINSTANCENAME: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: Lis

Inclusão

SQLServerVersion :

ExpectedVersion: 3.1.1

InstalledVersion :

Êxito: verdadeiro

Se o banco de dados estiver configurado corretamente, mas ainda estiver disponível, o campo bem-sucedido será mostrado como **falso**, e avisos adicionais e informações serão fornecidos:

SqlServerFqdn: atl-sql-001.litwareinc.com

SQLINSTANCENAME: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

Inclusão

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Bem-sucedido: falso

SqlServerFqdn: atl-cs-001.litwareinc.com

SQLINSTANCENAME: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: Lis

Inclusão

SQLServerVersion :

ExpectedVersion: 3.1.1

InstalledVersion :

Bem-sucedido: falso

Aviso: Test-CsDatabase encontrou erros. Consulte o arquivo de log para obter uma

análise detalhada e para garantir que todos os erros (2) e avisos (0) sejam tratados

antes de continuar.

Aviso: os resultados detalhados podem ser encontrados em

"C:\\usuários\\\\testando\\AppData\\local\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6. html ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsDatabase** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Esse comando falhará se o banco de dados estiver configurado incorretamente ou ainda não foi implantado.

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

