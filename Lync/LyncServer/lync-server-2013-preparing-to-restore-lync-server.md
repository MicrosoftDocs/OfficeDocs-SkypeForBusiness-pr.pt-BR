---
title: 'Lync Server 2013: preparando para restaurar o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f31354ee87cdf7df5efdb6c4e2accf3758829c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506828"
---
# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="37236-102">Preparando para restaurar o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37236-102">Preparing to restore Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37236-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="37236-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="37236-104">Antes de começar a restauração de servidores e bancos de dados após uma falha, você precisa determinar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="37236-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="37236-105">O que precisa ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="37236-105">What needs to be restored.</span></span>

  - <span data-ttu-id="37236-106">O hardware, o software, os dados e as ferramentas de que você precisa para a restauração.</span><span class="sxs-lookup"><span data-stu-id="37236-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="37236-107">Determinando o quê restaurar</span><span class="sxs-lookup"><span data-stu-id="37236-107">Determining What to Restore</span></span>

<span data-ttu-id="37236-108">Este tópico descreve como restaurar as interrupções do Lync Server que ocorrem no nível do servidor, pool ou repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="37236-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="37236-109">Se o repositório de gerenciamento central falhar, sua implantação do Lync Server continuará a funcionar, mas não será possível fazer alterações na configuração.</span><span class="sxs-lookup"><span data-stu-id="37236-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="37236-110">Se um servidor Standard Edition ou de Back-End falhar, o pool de usuário para de funcionar.</span><span class="sxs-lookup"><span data-stu-id="37236-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="37236-111">Se qualquer outro servidor falhar, a magnitude da falha depende da função de servidor que o servidor está executando e de se o servidor hospeda um ou mais bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="37236-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="37236-112">O que restaurar</span><span class="sxs-lookup"><span data-stu-id="37236-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37236-113">Se isto falhou</span><span class="sxs-lookup"><span data-stu-id="37236-113">If this failed</span></span></th>
<th><span data-ttu-id="37236-114">Consulte esta seção:</span><span class="sxs-lookup"><span data-stu-id="37236-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37236-115">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="37236-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="37236-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restaurando um servidor Standard Edition no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37236-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37236-117">Repositório de Gerenciamento Central</span><span class="sxs-lookup"><span data-stu-id="37236-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="37236-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restaurando o servidor que hospeda o repositório de gerenciamento central no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37236-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37236-119">Back-end do Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="37236-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="37236-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restaurando um servidor back-end Enterprise Edition no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37236-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37236-121">Servidor primário de back-end do Enterprise Edition espelhado</span><span class="sxs-lookup"><span data-stu-id="37236-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="37236-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restaurando um servidor back-end Enterprise Edition espelhado no Lync Server 2013-principal</a></span><span class="sxs-lookup"><span data-stu-id="37236-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37236-123">Servidor secundário de back-end do Enterprise Edition espelhado</span><span class="sxs-lookup"><span data-stu-id="37236-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="37236-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restaurando um servidor back-end Enterprise Edition espelhado no Lync Server 2013-espelho</a></span><span class="sxs-lookup"><span data-stu-id="37236-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37236-125">Qualquer servidor Enterprise Edition executando uma função de servidor, como um servidor front-end, servidor de borda, diretor, servidor de mediação, ou servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="37236-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="37236-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restaurando um servidor membro Enterprise Edition no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37236-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37236-127">Um pool completo do Lync Server</span><span class="sxs-lookup"><span data-stu-id="37236-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="37236-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restaurando um pool do Lync Server no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37236-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37236-129">Repositório de arquivos Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="37236-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="37236-130"><a href="lync-server-2013-restoring-a-file-store.md">Restaurando um repositório de arquivos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37236-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37236-131">Um banco de dados de monitoramento autônomo ou banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="37236-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="37236-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauração de dados de monitoramento ou arquivamento no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37236-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37236-133">Um banco de dados persistente de chat autônomo</span><span class="sxs-lookup"><span data-stu-id="37236-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="37236-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restaurando dados de chat persistente no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="37236-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="37236-135">Coletando hardware, software e ferramentas</span><span class="sxs-lookup"><span data-stu-id="37236-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="37236-136">Quando você restaurar um servidor, será necessário iniciar com um computador novo ou limpo.</span><span class="sxs-lookup"><span data-stu-id="37236-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="37236-137">Além disso, você deve ter os seguintes hardwares e softwares disponíveis:</span><span class="sxs-lookup"><span data-stu-id="37236-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="37236-138">Um servidor novo ou limpo com o mesmoFQDN (nome de domínio totalmente qualificado) do servidor que falhou.</span><span class="sxs-lookup"><span data-stu-id="37236-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="37236-139">Ao instalar o sistema operacional, certifique-se de não excluir a conta de computador nos serviços de domínio do Active Directory e se as permissões de grupo da conta são mantidas.</span><span class="sxs-lookup"><span data-stu-id="37236-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="37236-140">Software de instalação para o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="37236-140">Installation software for the operating system.</span></span> <span data-ttu-id="37236-141">Para instalar o sistema operacional, use as configurações de implantação do servidor e procedimentos estabelecidos pela organização.</span><span class="sxs-lookup"><span data-stu-id="37236-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="37236-142">Você deve ter esses procedimentos e requisitos de configuração disponíveis ao restaurar o serviço.</span><span class="sxs-lookup"><span data-stu-id="37236-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="37236-143">Software de instalação do SQL Server 2012 ou SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="37236-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="37236-144">Para instalar um servidor de banco de dados, use a versão adequada do SQL Server e os procedimentos de implantação do servidor de banco de dados e configurações estabelecidos pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="37236-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="37236-145">Você deve ter esses procedimentos e requisitos de configuração disponíveis ao restaurar o serviço.</span><span class="sxs-lookup"><span data-stu-id="37236-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37236-146">O assistente de implantação do Lync Server instala automaticamente o SQL Server 2012 Express em cada servidor Standard Edition e em qualquer outro servidor do Lync Server quando um repositório de configuração local é instalado, a menos que você tenha pré-instalado o SQL Server 2012 ou o SQL Server 2008 R2 no servidor.</span><span class="sxs-lookup"><span data-stu-id="37236-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="37236-147">Software para fazer imagens de sistema.</span><span class="sxs-lookup"><span data-stu-id="37236-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="37236-148">Recomendamos que você faça uma cópia de imagem do sistema depois de instalar o sistema operacional e o SQL Server e antes de iniciar a restauração, para que você possa usá-la como um ponto de reversão caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="37236-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="37236-149">Software de instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37236-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="37236-150">O assistente de implantação do Lync Server está localizado na pasta de instalação do Lync Server ou mídia no \\ arquivo de instalação \\ AMD64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="37236-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="37236-151">Durante a restauração, você pode usar as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="37236-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="37236-152">Cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="37236-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="37236-153">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="37236-153">Import-CsUserData</span></span>

  - <span data-ttu-id="37236-154">Ferramentas para restaurar as pastas do Windows</span><span class="sxs-lookup"><span data-stu-id="37236-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="37236-155">Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="37236-155">Topology Builder</span></span>

  - <span data-ttu-id="37236-156">Utilitários de banco de dados de SQL Server, como o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37236-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="37236-157">Preparação para restaurar um servidor</span><span class="sxs-lookup"><span data-stu-id="37236-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="37236-158">Antes de restaurar o servidor, você deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="37236-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="37236-159">Instale o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="37236-159">Install the operating system.</span></span>

