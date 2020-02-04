---
title: 'Lync Server 2013: testando a configuração do servidor LIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3c99e9f10f98d93af73869d166c33a27e9ce18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Testando a configuração do servidor LIS no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsLisConfiguration. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsLisConfiguration verifica sua capacidade de entrar em contato com o serviço Web LIS. Se o serviço Web puder ser contatado, o teste será considerado um sucesso, independentemente de ser possível encontrar locais específicos.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsLisConfguration pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server. Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado. Por exemplo:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta ao chamar Test-CsLisConfiguration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o LIS estiver configurado corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**

TargetUri :https://atl-cs-001.litwareinc.com:443/locationinformation/

liservice. svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.1616913

Erros

Correto

Se o usuário especificado não puder fazer logon ou logoff, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetUri :

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 11004, o nome solicitado é válido, mas não tem dados do pedido

tipo encontrado

Correto

Test-CsLisConfiguration: nenhum cluster correspondente localizado na topologia.

Por exemplo, a saída anterior inclui a observação "nenhum cluster correspondente encontrado na topologia". Isso geralmente indica um problema com o servidor de borda: o LIS usando o servidor de borda para se conectar ao provedor de serviços e validar os endereços.

Se Test-CsLisConfiguration falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose estiver incluído, Test-CsLisConfiguration retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server. Por exemplo:

Serviço de informações de localização de chamadas.

Caminho do serviço =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

ChassisId =

Portid =

PortIdSubType = tipo indefinido

Mac

Falha na solicitação de serviço Web de informações de localização de uma exceção com um código de resposta Item400. ' ocorrido durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTrsnactions. workflows. STLisConfigurationWorkflow.

Se você examinar a saída anterior atentamente, verá que o cmdlet falhou após a tentativa de chamar o serviço de informações de localização. Um dos parâmetros que foram usados nesta chamada foi o seguinte:

BssId = 5

Esse não é um valor válido para o BssID (Basic Service Set Identifier). Em vez disso, um BssID deve ser semelhante ao seguinte:

12-34-56-78-90-AB

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsLisConfiguration pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Conforme mostrado no exemplo anterior, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.

</div>

</div>

<span> </span>

</div>

</div>

</div>

