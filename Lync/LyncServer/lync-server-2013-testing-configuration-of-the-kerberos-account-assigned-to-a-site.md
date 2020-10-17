---
title: Testando a configuração da conta Kerberos atribuída a um site
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08477e9902a1410a98516a79fe5fdd01c5e94214
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504118"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Testando a configuração da conta Kerberos atribuída a um site no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-05_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsKerberosAccountAssignment. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsKerberosAccountAssignment permite que você verifique se uma conta Kerberos está associada a um determinado site, se essa conta está configurada corretamente e se a conta está funcionando conforme o esperado. As contas Kerberos são contas de computador que podem servir como entidade de autenticação para todos os computadores em um site que executa o Internet Information Server (IIS). Como essas contas usam o protocolo de autenticação Kerberos, as contas são conhecidas como contas Kerberos e o novo processo de autenticação é conhecido como autenticação da Web Kerberos. Isso permite que você gerencie todos os servidores IIS usando uma única conta.

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Por padrão, Test-CsKerberosAccountAssignment exibe muito pouco saída na tela. Em vez disso, as informações retornadas pelo cmdlet são gravadas em um arquivo HTML. Por isso, recomendamos que você inclua o parâmetro Verbose e o parâmetro Report sempre que executar Test-CsKerberosAccountAssignment. O parâmetro Verbose fornecerá uma saída mais detalhada na tela enquanto o cmdlet é executado. O parâmetro Report permite que você especifique um caminho de arquivo e um nome de arquivo para o arquivo HTML gerado por Test-CsKerberosAccountAssignment. Se você não incluir o parâmetro Report, o arquivo HTML será automaticamente salvo na pasta usuários e receberá um nome semelhante a este: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.

Você também deve especificar uma identidade de site ao executar Test-CsKerberosAccountAssignment. As contas Kerberos são atribuídas no escopo do site.

O comando a seguir executa Test-CsKerberosAccountAssignment e salva a saída em um arquivo chamado C: \\ Logs \\KerberosTest.html:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

O cmdlet Test-CsKerberosAccountAssignment não retorna uma simples indicação de sucesso ou falha. Em vez disso, você deve exibir o arquivo HTML gerado usando o Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns para que Test-CsKerberosAccountAssignment possa falhar:

  - Você pode ter especificado uma identidade de site incorreta. Para retornar uma lista de identidade de site válida, use este comando:
    
        Get-CsSite | Select-Identity Identity
    
    Uma identidade de site geralmente tem a seguinte aparência:
    
    site: Redmond

  - O site especificado pode não ter uma conta Kerberos atribuída a ele. Você pode determinar se uma conta Kerberos é ou não atribuída a um site executando um comando semelhante a este:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Sua conta Kerberos pode ter uma senha que não é válida. Se você receber a seguinte mensagem de erro no relatório, provavelmente terá que redefinir a senha da conta Kerberos:
    
    InvalidKerberosConfiguration: a configuração Kerberos é inválida.
    
    InvalidKerberosConfiguration: a configuração Kerberos no atl-cs001.litwareinc.com é inválida. A conta atribuída esperada é litwareinc \\ kerberostest. Certifique-se de que a conta não tenha expirado e que a senha configurada na máquina corresponda à senha do Active Directory da conta.
    
    Você pode definir a senha usando o cmdlet [set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

