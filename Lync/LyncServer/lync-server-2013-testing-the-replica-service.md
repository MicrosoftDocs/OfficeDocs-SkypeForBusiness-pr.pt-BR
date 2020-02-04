---
title: 'Lync Server 2013: testando o serviço de réplica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Testando o serviço de réplica no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-11-03_


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
<td><p>Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsReplica</strong> . Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsReplica** verifica se o serviço de réplica do Lync Server 2013 está em execução no computador local. O cmdlet **Test-CsReplica** executa tarefas como:

  - Verificando o status do agente do Replicator e dos serviços de agente de log centralizado

  - verificar se as portas necessárias foram abertas no firewall do Windows

  - Certifique-se de que os grupos de segurança do Active Directory e do computador local necessários estão presentes.

Observe que esse cmdlet deve ser executado localmente. Ou seja, ele deve ser executado no mesmo computador em que o serviço de réplica está em execução. Não há nenhuma opção para executar o cmdlet **Test-CsReplica** em um servidor remoto.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O comando mostrado no exemplo 1 testa o serviço de réplica do Lync Server 2013 no computador local. Neste exemplo, o parâmetro Verbose é usado para garantir que as informações sobre o teste, incluindo a falha eventual ou o sucesso do teste e a localização do relatório gerado pelo teste – sejam exibidas na tela.

    Test-CsReplica -Verbose

O exemplo 2 é uma variação do comando mostrado no exemplo 1. Nesse caso, o parâmetro do relatório é incluído para especificar o nome e o caminho da pasta para o relatório gerado pelo teste. Se você não especificar um caminho de relatório, o relatório receberá um nome gerado automaticamente semelhante a este:

C:\\Users\\Administrator\\.\\litwareinc\\AppData\\local\\Temp 1 Test-CS-CS-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Inserir o corpo da seção aqui.

VERBOse: Criando novo arquivo de log "\\C\\:\\usuários\\testando\\os arquivos de log temporários locais\\-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".

VERBOse: Criando novo arquivo de log "\\C\\:\\usuários\\testando\\os arquivos de log temporários locais\\-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".

MODO detalhado: o processamento de "Test-CsReplica" foi concluído com êxito.

VERBOse: resultados detalhados podem ser encontrados em "\\C\\:\\usuários\\testando os usuários locais\\de\\teste de CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".

VERBOse: Criando um novo arquivo de log

"C:\\os\\usuários\\testando\\AppData\\\\local\\Temp 2-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. xml ".

VERBOse: Criando um novo arquivo de log

"C:\\os\\usuários\\testando\\AppData\\\\local\\Temp 2-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. html ".

Aviso: falha de Test-CsReplica.

Aviso: os resultados detalhados podem ser encontrados em

"C:\\os\\usuários\\testando\\AppData\\\\local\\Temp 2-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083. html ".

Test-CsReplica: falha na execução do comando: o acesso do registro solicitado não está

autorizados.

Na linha: 1 caractere: 1

\+Test-CsReplica-Verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: (:) \[Test-CsReplica\], segurança

Extremamente

\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. Deploy

atribui. TestReplicaCmdlet

PS C:\\testes\\de usuários\>

PS C:\\usuários\\testando\> Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M

icrosoft.com "

Aviso: falha ao ler o número da porta do registrador para o número da porta de dados totalmente qualificado

FQDN (nome de domínio). Usando o número da porta do registrador padrão. Extremamente

System. InvalidOperationException: nenhum cluster correspondente localizado na topologia.

como

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: não há um usuário de teste atribuído para

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Verifique a configuração do usuário do teste.

Na linha: 1 caractere: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsReplica** pode falhar:

  - Pode haver um problema maior com o agente do Replicator e os serviços de agente de log centralizado

  - As portas necessárias podem não estar abertas no firewall do Windows

  - Os grupos de segurança do Active Directory e do computador local necessários podem não existir

</div>

</div>

<span> </span>

</div>

</div>

</div>

