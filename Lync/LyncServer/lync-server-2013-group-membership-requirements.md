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
ms.openlocfilehash: f8726d471b1db95aa67cca58a77452d9faa43df4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="3b4ee-102">Requisitos de associação de grupo para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b4ee-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b4ee-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3b4ee-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3b4ee-104">A tabela a seguir resume o grupo ou grupos aos quais uma pessoa deve pertencer para instalar, gerenciar e solucionar problemas com êxito do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b4ee-105">Executável do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b4ee-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="3b4ee-106">Participação no grupo necessária</span><span class="sxs-lookup"><span data-stu-id="3b4ee-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b4ee-107"><strong>Setup. exe</strong> – executável que inicia a instalação das ferramentas administrativas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="3b4ee-108">Membros do grupo de Administradores Locais no computador o qual o executável está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="3b4ee-109">Membro do grupo usuários do domínio para ler as informações nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="3b4ee-110">Este nível de permissão é necessário porque a instalação automática dos pacotes MSI necessários no computador local requer privilégios que permitam ler e gravar dos recursos do computador local protegido, como diretórios de Arquivos de Programas e registros protegidos, como a ramificação da Máquina Local.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="3b4ee-111">Você também pode delegar permissões de instalação para usuários e grupos os quais não deseja fornecer participação no grupo de Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="3b4ee-112">Para obter detalhes, consulte <A href="lync-server-2013-granting-setup-permissions.md">granting setup Permissions in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b4ee-113"><strong>Deploy.exe</strong> – Chamado pelo setup.exe, o deploy.exe é responsável pela implantação dos componentes de software para funções do servidor.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="3b4ee-114">Membros do grupo de Administradores Locais no computador o qual o executável está executando.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="3b4ee-115">Membros do grupo de Usuários de Domínio para ler informações no AD DS.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="3b4ee-116">Este nível de permissão é necessário porque a instalação automática dos pacotes MSI necessários no computador local precisam de privilégios que permitam a leitura e gravação nos recursos do computador local protegido, como diretórios de Arquivos de Programas e registros protegidos, como a ramificação da Máquina Local.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="3b4ee-117">A associação ao grupo RtcUniversalReadOnlyAdmins é necessária para ler o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3b4ee-118">Se você estiver executando o sistema operacional Windows Vista ou o sistema operacional Windows 7, você será solicitado pelo UAC (controle de conta de usuário) para prosseguir com a instalação.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="3b4ee-119">Se você estiver logado em uma conta de usuário padrão, precisará de alguém que seja membro do grupo de Administradores Locais para fornecer as credenciais quando solicitado para uma conta com permissões de instalar software.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b4ee-120"><strong>Bootstrapper.exe</strong> – Chamado pelo setup.exe, o bootstrapper.exe é responsável pela implantação e configuração das funções do servidor.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="3b4ee-p105">Membros do grupo de Administradores Locais no computador o qual o executável está sendo executado. Membro do grupo RTCUniversalServerAdmins para executar o Bootstrapper.exe. Membro do grupo de Usuários do Domínio para ler informações no AD DS. Este nível de permissão é necessário porque a instalação automática dos pacotes MSI necessários no computador local precisam de privilégios que permitam a leitura e gravação nos recursos do computador local protegido, como diretórios de Arquivos de Programas e registros protegidos, como a ramificação da Máquina Local.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b4ee-125"><strong>TopologyBuilder</strong> – interface de usuário orientada por assistente para criar, exibir, ajustar e validar topologias do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="3b4ee-126">Membros do grupo de Administradores Locais o qual o executável está sendo executado para visualizar a topologia.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="3b4ee-127">Membros do grupo RTCUniversalServerAdmins para alterar as definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="3b4ee-128">Membros do grupo RTCUniversalServerAdmins e grupo de Administradores de Domínio ou membros do grupo RTCUniversalServerAdmins (somente se o grupo possuir permissões de instalação delegadas) para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="3b4ee-129">Para obter detalhes sobre como delegar permissões de configuração para permitir que os membros do grupo RTCUniversalServerAdmins publiquem a topologia sem ser membros do grupo de administradores de domínio, consulte <a href="lync-server-2013-granting-setup-permissions.md">granting setup Permissions in Lync Server 2013</a> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b4ee-130"><strong>AdminUIHost</strong> – interface gráfica de usuário baseada na Web para o gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="3b4ee-131">Membro do grupo ou outra função RBAC o qual a tarefa administrativa específica é atribuída.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="3b4ee-132">O painel de controle do Lync Server 2013 implementa as alterações de configuração executando os cmdlets do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="3b4ee-133">Para obter uma lista de funções predefinidas e os membros de cmdlets podem ser executados, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b4ee-134"><strong>PowerShell. exe com o módulo do Lync Server 2013 carregado</strong> – ferramenta administrativa de linha de comando com cmdlets específicos para o gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="3b4ee-135">Membro do grupo CsAdministrator ou membro de outra função do RBAC o qual o cmdlet específico foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="3b4ee-136">Para obter uma lista de funções predefinidas e os membros de cmdlets podem ser executados, consulte <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="3b4ee-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="3b4ee-137">Ou, membro de um ou mais dos seguintes grupos, dependendo do cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3b4ee-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="3b4ee-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3b4ee-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="3b4ee-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3b4ee-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="3b4ee-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="3b4ee-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

