---
title: 'Lync Server 2013: testar conferência UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c5daad2d43cf5a7e61dd0e87fac79eb98b9c82e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Testando a conferência do UCWA no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsUcwaConference</strong> . Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsUcwaConference** verifica se um par de usuários de teste pode agendar, participar e, em seguida, conduzir uma conferência online usando a API Web de comunicações unificadas (UCWA). Para fazer isso, o cmdlet usa o serviço de tíquete da Web do Lync Server para autenticar os dois usuários de teste e registrá-los no Lync Server. O cmdlet então inicia uma conferência usando as credenciais do organizador e convida o participante para entrar na reunião. Depois que a reunião é associada, o cmdlet **Test-CsUcwaConference** verifica se os usuários podem fazer coisas como mensagens instantâneas do Exchange e pools de condução e, em seguida, desconecta a conferência e cancela o registro dos dois usuários de teste. A conferência agendada também será excluída quando o teste for concluído.

O cmdlet **Test-CsUcwaConference** também pode ser usado para determinar se os usuários anônimos podem participar de conferências online.

Observe que o cmdlet **Test-CsUcwaConference** não deve ser executado em um pool do Microsoft Lync Server 2010, a menos que o UCWA tenha sido instalado nesse pool. Se o UCWA não tiver sido instalado, a chamada para o cmdlet **Test-CsUcwaConference** falhará.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O comando mostrado no Exemplo 1 verifica se um par de usuários de teste pode participar de uma conferência de UCWA no pool atl-cs-001.litwareinc.com. Observe que esse comando falha se você não predefinir um par de usuários de teste de configuração de monitoramento de integridade para o atl-cs-001.litwareinc.com.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

Os comandos mostrados no exemplo 2 testam a capacidade de um par de usuários\\(litwareinc pilar\\e litwareinc kenmyer) para participar de uma conferência do UCWA. Para fazer isso, o primeiro comando no exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contenha o nome e a senha do usuário pilar Ackerman. (Como o nome de logon,\\litwareinc pilar, foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto de credenciais resultante é armazenado em uma variável chamada $cred 1. O segundo comando fará o mesmo, retornando, desta vez, um objeto de credencial para a conta de Ken Myer.

Com os dois objetos de credencial em mãos, o terceiro comando no exemplo determina se os dois usuários podem participar de uma conferência do UCWA. Para executar essa tarefa, o cmdlet **Test-CsUcwaConference** é chamado, junto com os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); OrganizerSipAddress (o endereço SIP do organizador da reunião); OrganizerCredential (o objeto Windows PowerShell que contém as credenciais desse mesmo usuário); ParticipantSipAddress (o endereço SIP para o outro usuário de teste); e ParticipantCredential (o objeto de interface de linha de comando do Windows PowerShell que contém as credenciais do outro usuário).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se a conferência estiver configurada corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino: https://LyncTest-SE. LyncTest. SelfHost. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Resultado: êxito

Latência: 00:00:14.9862716

Mensagem de erro:

Diagnóstico

Se os usuários especificados não puderem usar conferências, o resultado será mostrado como **falha**, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

Aviso: falha ao ler o número da porta do registrador para o fornecido totalmente qualificado

FQDN (nome de domínio). Usando o número da porta do registrador padrão. Exceções

System. InvalidOperationException: nenhum cluster correspondente encontrado na topologia.

por

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: não há um usuário de teste atribuído para

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Verifique a configuração do usuário de teste.

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

Aqui estão alguns motivos comuns pelos quais **Test-CsUcwaConference** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - A capacidade de realizar uma conferência depende da política de conferência que foi atribuída ao usuário que organizou a conferência (no caso do cmdlet **Test-CsUcwaConference** , que é o "remetente"). Se o organizador não tiver permissão para incluir atividades colaborativas em sua reunião (por exemplo, se a política de conferência tiver a propriedade EnableDataCollaboration definida como false), o cmdlet **Test-CsUcwaConference** falhará.

  - Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não tiver sido implantado.

</div>

<div>

## <a name="see-also"></a>Confira Também


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

