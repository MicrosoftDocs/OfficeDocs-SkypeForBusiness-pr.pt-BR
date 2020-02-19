---
title: 'Lync Server 2013: testar a ativação do serviço e permissões de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38bc988ec1fdfeb0c4fd5714f31342902fe45821
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Testando a ativação de serviços e permissões de grupo no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsTopology. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsTopology permite verificar se o Lync Server 2013 está funcionando corretamente em um escopo global. Por padrão, o cmdlet verifica toda a infraestrutura do Lync Server, verificando se os serviços necessários estão em execução e se as permissões apropriadas estão definidas para esses serviços e para os grupos de segurança universal criados quando você instala o Lync Server .

Além de verificar a validade da instalação do Lync Server, o Test-CsTopology também permite verificar a validade de um serviço específico. Por exemplo, este comando verifica o estado do Servidor de Conferência A/V no pool atl-cs-001.litwareinc.com:

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Por padrão, Test-CsTopology exibe uma saída muito pequena na tela. Em vez disso, as informações retornadas pelo cmdlet são gravadas em um arquivo HTML. O parâmetro Report permite que você especifique um caminho de arquivo e um nome de arquivo para o arquivo HTML gerado por Test-CsTopology. Se você não incluir o parâmetro Report, o arquivo HTML será automaticamente salvo na pasta usuários e receberá um nome semelhante a este: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

O seguinte comando de exemplo executa Test-CsTopology e salva a saída em um arquivo chamado C:\\logs\\ComputerTest. html:

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Ao contrário da maioria dos cmdlets de teste, Test-CsTopology relata êxito ou falha. Em parte, isso ocorre devido ao grande número de verificações de verificação que o cmdlet deve fazer sempre que for executado. Em vez disso, os dados são salvos em um relatório HTML que pode ser visualizado usando o Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsTopology pode falhar:

  - A replicação pode não estar atualizada no computador de teste. Você pode verificar o status de replicação atual de um computador executando o cmdlet Get-CsManagementStoreReplicationStatus:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Se o status de replicação não estiver atualizado, você poderá forçar a replicação a ocorrer manualmente usando um comando semelhante a este:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - A topologia pode ter que ser ativada. Se você alterar a topologia do Lync Server (alterações que possam afetar o computador local), deverá habilitar a nova topologia. Você pode habilitar a topologia a qualquer momento executando este comando:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

