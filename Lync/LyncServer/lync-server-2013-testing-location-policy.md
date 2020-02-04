---
title: 'Lync Server 2013: testando a política de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a954405cb8dbba842250e0545ac8661d4f3795c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Testando a política de localização no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-05_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsLocationPolicy. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsLocationPolicy verifica se uma política de localização é atribuída a um usuário. A política de localização é usada para aplicar configurações relacionadas à funcionalidade do E9-1-1 e ao local do cliente. A política de localização determina se um usuário está habilitado para E9-1-1 e, se a resposta for "Sim", qual é o comportamento de uma chamada de emergência. Por exemplo, você pode usar a política de localização para definir qual número constitui uma chamada de emergência (911 nos Estados Unidos), se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.

Você pode testar políticas de localização em usuários ou em sub-redes de rede. Se você executar o teste em uma sub-rede (especificando um valor para o parâmetro de sub-rede), o cmdlet tentará resolver a política de localização dessa sub-rede. Se nenhuma política de localização for atribuída à sub-rede, a política de localização para o usuário configurado será recuperada. Se a política de sub-rede for recuperada com êxito, a saída incluirá um valor LocationPolicyTagID que começa com subnet-TagId. Se uma política de localização para a sub-rede não for encontrada, o LocationPolicyTagID começará com o User-TagId.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsLocationPolicy pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server. Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado. Por exemplo:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta ao chamar Test-CsLocationPolicy:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o usuário especificado tiver uma política de local válida, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**

EnhancedEmergencyServicesEnabled: true

LocationPolicyTagID: user-TagId

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Correto

Se não for possível encontrar uma política de local válida para o usuário especificado, o resultado será mostrado como uma falha, e as informações adicionais serão gravadas nas propriedades erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 404, não encontrado

Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,

Motivo = o URI de destino não está habilitado para SIP ou não

Existem.

Microsoft. RTC. Signaling. DiagnosticHeader

A saída anterior informa que o teste falhou porque o usuário especificado não é válido: ou a conta não existe ou o usuário não foi habilitado para o Lync Server. Você pode verificar a validade de uma conta e determinar se essa conta foi habilitada para nm-OCS-14-3º, executando um comando semelhante a este:

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Se Test-CsLocationPolicy falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose estiver incluído, Test-CsLocationPolicy retornará uma conta passo a passo de cada ação que tentou ao verificar a política de localização. Por exemplo, essa saída indica que o Lync Server não pôde fazer logon no usuário de teste, provavelmente porque foi fornecida uma senha inválida:

Enviando solicitação de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Endereço SIP do usuário = sip:kenmyer@litwareinc.com

Porta do registrador = 5061

O tipo de autenticação ' IWA ' é selecionado.

Acesso à inscrição em SIP/ATL-cs-001. litwareinc. com

Atividade ' Register ' concluída em ' 0, 601795 ' segundos.

Uma exceção ' o logon foi negado. Verifique se as credenciais corretas estão sendo usadas e se a conta está ativa. ocorridas durante o fluxo de trabalho.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsLocationPolicy pode falhar:

  - Você especificou uma conta de usuário que não é válida. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

