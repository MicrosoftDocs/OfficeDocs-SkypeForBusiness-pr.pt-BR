---
title: 'Lync Server 2013: planejamento para controle de acesso baseado em função'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb7a359620c7e93565c0d4ef49c813ff0966989c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Planejando o controle de acesso baseado em função no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-01-27_

Para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança, o Lync Server 2013 oferece controle de acesso baseado em função (RBAC). Com o RBAC, o privilégio administrativo é concedido pela atribuição de usuários a funções administrativas. O Lync Server 2013 inclui um conjunto avançado de funções administrativas internas e também permite que você crie novas funções e especifique uma lista personalizada de cmdlets para cada nova função. Você pode também adicionar scripts de cmdlets às tarefas permitidas para ambas as funções personalizadas e predefinidas do RBAC.

<div>

## <a name="better-server-security-and-centralization"></a>Melhor segurança e centralização do servidor

Com o RBAC, o acesso e a autorização são baseados precisamente na função do Lync Server do usuário. Isso permite uso adequado da prática de segurança de "privilégio mínimo", concedendo a administradores e usuários somente os direitos necessários para seus trabalhos.

<div>


> [!IMPORTANT]  
> As restrições RBAC funcionam somente nos administradores que trabalham remotamente, usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server. Um usuário em um servidor executando o Lync Server não é restrito pelo RBAC. Portanto, a segurança física do Lync Server é importante para preservar as restrições de RBAC.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Funções e escopo

No RBAC, uma *função* é habilitada para usar uma lista de cmdlets, projetadas para ser útil para um determinado tipo de administrador ou técnico. Um *escopo* é o conjunto de objetos que os cmdlets definidos em uma função podem operar. Os objetos que o escopo afeta podem ser contas de usuário (agrupadas por unidade organizacional) ou servidores (agrupados por site).

A tabela a seguir lista as funções predefinidas no Lync Server e fornece uma visão geral dos tipos de tarefas que cada uma pode fazer. A quarta coluna mostra a função de servidor do Microsoft Exchange semelhante para cada função de servidor do Lync, se houver uma.

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
<th>Role</th>
<th>Tarefas permitidas</th>
<th>Grupo subjacente do Diretório Ativo</th>
<th>Equivalente do Exchange</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>Pode executar todas as tarefas administrativas e modificar todas as configurações, incluindo a criação de funções e a atribuição de usuários a funções. Pode expandir uma implantação adicionando novos sites, pools e serviços.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Gerenciamento de Organização</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Pode habilitar e desabilitar usuários para o Lync Server, mover usuários e atribuir políticas existentes aos usuários. Não é possível modificar as políticas.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Destinatários de Email</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Pode criar, configurar e gerenciar políticas e configurações relacionadas à voz.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Pode gerenciar, monitorar e solucionar problemas de servidores e serviços. Pode impedir novas conexões com servidores, parar e iniciar serviços e aplicar atualizações de software. Não é possível fazer alterações com impacto de configuração global.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Gerenciamento de Servidor</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Pode exibir a implantação, incluindo informações de usuário e servidor, para monitorar a integridade da implantação.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Gerenciamento da Organização Somente para Exibição</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Pode exibir a implantação, incluindo propriedades e políticas do usuário. Pode executar tarefas específicas de solução de problemas. Não é possível alterar propriedades ou políticas do usuário, configuração do servidor ou serviços.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Comunique</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Pode modificar a configuração e as políticas de arquivamento.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Gerenciamento de Retenção, Bloqueio Legal</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Pode gerenciar a configuração do aplicativo Grupo de Resposta em um site.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Nível mais baixo de direitos de gerenciamento de E9-1-1 (9-1-1 Avançado), incluindo a criação de locais e identificadores de rede E9-1-1 e associando uns com os outros. Esta função é sempre atribuída com um escopo global.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>À csresponsegroupmanager</p></td>
<td><p>Pode gerenciar grupos de resposta específicos.</p></td>
<td><p>À csresponsegroupmanager</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Pode gerenciar o recurso de Bate-papo Persistente e salas de Bate-papo Persistente específicas.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>Não aplicável</p></td>
</tr>
</tbody>
</table>


Todas as funções predefinidas fornecidas no Lync Server têm um escopo global. Para seguir ao menos as práticas de privilégio, você não deve atribuir usuários a funções com escopo global se eles forem administrar apenas um conjunto limitado de servidores ou usuários. Para tal, você pode criar funções que são baseadas em uma função existente, mas com escopo mais limitado.

<div>

## <a name="creating-a-scoped-role"></a>Criando uma Função com escopo

