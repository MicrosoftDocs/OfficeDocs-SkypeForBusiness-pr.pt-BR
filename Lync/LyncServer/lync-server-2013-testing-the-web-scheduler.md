---
title: 'Lync Server 2013: testar o Agendador da Web'
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
ms.openlocfilehash: 83f9eb59a14fc0ede5cc5d61f0c9f8dff0e1e445
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Testando o Agendador da Web no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-11-03_


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
<td><p>Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsWebScheduler</strong> . Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsWebScheduler** permite determinar se um usuário específico pode agendar uma reunião usando o Agendador da Web. O Agendador da Web permite que usuários que não estejam executando o Outlook agendem reuniões online. Entre outras coisas, esse novo recurso (que incorpora a funcionalidade encontrada na ferramenta Agendador da Web incluída com o Microsoft Lync Server 2010 Resource Kit) permite aos usuários:

  - Programar uma nova reunião online.

  - Lista todas as reuniões que programou.

  - Exibir/modificar uma reunião existente.

  - Exclui uma reunião existente.

  - Envia um convite de email para participantes da reunião usando um servidor de email SMTP pré-configurado.

  - Participar de uma conferência existente.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O exemplo a seguir verifica o Agendador da Web para o pool atl-cs-001.litwareinc.com. Este comando só funcionará se os usuários de teste estiverem definidos para o pool atl-cs-001.litwareinc.com. Se houver, o comando determinará se o primeiro usuário de teste pode agendar uma reunião online usando o Agendador da Web.

Se os usuários de teste não estiverem definidos, o comando falhará porque não saberá qual usuário fará logon como. Se você não definiu os usuários de teste para um pool, deverá incluir o parâmetro UserSipAddress e as credenciais do usuário que o comando deve usar ao tentar fazer logon.

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

Os comandos mostrados no exemplo a seguir testam a capacidade de um usuário específico\\(litwareinc kenmeyer) para agendar uma reunião online usando o Agendador da Web. Para fazer isso, o primeiro comando no exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contenha o nome e a senha do usuário Ken Araújo. (Como o nome de logon\\litwareinc kenmeyer é incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell requer apenas que o administrador insira a senha da conta Ken Araújo.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.

Em seguida, o segundo comando verifica se esse usuário pode fazer logon no pool atl-cs-001.litwareinc.com e agendar uma reunião online. Para executar essa tarefa, o cmdlet **Test-CsWebScheduler** é chamado, juntamente com três parâmetros: TargetFqdn (o FQDN do pool de registrador); Usercredential (o objeto Windows PowerShell que contém as credenciais de usuário de pilar Ackerman); e UserSipAddress (o endereço SIP que corresponde às credenciais de usuário fornecidas).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o Agendador da Web estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success**:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino: https://atl-cs-001.litwareinc.com.

litwareinc.com:443/Scheduler

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Diagnóstico

Se o Agendador da Web não estiver configurado corretamente, o resultado será mostrado como **falha**, e as informações adicionais serão registradas nas propriedades de erro e diagnóstico:

Aviso: falha ao ler o número da porta do registrador para o fornecido totalmente qualificado

FQDN (nome de domínio). Usando o número da porta do registrador padrão. Exceções

System. InvalidOperationException: nenhum cluster correspondente encontrado na topologia.

por

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:

Resultado: falha

Latência: 00:00:00

Mensagem de erro: nenhum cluster correspondente encontrado na topologia.

Diagnóstico

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsWebScheduler** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Esse comando falhará se o Agendador da Web estiver configurado incorretamente ou ainda não tiver sido implantado.

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

