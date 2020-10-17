---
title: 'Lync Server 2013: testar a configuração do nó do Inspetor'
description: 'Lync Server 2013: testar a configuração do nó do observador.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546837"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Testando a configuração do nó do Inspetor no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsWatcherNodeConfiguration</strong> . Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Se estiver usando o Microsoft System Center Operations Manager para monitorar o Lync Server 2013, você terá a opção de configurar "nós do Inspetor": computadores que periodicamente, e automaticamente, executam transações sintéticas para verificar se o Lync Server está funcionando conforme o esperado. Os nós do Inspetor são atribuídos a pools e são gerenciados usando os cmdlets **CsWatcherNodeConfiguration** . Observe que você não precisa instalar nós do observador se estiver usando o System Center Operations Manager. Você ainda pode monitorar o sistema sem usar nós do Inspetor. A única diferença é que todas as transações sintéticas que você deseja executar devem ser chamadas manualmente em vez de invocadas automaticamente pelo Operations Manager.

O cmdlet **Test-CsWatcherNodeConfiguration** permite verificar se um nó do inspetor foi configurado corretamente e é atribuído a um pool válido do Lync Server 2013. Observe que o cmdlet **Test-CsWatcherNodeConfiguration** deve ser executado no próprio nó do Inspetor. O cmdlet não pode ser executado em computadores remotos.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O comando a seguir verifica as definições de configuração para cada nó do inspetor que está sendo usado na organização.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

A saída de exemplo a seguir mostra um sistema com quatro servidores de borda.

Validar o pool de destino atl-cs-001.litwareinc.com em relação à topologia.

Êxito: o pool de destino atl-cs-001.litwareinc.com existe na topologia.

Êxito: o pool de destino atl-cs-001.litwareinc.com tem a função de registrador instalada.

Êxito: versão do pool de destino atl-cs-001.litwareinc.com suportada.

Êxito: o número da porta para o pool de destino 5061 atl-cs-001.litwareinc.com está correto.

A verificação de pools ausentes na configuração do nó do inspetor foi iniciada. Se algum erro for detectado, ele será impresso.

A verificação de pools ausentes na configuração do nó do inspetor está concluída.

A verificação das chaves do registro do nó do observador criadas pela instalação do nó do observador, será iniciada. Se algum erro for detectado, ele será impresso.

A verificação das chaves do registro do nó do observador criadas pela instalação do nó do observador foi concluída. O tipo de autenticação detectado é Negotiate.

Existência validada com êxito da credencial do usuário de teste SIP: user1@ atl-cs-001.litwareinc.com no repositório de gerenciamento de credenciais.

Existência validada com êxito da credencial do usuário de teste SIP: user2@ atl-cs-001.litwareinc.com no repositório de gerenciamento de credenciais.

A verificação de pools ausentes na configuração do nó do inspetor foi iniciada. Se algum erro for detectado, ele será impresso.

Aviso: o pool atl-cs-001.litwareinc.com tem o registrador

função instalada, mas não há usuários de teste configurados para ele.

A verificação de pools ausentes na configuração do nó do inspetor está concluída.

Verificar as chaves do registro do nó do observador criadas pela instalação do nó do observador, é

tiver. Se algum erro for detectado, ele será impresso.

Test-CsWatcherNodeConfiguration: não é possível encontrar a chave do registro de integridade no

\\Comunicação do software da Microsoft \\ em tempo real. Verifique se o nó do Inspetor. msi é

instalado corretamente.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsWatcherNodeConfiguration** pode falhar:

  - O nó do inspetor não está instalado corretamente.

  - Nenhum usuário de teste está configurado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