Ao criar uma função com escopo limitado (função com escopo), você especifica o escopo junto com a função existente a qual é baseada e o grupo de Diretório Ativo a ser atribuído à função. O grupo do Diretório Ativo especificado já deve ter sido criado. O cmdlet a seguir é um exemplo de uma criação de função a qual possui os privilégios de uma das funções administrativas, mas com escopo limitado. Ele cria uma nova função chamada `Site01 Server Administrators`. A função possui as capacidades da função CsServerAdministrator predefinida, mas apenas servidores localizados no local do Site01. Para que este cmdlet funcione, o site do Site01 já deve estar definido, e um grupo de segurança `Site01 Server Administrators` universal chamado já deve existir.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Após a execução do cmdlet, todos os usuários que são membros `Site01 Server Administrators` do grupo terão privilégios de administrador do servidor para os servidores no Site01. Além disso, qualquer usuário que posteriormente adicionado a esse grupo de segurança universal também obterá os privilégios dessa função. Observe que a função em si e o grupo de segurança universal ao qual é atribuído são chamados `Site01 Server Administrators`.

O exemplo a seguir limita o escopo de usuário, em vez do escopo do servidor. Ele cria uma `Sales Users Administrator` função para administrar as contas de usuário na unidade organizacional Sales. O grupo de segurança universal do SalesUsersAdministrator já deve ser criado para que esse cmdlet funcione.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Criando uma nova função

Para criar uma função que possui acesso a um conjunto de cmdlets que não estão em uma das funções predefinidas ou para um conjunto de scripts ou módulos, você pode começar utilizando uma das funções predefinidas como modelo. Observe que os scripts e módulos com a função que devem estar aptos a ser executados devem ser armazenados nos seguintes locais:

  - O caminho do módulo do Lync, que é por padrão\\C:\\arquivos de\\programa arquivos comuns do\\Microsoft\\Lync Server 2013 Lync

  - O caminho do script de usuário, que é por padrão\\C:\\arquivos de\\programas comuns Microsoft Lync\\Server 2013 AdminScripts

Para criar uma nova função, utilize o cmdlet **New-CsAdminRole**. Antes de executar o **New-CsAdminRole**, você deve primeiro criar o grupo de segurança universal subjacente que será associado a essa função.

Os seguintes cmdlets servem como um exemplo de criação de nova função. Eles criam um novo tipo de função `MyHelpDeskScriptRole`chamado. A nova função possui as capacidades da função CsHelpDesk predefinida e pode, adicionalmente, executar funções em um script chamado “testscript”.

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Para que este cmdlet funcione, você deve ter criado primeiro o grupo de segurança universal MyHelpDeskScriptRole.

Depois que esse cmdlet é executado, você pode atribuir usuários diretamente a essa função (neste caso, eles possuem escopo global) ou criar uma função com escopo com base nessa função, como explicado em Criando uma função com escopo, anteriormente neste documento.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Atribuindo funções a usuários

Cada função de servidor do Lync é associada a um grupo de segurança universal subjacente do Active Directory. Qualquer usuário adicionado ao grupo subjacente recebem as capacidades de tal função.

Os exemplos nas seções anteriores criaram uma nova função e atribuiram um grupo de segurança universal existente à nova função. Para atribuir uma função existente a um ou mais usuários, adicione tais usuários ao grupo associado com tal função. Você pode adicionar usuários individuais e grupos de segurança universais a esses grupos.

Por exemplo, a função **CsAdministrator** é automaticamente concedida ao grupo de segurança universal **Administradores de CS** no Active Directory. Esse grupo de segurança universal é criado no Active Directory quando você implanta o Lync Server. Para fornecer esse privilégio a um usuário ou grupo, você pode simplesmente adicioná-los ao grupo **Administradores CS**.

Um usuário pode receber várias funções do RBAC ao ser adicionado aos grupos subjacentes do Active Directory que correspondem a cada função.

Observe que quando você cria uma função, os usuários que posteriormente são adicionados ao grupo subjacente do Active Directory ganham os recursos dessa função.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Modificando as capacidades de uma função

Você pode modificar a lista de cmdlets e scripts que uma função pode executar. Você pode modificar tanto os cmdlets quanto scripts que as funções personalizadas podem executar, mas pode apenas modificar os scripts para funções predefinidas. Cada cmdlet que você digita pode adicionar, remover ou substituir cmdlets ou scripts.

Para modificar uma função, utilize o cmdlet **Set-CsAdminRole**. O cmdlet a seguir remove um script da função.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Planejando o RBAC

Para cada pessoa que deverá receber qualquer tipo de direitos administrativos para sua implantação do Lync Server, considere exatamente quais tarefas precisam ser executadas e, em seguida, atribua-as às funções com o menor privilégio e escopo necessários para o trabalho. Se necessário, você pode usar o cmdlet **Set-CsAdminRole** para criar uma nova função com com apenas os cmdlets necessários para as tarefas dessa pessoa.

Os usuários que têm a função CsAdministrator podem criar todos os tipos de funções, incluindo funções baseadas no CsAdministrator e atribuir usuários a elas. A melhor prática é atribuir a função CsAdministrator a um conjunto muito pequeno de usuários confiáveis.

</div>

</div>

<span> </span>

</div>

</div>

</div>

