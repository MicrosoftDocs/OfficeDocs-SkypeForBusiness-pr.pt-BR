---
title: 'Lync Server 2013: testando o Agendador da Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d7dc70bad90dc4e4c94e2db273f44ed20c50ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Testando o Agendador da Web no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsWebScheduler</strong> . Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsWebScheduler** permite que você determine se um usuário específico pode agendar uma reunião usando o Web scheduler. O Web Scheduler permite que os usuários que não estão executando o Outlook agendem reuniões online. Entre outras coisas, esse novo recurso (que incorpora a funcionalidade encontrada na ferramenta do Agendador da Web incluída com o Microsoft Lync Server 2010 Resource Kit) permite que os usuários:

  - Agendar uma nova reunião online.

  - Listar todas as reuniões agendadas por ele ou ela.

  - Exibir/modificar uma reunião existente.

  - Excluir uma reunião existente.

  - Envie um convite por email para os participantes da reunião usando um servidor de email SMTP pré-configurado.

  - Ingressar em uma conferência existente.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O exemplo a seguir verifica o Agendador da Web para o conjunto de atl-cs-001.litwareinc.com. Esse comando funcionará apenas se os usuários de teste estiverem definidos para o pool atl-cs-001.litwareinc.com. Se eles tiverem, o comando determinará se o primeiro usuário de teste pode agendar uma reunião online usando o Web scheduler.

Se os usuários de teste não estiverem definidos, o comando falhará porque não saberá qual usuário deve fazer logon. Se você não definiu usuários de teste para um pool, deve incluir o parâmetro UserSipAddress e as credenciais do usuário que o comando deve usar quando tentar fazer logon.

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

Os comandos mostrados no próximo exemplo testam a capacidade de um usuário específico (\\litwareinc kenmeyer) agendar uma reunião online usando o Web scheduler. Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contém o nome e a senha do usuário Ken Meyer. (Como o nome de logon\\litwareinc kenmeyer está incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige que o administrador digite a senha da conta Ken Meyer.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.

Em seguida, o segundo comando verifica se este usuário pode fazer logon no pool atl-cs-001.litwareinc.com e agendar uma reunião online. Para executar essa tarefa, o cmdlet **Test-CsWebScheduler** é chamado, juntamente com três parâmetros: TargetFqdn (o FQDN do pool de registrador); Usercredential (o objeto do Windows PowerShell que contém as credenciais de usuário de pilar Alverca); e UserSipAddress (o endereço SIP correspondente às credenciais de usuário fornecidas).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o Web Scheduler estiver configurado corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success**:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino: https://atl-cs-001.litwareinc.com.

litwareinc.com:443/Scheduler

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Correto

Se o Web Scheduler não estiver configurado corretamente, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

Aviso: falha ao ler o número da porta do registrador para o número da porta de dados totalmente qualificado

FQDN (nome de domínio). Usando o número da porta do registrador padrão. Extremamente

System. InvalidOperationException: nenhum cluster correspondente localizado na topologia.

como

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:

Resultado: falha

Latência: 00:00:00

Mensagem de erro: nenhum cluster correspondente localizado na topologia.

Correto

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsWebScheduler** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Esse comando falhará se o Web Scheduler estiver configurado incorretamente ou ainda não foi implantado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

