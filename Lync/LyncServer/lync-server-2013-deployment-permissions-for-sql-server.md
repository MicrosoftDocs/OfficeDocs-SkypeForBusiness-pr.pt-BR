---
title: 'Lync Server 2013: permissões de implantação para o SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab8628859d5bcb4306cb745509d572a77a21851e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522648"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="3d16c-102">Permissões de implantação para o SQL Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d16c-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d16c-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3d16c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3d16c-104">O Microsoft SQL Server 2012 tem requisitos específicos ao instalar e implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d16c-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="3d16c-105">Como o Windows e o SQL Server definem sua segurança de forma diferente, fazer logon como administrador no domínio do Active Directory não concede implicitamente permissões para o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d16c-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="3d16c-106">Você também deve ser membro da entidade sysadmin no servidor baseado no SQL Server que está configurando.</span><span class="sxs-lookup"><span data-stu-id="3d16c-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="3d16c-107">Permissões necessárias para a instalação do banco de dados e do Lync Server</span><span class="sxs-lookup"><span data-stu-id="3d16c-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="3d16c-108">As opções a seguir detalham três associações de associação de grupo e permissões para instalação de arquivos do Lync Server 2013 e bancos de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d16c-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="3d16c-109">Escolha o cenário que melhor atenda às necessidades de sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d16c-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="3d16c-110">Permissões e associações de membros do grupo</span><span class="sxs-lookup"><span data-stu-id="3d16c-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d16c-111">Função do SQL Server ou do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d16c-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="3d16c-112">Permissões e membros de grupo típicos de função do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d16c-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="3d16c-113">Função-permissões típicas do Lync Server 2013 e Associação de grupo</span><span class="sxs-lookup"><span data-stu-id="3d16c-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="3d16c-114">Resultado de permissões</span><span class="sxs-lookup"><span data-stu-id="3d16c-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d16c-115">Administrador do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d16c-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="3d16c-116">Deve ser concedido a membros do grupo de segurança sysadmins do SQL Server e a membros do grupo Administradores local do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d16c-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="3d16c-117">Deve ser um membro do grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3d16c-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="3d16c-118">Lync Server 2013 o administrador tem as permissões adequadas para instalar os bancos de dados do Lync Server 2013 e do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d16c-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d16c-119">Administrador do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d16c-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="3d16c-120">Membro do grupo sysadmin do SQL Server (ou equivalente) e membro do grupo Administradores local do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d16c-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="3d16c-121">Deve ser um membro do grupo RTCUniversalServerReadOnly</span><span class="sxs-lookup"><span data-stu-id="3d16c-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="3d16c-122">O administrador do SQL Server tem as permissões adequadas para instalar os bancos de dados do Lync Server 2013 e do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d16c-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d16c-123">Os dois administradores compartilham as tarefas de instalação</span><span class="sxs-lookup"><span data-stu-id="3d16c-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="3d16c-124">O administrador do SQL Server é membro do grupo de sysadmins (ou equivalente) e membro do grupo Administradores local do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d16c-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="3d16c-125">Lync Server 2013 o administrador é membro de RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3d16c-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="3d16c-126">O administrador do Lync Server 2013 pode instalar o Lync Server 2013, mas não pode instalar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3d16c-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="3d16c-127">O administrador do SQL Server usa o Shell de gerenciamento do Lync Server e os cmdlets do Windows PowerShell fornecidos pelo administrador do Lync Server 2013 para instalar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3d16c-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="3d16c-128">O Shell de gerenciamento do Lync Server 2013 usado pelo administrador do SQL Server é instalado no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="3d16c-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="3d16c-129">Isso elimina a necessidade de instalar as ferramentas administrativas do Lync Server 2013 no servidor baseado no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d16c-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

