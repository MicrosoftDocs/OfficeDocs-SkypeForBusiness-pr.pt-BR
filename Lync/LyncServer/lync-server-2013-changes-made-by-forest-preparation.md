---
title: 'Lync Server 2013: alterações feitas pela preparação da floresta'
description: 'Lync Server 2013: alterações feitas pela preparação da floresta.'
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
ms.openlocfilehash: 1c9bc40539c285e03610b2fc97166842473997fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543647"
---
# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Alterações feitas pela preparação da floresta no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-30_

Esta seção descreve os objetos e as configurações globais, além dos grupos universais de serviço e administração criados pela etapa de preparação de floresta.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Objetos e configurações globais do Active Directory

Se você armazenar as configurações globais no contêiner de configuração (como é o caso de todas as novas implantações do Lync Server 2013), a preparação da floresta usará o contêiner de serviços existente e adicionará um objeto de **serviço RTC** sob o objeto de serviços de configuração \\ . Sob a implantação do Serviço de RTC, a preparação da floresta adiciona um objeto **Configurações Globais** do tipo msRTCSIP-GlobalContainer. O objeto de configurações globais contém todas as configurações que se aplicam à implantação do Lync Server. Se você armazenar as configurações globais no contêiner do sistema, a preparação da floresta usará um contêiner da Microsoft no contêiner do sistema de domínio raiz e um objeto de serviço RTC no objeto do sistema \\ Microsoft.

A preparação de floresta também adiciona um novo objeto **msRTCSIP-Domain** ao domínio raiz no qual o procedimento é executado.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Grupos universais de serviço e administração do Active Directory

A preparação de floresta cria grupos universais com base no domínio especificado e adiciona entradas de controle de acesso (ACEs) para esses grupos. Essa etapa cria os grupos universais nos contêineres Usuário do domínio especificado.

Os grupos universais permitem que os administradores acessem e gerenciem as configurações e serviços globais. A preparação da floresta adiciona os seguintes tipos de grupos universais:

  - **Grupos administrativos**     Esses grupos definem as funções de administrador para uma rede do Lync Server.

  - **Grupos**     de infraestrutura Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Lync Server. Eles funcionam como componentes dos grupos administrativos. Não modifique esses grupos ou adicione usuários diretamente a eles.

  - **Grupos**     de serviço Esses grupos são contas de serviço necessárias para acessar vários serviços do Lync Server.

A tabela seguir descreve os grupos administrativos.

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
<td><p>Permite que os membros gerenciem as configurações de servidor e de pool, incluindo todas as funções de servidor, configurações globais e usuários.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Permite que os membros gerenciem configurações de usuário e movam usuários de um servidor ou pool para outro.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Permite que os membros leiam configurações de servidor, pool e usuário.</p></td>
</tr>
</tbody>
</table>


A tabela seguir descreve os grupos de infraestrutura.

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
<td><p>Concede acesso de gravação aos objetos de configuração global para o Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Concede acesso somente leitura aos objetos de configuração global para o Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Concede acesso somente leitura às configurações de usuário do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Concede acesso somente leitura às configurações do Lync Server. Este grupo não tem acesso às configurações no nível do pool, mas apenas às configurações específicas de um servidor individual.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Concede acesso somente leitura à configuração do Lync Server e é colocado no grupo local de administradores dos aparelhos de filial persistentes durante a instalação.</p></td>
</tr>
</tbody>
</table>


A tabela seguir descreve os grupos de serviço.

### <a name="service-groups-created-during-forest-preparation"></a>Grupos de serviço criados durante a preparação da floresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de serviço</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Inclui contas de serviço usadas para executar servidores front-end Server e Standard Edition. Esse grupo permite que os servidores tenham acesso de leitura/gravação às configurações globais do Lync Server e aos objetos de usuário do Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Inclui contas de serviço usadas para executar servidores de conferência A/V, serviços Web, servidor de mediação, servidor de arquivamento e servidor de monitoramento.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Inclui contas de serviço usadas para executar servidores de borda do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Inclui servidores que podem participar da replicação do repositório de gerenciamento central do Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Concede acesso somente leitura às configurações do Lync Server, mas permite a configuração da instalação de um servidor de filial persistente e implantação de aparelho de filial persistente.</p></td>
</tr>
</tbody>
</table>


Em seguida, a preparação de floresta adiciona os grupos de serviço e administração aos grupos de infraestrutura apropriados, da seguinte maneira:

  - RTCUniversalServerAdmins é adicionado a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

  - RTCUniversalUserAdmins é adicionado como membro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

  - RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins são adicionados como membros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

A preparação da floresta também cria os seguintes grupos RBAC (controle de acesso baseado na função):

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

  - À csresponsegroupmanager

Para obter detalhes sobre as funções RBAC e as tarefas permitidas para cada uma, consulte [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) na documentação de planejamento.

A preparação de floresta cria ACEs particulares e públicas. Ele cria ACEs privadas no contêiner de configurações globais usado pelo Lync Server. Esse contêiner é usado apenas pelo Lync Server e está localizado no contêiner de configuração ou no contêiner de sistema no domínio raiz, dependendo de onde você armazena as configurações globais. As ACEs públicas criadas pela preparação de floresta estão listadas na tabela a seguir.

### <a name="public-aces-created-by-forest-preparation"></a>ACEs públicas criadas pela preparação de floresta

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
<td><p>Ler o contêiner Sistema do domínio raiz (não herdado)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Ler o contêiner DisplaySpecifiers de Configuração (não herdado)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>As ACEs que não são herdadas não concedem acesso a objetos filho sob esses contêineres. As ACEs que são herdadas concedem acesso aos objetos filho desses contêineres.



</div>

No contêiner Configuração, no contexto de nomenclatura de configuração, a preparação de floresta executa as seguintes tarefas:

  - Adiciona uma entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para a página **Propriedade RTC** dos atributos adminContextMenu e adminPropertyPages do especificador de exibição de idioma para usuários, contatos e InetOrgPersons (por exemplo, CN=user-Display,CN=409,CN=DisplaySpecifiers).

  - Adiciona um objeto **RTCPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário e Contato.

  - Adiciona um objeto **RTCUserSearchPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário, Contato, UO e DomainDNS.

  - Adiciona **msRTCSIP-PrimaryUserAddress** sob o atributo **extraColumns** do especificador de exibição da UO (unidade organizacional) de cada idioma (por exemplo, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) e copia os valores do atributo **extraColumns** da exibição padrão (por exemplo, CN=default-Display, CN=409,CN=DisplaySpecifiers).

  - Adiciona os atributos de filtragem **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** e **msRTCSIP-UserEnabled** sob o atributo **attributeDisplayNames** do especificador de exibição de cada idioma para os objetos Usuários, Contatos e InetOrgPerson (por exemplo, em inglês: CN=user-Display,CN=409,CN=DisplaySpecifiers).

</div>

</div>

<span> </span>

</div>

</div>

</div>