2.  <span data-ttu-id="37236-160">Se o servidor for um servidor back-end, instale o SQL Server 2012 ou o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="37236-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="37236-161">Restaure ou registre novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="37236-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="37236-162">Para obter detalhes sobre certificados, consulte "requisitos adicionais de backup" em [requisitos de backup e restauração no Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="37236-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="37236-163">Tire uma imagem do sistema antes de iniciar a restauração para usar como um ponto de reversão, caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="37236-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37236-164">O assistente de implantação do Lync Server e os cmdlets descritos nos procedimentos deste tópico e tópicos relacionados, define todas as listas de controle de acesso (ACLs) necessárias.</span><span class="sxs-lookup"><span data-stu-id="37236-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="37236-165">Verifique se o hardware e o software necessários para os componentes que você planeja restaurar estão disponíveis antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="37236-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="37236-166">Depois de instalar o sistema operacional e o SQL Server, a maioria das etapas nos procedimentos de restauração a seguir pode ser executada remotamente.</span><span class="sxs-lookup"><span data-stu-id="37236-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="37236-167">As exceções estão indicadas nos procedimentos.</span><span class="sxs-lookup"><span data-stu-id="37236-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="37236-168">Você também deve ter o plano de backup e restauração da sua organização e as informações do seu último backup, como as informações nas planilhas deste documento (para obter detalhes, consulte [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponível antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="37236-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

