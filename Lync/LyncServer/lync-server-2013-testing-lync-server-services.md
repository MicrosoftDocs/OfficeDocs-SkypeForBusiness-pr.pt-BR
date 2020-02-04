---
title: 'Lync Server 2013: testando serviços do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdafd84f5a8edd21d6e62433d028ed735e37a37d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>Testando serviços do Lync Server no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsComputer. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Test-CsComputer verifica o status de todos os serviços do Lync Server 2013 que estão em execução no computador local. (Test-CsComputer só pode ser executado localmente; ele não pode ser executado em uma instância remota do Windows PowerShell.) O cmdlet também verifica se as portas de firewall adequadas estão abertas no computador e determina se os grupos do Active Directory que foram criados quando você instalou o Lync Server 2013 foram adicionados aos grupos locais correspondentes. Por exemplo, Test-CsComputer verificará se a RTCUniversalUserAdmins do grupo do Active Directory foi adicionada ao grupo Administradores.

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsComputer só pode ser executado no computador local, e você não pode chamar Test-CsComputer de uma instância remota do Windows PowerShell. Por padrão, Test-CsComputer exibe uma saída na tela muito pouco, em vez disso, as informações retornadas pelo cmdlet são gravadas em um arquivo HTML. Por isso, recomendamos que você inclua o parâmetro Verbose e o parâmetro Report a qualquer momento que executar Test-CsComputer. O parâmetro Verbose fornecerá uma saída levemente mais detalhada na tela enquanto o cmdlet é executado. O parâmetro Report permite que você especifique um caminho de arquivo e um nome de arquivo para o arquivo HTML gerado por Test-CsComputer. Se você não incluir o parâmetro do relatório, o arquivo HTML será salvo automaticamente na pasta usuários e receberá um nome semelhante a este: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

O comando de exemplo a seguir executa Test-CsComputer e salva a saída em um arquivo chamado C:\\logs\\ComputerTest. html:

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Devido ao número de verificações de verificação que ele executa, Test-CsComputer não relata um simples **Sim, o teste foi bem-sucedido** ou **não, o teste falhou**. Em vez disso, você precisa exibir o arquivo HTML gerado usando o Internet Explorer para determinar o êxito ou falha de cada teste.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsComputer pode falhar:

  - O computador de teste pode não estar habilitado para uso com o Lync Server. Isso pode ocorrer se os serviços do Lync Server ou as funções de servidor no computador tiverem sido alteradas e o cmdlet Enable-CsComputer não for executado. Para solucionar esse problema, execute o seguinte comando:
    
        Enable-CsComputer

  - A replicação pode não estar atualizada no computador de teste. Você pode verificar o status de replicação atual de um computador executando o cmdlet Get-CsManagementStoreReplicationStatus:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Se o status de replicação não for atualizado, você pode forçar manualmente a ocorrência da replicação usando um comando semelhante a este:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - A topologia pode ter que ser ativada. Se você alterar a topologia do Lync Server (alterações que podem afetar o computador local), será necessário habilitar a nova topologia. Você pode habilitar a topologia a qualquer momento executando este comando:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

