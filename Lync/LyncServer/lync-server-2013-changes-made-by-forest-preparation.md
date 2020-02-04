---
title: 'Lync Server 2013: alterações feitas pela preparação da floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4df16ffb24c4eb4e010e2b57f6af62d3518c05b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Alterações feitas pela preparação da floresta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-30_

Esta seção descreve as configurações globais e os objetos, e o serviço universal e os grupos de administração criados pela etapa de preparação da floresta.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Objetos e configurações globais do Active Directory

Se você armazenar configurações globais no contêiner de configuração (como é o caso de todas as novas implantações do Lync Server 2013), a preparação da floresta usará o contêiner de serviços existentes e adicionará um objeto de **serviço RTC** no objeto de serviços de configuração\\. No objeto de serviço RTC, a preparação da floresta adiciona um objeto de **configurações globais** do tipo MsRTCSIP-GlobalContainer. O objeto de configurações globais armazena todas as configurações que se aplicam à implantação do Lync Server. Se você armazenar configurações globais no contêiner do sistema, a preparação da floresta usará um contêiner da Microsoft no contêiner do sistema do domínio raiz e um objeto\\de serviço RTC sob o objeto do sistema Microsoft.

A preparação da floresta também adiciona um novo objeto **msRTCSIP-Domain** para o domínio raiz no qual o procedimento é executado.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Grupos de administração e serviço universal do Active Directory

A preparação da floresta cria grupos universais baseados no domínio que você especifica e adiciona entradas de controle de acesso (ACEs) a esses grupos. Esta etapa cria os grupos universais nos contêineres de usuários do domínio que você especificar.

Os grupos universais permitem que os administradores acessem e gerenciem serviços e configurações globais. A preparação da floresta adiciona os seguintes tipos de grupos universais:

  - **Grupos administrativos esses**   grupos definem funções de administrador para uma rede do Lync Server.

  - **Grupos de infraestrutura**   esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Lync Server. Elas funcionam como componentes de grupos administrativos. Você não deve modificar esses grupos ou adicionar usuários diretamente a eles.

  - **Grupos de serviços**   esses grupos são contas de serviço que são necessárias para acessar vários serviços do Lync Server.

A tabela a seguir descreve os grupos administrativos.

### <a name="administrative-groups-created-during-forest-preparation"></a>Grupos administrativos criados durante a preparação da floresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo administrativo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Permite que os membros gerenciem as configurações do servidor e do pool, incluindo todas as funções do servidor, configurações globais e usuários.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Permite que os membros gerenciem as configurações do usuário e movam os usuários de um servidor ou pool para outro.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Permite que os membros leiam configurações de servidor, pool e usuário.</p></td>
</tr>
</tbody>
</table>


A tabela a seguir descreve os grupos de infraestrutura.

### <a name="infrastructure-groups-created-during-forest-preparation"></a>Grupos de infraestrutura criados durante a preparação da floresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de infraestrutura</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Concede acesso de gravação a objetos de configuração global do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Concede acesso somente leitura aos objetos de configuração global do Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Concede acesso somente leitura às configurações de usuário do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Concede acesso somente leitura às configurações do Lync Server. Esse grupo não tem acesso às configurações do nível do pool, somente para configurações específicas de um servidor individual.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Concede acesso somente leitura à configuração do Lync Server e é colocado no grupo Administradores local dos aparelhos de ramificação sobreviventes durante a instalação.</p></td>
</tr>
</tbody>
</table>


A tabela a seguir descreve os grupos de serviços.

### <a name="service-groups-created-during-forest-preparation"></a>Grupos de serviço criados durante a preparação da floresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de serviços</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Inclui contas de serviço usadas para executar servidores front-end Server e Standard Edition. Esse grupo permite que os servidores tenham acesso de leitura/gravação para configurações globais do Lync Server e objetos de usuário do Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Inclui contas de serviço usadas para executar servidores de conferência A/V, serviços Web, servidor de mediação, servidor de arquivamento e Monitoring Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Inclui contas de serviço usadas para executar servidores do Lync Server Edge.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Inclui servidores que podem participar da replicação do repositório de gerenciamento central do Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Concede acesso somente leitura às configurações do Lync Server, mas permite a configuração de um servidor de ramificação para a instalação de um servidor de ramificação sobreviventes e a implantação de dispositivos em filiais sobreviventes.</p></td>
</tr>
</tbody>
</table>


A preparação da floresta adiciona grupos de serviços e de administração aos grupos de infraestrutura apropriados, da seguinte maneira:

  - RTCUniversalServerAdmins é adicionado a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

  - RTCUniversalUserAdmins é adicionado como membro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

  - RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins são adicionados como membros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

A preparação da floresta também cria os seguintes grupos de controle de acesso baseado na função (RBAC):

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

Para obter detalhes sobre as funções RBAC e as tarefas permitidas para cada uma, consulte [planejando o controle de acesso baseado em função no Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) na documentação de planejamento.

A preparação da floresta cria ACEs públicas e privadas. Ele cria ACEs privadas no contêiner de configurações globais usado pelo Lync Server. Esse contêiner é usado apenas pelo Lync Server e está localizado no contêiner de configuração ou no contêiner do sistema do domínio raiz, dependendo de onde você armazenou as configurações globais. As ACEs públicas criadas pela preparação da floresta são listadas na tabela a seguir.

### <a name="public-aces-created-by-forest-preparation"></a>ACEs públicas criadas pela preparação da floresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ler contêiner do sistema de domínio raiz (não herdado)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Ler o contêiner DisplaySpecifiers da configuração (não herdado)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>As ACEs que não são herdadas não concedem acesso a objetos filho sob esses contêineres. ACEs que são herdadas conceder acesso a objetos filho sob esses contêineres.



</div>

No contêiner de configuração, no contexto de nomenclatura de configuração, a preparação da floresta executa as seguintes tarefas:

  - Adiciona uma entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para a página de **Propriedades RTC** nos atributos adminContextMenu e adminPropertyPages do especificador de exibição de idioma para usuários, contatos e inetOrgPersons (por exemplo, CN = user-Display, CN = 409, CN = DisplaySpecifiers).

  - Adiciona um objeto **RTCPropertySet** do tipo **ControlAccessRight** em **direitos estendidos** que se aplicam às classes de usuário e de contato.

  - Adiciona um objeto **RTCUserSearchPropertySet** do tipo **ControlAccessRight** em **direitos estendidos** que se aplicam às classes usuário, contato, UO e DomainDNS.

  - Adiciona **msRTCSIP-PrimaryUserAddress** sob o atributo **extraColumns** de cada especificador de exibição de unidade organizacional (ou) de idioma (por exemplo, CN = ORGANIZATIONALUNIT-display, CN = 409, CN = DisplaySpecifiers) e copia os valores do atributo **extraColumns** da exibição padrão (por exemplo, CN = Default-display, CN = 409, CN = DisplaySpecifiers).

  - Adiciona atributos de filtragem **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**e **msRTCSIP-UserEnabled** sob o atributo **attributeDisplayNames** de cada especificador de exibição de idioma para os objetos usuários, contatos e INETORGPERSON (por exemplo, em inglês: CN = usuário-exibição, CN = 409, CN = DisplaySpecifiers).

</div>

</div>

<span> </span>

</div>

</div>

</div>

