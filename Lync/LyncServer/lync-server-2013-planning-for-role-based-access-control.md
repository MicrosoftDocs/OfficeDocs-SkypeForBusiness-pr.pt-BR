---
title: 'Lync Server 2013: Planejamento de controle de acesso baseado em função'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Planejamento de controle de acesso baseado em função no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-01-27_

Para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança, o Lync Server 2013 oferece controle de acesso baseado em função (RBAC). Com o RBAC, o privilégio administrativo é concedido por meio da atribuição de usuários a funções administrativas. O Lync Server 2013 inclui um conjunto rico de funções administrativas internas e também permite que você crie novas funções e especifique uma lista personalizada de cmdlets para cada nova função. Você também pode adicionar scripts de cmdlets às tarefas permitidas de funções RBAC predefinidas e personalizadas.

<div>

## <a name="better-server-security-and-centralization"></a>Melhor segurança e centralização do servidor

Com o RBAC, o acesso e a autorização são baseados precisamente na função do Lync Server de um usuário. Isso permite o uso da prática de segurança de "privilégio mínimo", concedendo aos administradores e usuários somente os direitos necessários para o trabalho.

<div>


> [!IMPORTANT]  
> As restrições RBAC funcionam apenas em administradores que trabalham remotamente, usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server. Um usuário em um servidor que executa o Lync Server não é restrito pelo RBAC. Portanto, a segurança física do Lync Server é importante para preservar as restrições de RBAC.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Funções e escopo

No RBAC, uma *função* é habilitada para usar uma lista de cmdlets, projetada para ser útil para um determinado tipo de administrador ou técnico. Um *escopo* é o conjunto de objetos que os cmdlets definidos em uma função podem operar. Os objetos que afetam o escopo podem ser contas de usuário (agrupadas por unidade organizacional) ou servidores (agrupados por site).

A tabela a seguir lista as funções predefinidas no Lync Server e fornece uma visão geral dos tipos de tarefas que cada uma pode fazer. A quarta coluna mostra a função do Microsoft Exchange Server semelhante para cada função do Lync Server, se houver uma.

### <a name="predefined-administrative-roles"></a>Funções administrativas predefinidas

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função</th>
<th>Tarefas permitidas</th>
<th>Grupo subjacente do Active Directory</th>
<th>Equivalente do Exchange</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>Pode executar todas as tarefas administrativas e modificar todas as configurações, incluindo a criação de funções e a atribuição de usuários a funções. Pode expandir uma implantação adicionando novos sites, pools e serviços.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Gerenciamento de organização</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Pode habilitar e desabilitar usuários do Lync Server, mover usuários e atribuir políticas existentes para os usuários. Não é possível modificar políticas.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Destinatários do email</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Pode criar, configurar e gerenciar configurações e políticas relacionadas à voz.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Pode gerenciar, monitorar e solucionar problemas de servidores e serviços. Pode impedir novas conexões com os servidores, interromper e iniciar serviços e aplicar atualizações de software. Não é possível fazer alterações com o impacto de configuração global.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Gerenciamento de servidor</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Pode exibir a implantação, incluindo informações de usuário e do servidor, para monitorar a integridade da implantação.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Gerenciamento de organização somente para exibição</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Pode exibir a implantação, incluindo propriedades e políticas do usuário. Pode executar tarefas específicas de solução de problemas. Não é possível alterar propriedades ou políticas do usuário, configuração do servidor ou serviços.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Assistência técnica</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Pode modificar a configuração e as políticas de arquivamento.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Gerenciamento de retenção, controle legal</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Pode gerenciar a configuração do aplicativo de grupo de resposta em um site.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Nível mais baixo de direitos para gerenciamento aprimorado de 9-1-1 (E9-1-1), incluindo a criação de locais E9-1-1 e identificadores de rede e associação entre eles. Esta função é sempre atribuída com um escopo global.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>Pode gerenciar grupos de resposta específicos.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Pode gerenciar o recurso de chat persistente e salas de chat persistentes específicas.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>Não aplicável</p></td>
</tr>
</tbody>
</table>


Todas as funções predefinidas fornecidas no Lync Server têm um escopo global. Para acompanhar as práticas de privilégio mínimo, você não deve atribuir usuários às funções com escopo global se eles vão administrar apenas um conjunto limitado de servidores ou usuários. Para fazer isso, você pode criar funções com base em uma função existente, mas com um escopo mais limitado.

<div>

## <a name="creating-a-scoped-role"></a>Criando uma função com escopo

