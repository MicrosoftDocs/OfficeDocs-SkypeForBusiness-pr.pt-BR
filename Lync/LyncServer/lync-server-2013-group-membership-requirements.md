---
title: 'Lync Server 2013: Requisitos de associação ao grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ad8c7f6eab93f3bdcd7b73d4ae05bd3b2e25ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Requisitos de associação ao grupo para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

A tabela a seguir resume o grupo ou grupos aos quais uma pessoa deve pertencer para instalar, gerenciar e solucionar problemas com êxito no Lync Server 2013.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Executável do Lync Server 2013</th>
<th>Associação de grupo necessária</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup. exe</strong> – executável que inicia a instalação das ferramentas administrativas do Lync Server 2013.</p></td>
<td><p>Membro do grupo Administradores local no computador do qual o executável é executado. Membro do grupo usuários do domínio para ler informações nos serviços de domínio Active Directory. Este nível de permissão é necessário porque a instalação automática dos pacotes MSI necessários no computador local requer privilégios que permitem a leitura e gravação em recursos de computador local protegidos, como pastas de arquivos de programas e protegido registro como o hive do computador local.</p>
<div>

> [!TIP]  
> Você também pode delegar permissões de configuração para usuários ou grupos aos quais você não deseja conceder associação no grupo Domain admins. Para obter detalhes, consulte <A href="lync-server-2013-granting-setup-permissions.md">concedendo permissões de configuração no Lync Server 2013</A> na documentação de implantação.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy. exe</strong> – chamado pelo Setup. exe, Deploy. exe é responsável pela implantação dos componentes do software para as funções do servidor.</p></td>
<td><p>Membro do grupo Administradores local no computador do qual o executável é executado. Membro do grupo usuários do domínio para ler informações no AD DS. Este nível de permissão é necessário porque a instalação automática dos pacotes MSI necessários no computador local requer privilégios que permitem a leitura e gravação em recursos de computador local protegidos, como pastas de arquivos de programas e protegido registro como o hive do computador local. A associação no grupo RtcUniversalReadOnlyAdmins é necessária para ler o repositório de gerenciamento central.</p>
<div>

> [!NOTE]  
> Se você estiver executando o sistema operacional Windows Vista ou o sistema operacional Windows 7, será solicitado que o controle de conta de usuário (UAC) prossiga com a instalação. Se você estiver conectado com uma conta de usuário padrão, precisará de alguém que seja membro do grupo local de administradores para fornecer as credenciais quando for solicitada uma conta com permissões para instalar o software.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper. exe</strong> – chamado pelo Setup. exe, bootstrapper. exe é responsável por implantação e configuração de funções de servidor.</p></td>
<td><p>Membro do grupo Administradores local no computador do qual o executável é executado. Membro do grupo RTCUniversalServerAdmins para executar bootstrapper. exe. Membro do grupo usuários do domínio para ler informações no AD DS. Este nível de permissão é necessário porque a instalação automática dos pacotes MSI necessários no computador local requer privilégios que permitem a leitura e gravação em recursos de computador local protegidos, como pastas de arquivos de programas e protegido registro como o hive do computador local.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> – interface do usuário orientada por assistente para criar, exibir, ajustar e validar topologias do Lync Server 2013.</p></td>
<td><p>Membro do grupo Administradores local no computador do qual o executável é executado para exibir a topologia. Membro do grupo RTCUniversalServerAdmins para alterar as definições de configuração. Membro do grupo RTCUniversalServerAdmins e do grupo Administradores do domínio ou membro do grupo RTCUniversalServerAdmins (apenas se o grupo tiver recebido permissões de configuração do representante), para publicar a topologia. Para obter detalhes sobre como delegar permissões de configuração para permitir que os membros do grupo RTCUniversalServerAdmins publiquem a topologia sem serem membros do grupo Domain admins, consulte <a href="lync-server-2013-granting-setup-permissions.md">concedendo permissões de instalação no Lync Server 2013</a> na documentação de implantação.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> – interface de usuário gráfica baseada na Web para o gerenciamento do Lync Server 2013.</p></td>
<td><p>Membro do grupo CsAdministrator ou membro de outra função de controle de acesso baseado em função (RBAC) à qual a tarefa administrativa específica é atribuída. O painel de controle do Lync Server 2013 implementa alterações de configuração Executando cmdlets do Shell de gerenciamento do Lync Server 2013. Para obter uma lista de funções predefinidas e os membros cmdlets podem ser executados, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">planejando o controle de acesso baseado em função no Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell. exe com o módulo do Lync Server 2013 carregado</strong> – ferramenta administrativa de linha de comando com cmdlets específicos para gerenciamento do Lync Server 2013.</p></td>
<td><p>Membro do grupo CsAdministrator ou membro de outra função RBAC à qual o cmdlet específico foi atribuído. Para obter uma lista de funções predefinidas e os membros cmdlets podem ser executados, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">planejando o controle de acesso baseado em função no Lync Server 2013</a> na documentação de planejamento.</p>
<p>Ou um membro de um ou mais dos seguintes grupos, dependendo do cmdlet:</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

