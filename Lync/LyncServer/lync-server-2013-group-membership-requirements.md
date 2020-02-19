---
title: 'Lync Server 2013: requisitos de associação de grupo'
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
ms.openlocfilehash: 93c1a79d39a70c21e353799a43c76599cc7af2b5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Requisitos de associação de grupo para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

A tabela a seguir resume o grupo ou grupos aos quais uma pessoa deve pertencer para instalar, gerenciar e solucionar problemas com êxito do Lync Server 2013.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Executável do Lync Server 2013</th>
<th>Participação no grupo necessária</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup. exe</strong> – executável que inicia a instalação das ferramentas administrativas do Lync Server 2013.</p></td>
<td><p>Membros do grupo de Administradores Locais no computador o qual o executável está sendo executado. Membro do grupo usuários do domínio para ler as informações nos serviços de domínio do Active Directory. Este nível de permissão é necessário porque a instalação automática dos pacotes MSI necessários no computador local requer privilégios que permitam ler e gravar dos recursos do computador local protegido, como diretórios de Arquivos de Programas e registros protegidos, como a ramificação da Máquina Local.</p>
<div>

> [!TIP]  
> Você também pode delegar permissões de instalação para usuários e grupos os quais não deseja fornecer participação no grupo de Administradores de Domínio. Para obter detalhes, consulte <A href="lync-server-2013-granting-setup-permissions.md">granting setup Permissions in Lync Server 2013</A> na documentação de implantação.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong> – Chamado pelo setup.exe, o deploy.exe é responsável pela implantação dos componentes de software para funções do servidor.</p></td>
<td><p>Membros do grupo de Administradores Locais no computador o qual o executável está executando. Membros do grupo de Usuários de Domínio para ler informações no AD DS. Este nível de permissão é necessário porque a instalação automática dos pacotes MSI necessários no computador local precisam de privilégios que permitam a leitura e gravação nos recursos do computador local protegido, como diretórios de Arquivos de Programas e registros protegidos, como a ramificação da Máquina Local. A associação ao grupo RtcUniversalReadOnlyAdmins é necessária para ler o repositório de gerenciamento central.</p>
<div>

> [!NOTE]  
> Se você estiver executando o sistema operacional Windows Vista ou o sistema operacional Windows 7, você será solicitado pelo UAC (controle de conta de usuário) para prosseguir com a instalação. Se você estiver logado em uma conta de usuário padrão, precisará de alguém que seja membro do grupo de Administradores Locais para fornecer as credenciais quando solicitado para uma conta com permissões de instalar software.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong> – Chamado pelo setup.exe, o bootstrapper.exe é responsável pela implantação e configuração das funções do servidor.</p></td>
<td><p>Membros do grupo de Administradores Locais no computador o qual o executável está sendo executado. Membro do grupo RTCUniversalServerAdmins para executar o Bootstrapper.exe. Membro do grupo de Usuários do Domínio para ler informações no AD DS. Este nível de permissão é necessário porque a instalação automática dos pacotes MSI necessários no computador local precisam de privilégios que permitam a leitura e gravação nos recursos do computador local protegido, como diretórios de Arquivos de Programas e registros protegidos, como a ramificação da Máquina Local.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> – interface de usuário orientada por assistente para criar, exibir, ajustar e validar topologias do Lync Server 2013.</p></td>
<td><p>Membros do grupo de Administradores Locais o qual o executável está sendo executado para visualizar a topologia. Membros do grupo RTCUniversalServerAdmins para alterar as definições de configuração. Membros do grupo RTCUniversalServerAdmins e grupo de Administradores de Domínio ou membros do grupo RTCUniversalServerAdmins (somente se o grupo possuir permissões de instalação delegadas) para publicar a topologia. Para obter detalhes sobre como delegar permissões de configuração para permitir que os membros do grupo RTCUniversalServerAdmins publiquem a topologia sem ser membros do grupo de administradores de domínio, consulte <a href="lync-server-2013-granting-setup-permissions.md">granting setup Permissions in Lync Server 2013</a> na documentação de implantação.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> – interface gráfica de usuário baseada na Web para o gerenciamento do Lync Server 2013.</p></td>
<td><p>Membro do grupo ou outra função RBAC o qual a tarefa administrativa específica é atribuída. O painel de controle do Lync Server 2013 implementa as alterações de configuração executando os cmdlets do Shell de gerenciamento do Lync Server 2013. Para obter uma lista de funções predefinidas e os membros de cmdlets podem ser executados, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell. exe com o módulo do Lync Server 2013 carregado</strong> – ferramenta administrativa de linha de comando com cmdlets específicos para o gerenciamento do Lync Server 2013.</p></td>
<td><p>Membro do grupo CsAdministrator ou membro de outra função do RBAC o qual o cmdlet específico foi atribuído. Para obter uma lista de funções predefinidas e os membros de cmdlets podem ser executados, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> na documentação de planejamento.</p>
<p>Ou, membro de um ou mais dos seguintes grupos, dependendo do cmdlet:</p>
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