Quando você cria uma função com escopo limitado (uma função com escopo), especifica o escopo, juntamente com a função existente na qual ele é baseado e o grupo do Active Directory ao qual a função deve ser atribuída. O grupo do Active Directory que você especificar já deve ter sido criado. O cmdlet a seguir é um exemplo de criação de uma função que tem os privilégios de uma das funções administrativas predefinidas, mas com escopo limitado. Ele cria uma nova função chamada `Site01 Server Administrators`. A função tem as habilidades da função CsServerAdministrator predefinida, mas somente para os servidores localizados no site do Site01. Para que esse cmdlet funcione, o site do Site01 já deve estar definido, e um grupo de segurança `Site01 Server Administrators` universal chamado já deve existir.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Após a execução do cmdlet, todos os usuários que são membros `Site01 Server Administrators` do grupo terão privilégios de administrador do servidor para os servidores no Site01. Além disso, todos os usuários adicionados posteriormente a esse grupo de segurança universal também obterão os privilégios dessa função. Observe que a função em si e o grupo de segurança universal ao qual ele está atribuído são `Site01 Server Administrators`chamados.

O exemplo a seguir limita o escopo do usuário em vez do escopo do servidor. Ele cria uma `Sales Users Administrator` função para administrar as contas de usuário na unidade organizacional Sales. O grupo de segurança universal SalesUsersAdministrator deve já ter sido criado para que esse cmdlet funcione.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Criando uma nova função

Para criar uma função que tenha acesso a um conjunto de cmdlets que não estão em uma das funções predefinidas ou a um conjunto de scripts ou módulos, comece novamente usando uma das funções predefinidas como um modelo. Observe que os scripts e os módulos que as funções devem ser capazes de executar devem estar armazenados nos seguintes locais:

  - O caminho do módulo do Lync, que é por padrão\\C:\\arquivos de\\programas arquivos comuns do\\Microsoft\\Lync Server 2013 Lync

  - O caminho do script de usuário, que, por padrão\\, C\\: arquivos\\de programas comuns Microsoft\\Lync Server 2013 AdminScripts

Para fazer uma nova função, use o cmdlet **New-CsAdminRole** . Antes de executar **New-CsAdminRole**, primeiro você deve criar o grupo de segurança universal subjacente que será associado a essa função.

Os cmdlets a seguir servem como um exemplo de criação de uma nova função. Eles criam um novo tipo de função `MyHelpDeskScriptRole`chamado. A nova função tem as habilidades da função CsHelpDesk predefinida e, além disso, pode executar as funções em um script chamado "TestScript".

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Para que esse cmdlet funcione, primeiro você deve ter criado o grupo de segurança universal MyHelpDeskScriptRole.

Depois que esse cmdlet é executado, você pode atribuir usuários diretamente a essa função (nesse caso, eles têm escopo global) ou criar uma função de escopo com base nessa função, conforme explicado em criando uma função de escopo, anteriormente neste documento.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Atribuindo funções a usuários

Cada função do Lync Server está associada a um grupo de segurança universal subjacente do Active Directory. Qualquer usuário que você adicionar ao grupo subjacente terá as habilidades dessa função.

Os exemplos nas seções anteriores criaram uma nova função e atribuí um grupo de segurança universal existente para a nova função. Para atribuir uma função existente a um ou mais usuários, adicione esses usuários ao grupo associado à função. Você pode adicionar usuários individuais e grupos de segurança universais a esses grupos.

Por exemplo, a função **CsAdministrator** é automaticamente concedida ao grupo de segurança universal **Administradores do CS** no Active Directory. Este grupo de segurança universal é criado no Active Directory quando você implanta o Lync Server. Para conceder esse privilégio a um usuário ou grupo, basta adicioná-lo ao grupo de **Administradores do CS** .

Um usuário pode receber várias funções RBAC ao ser adicionado aos grupos subjacentes do Active Directory que correspondem a cada função.

Observe que, quando você cria uma função, os usuários adicionados posteriormente ao grupo subjacente do Active Directory ganham as habilidades dessa função.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Modificando as habilidades de uma função

Você pode modificar a lista de cmdlets e scripts que uma função pode executar. Você pode modificar os cmdlets e scripts que as funções personalizadas podem executar, mas você pode modificar somente os scripts para funções predefinidas. Cada cmdlet digitado pode adicionar, remover ou substituir cmdlets ou scripts.

Para modificar uma função, use o cmdlet **set-CsAdminRole** . O cmdlet a seguir remove um script da função.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Planejando para RBAC

Para cada pessoa que deve receber qualquer tipo de direitos administrativos para a implantação do Lync Server, considere exatamente quais tarefas precisam executar e, em seguida, atribua-as às funções com o menor privilégio e escopo necessários para o trabalho. Se necessário, você pode usar o cmdlet **set-CsAdminRole** para criar uma nova função apenas com os cmdlets necessários para as tarefas desta pessoa.

Os usuários que têm a função CsAdministrator podem criar todos os tipos de funções, incluindo as funções baseadas no CsAdministrator, e atribuir usuários a elas. A prática recomendada é atribuir a função CsAdministrator a um conjunto muito pequeno de usuários confiáveis.

</div>

</div>

<span> </span>

</div>

</div>

</div>

