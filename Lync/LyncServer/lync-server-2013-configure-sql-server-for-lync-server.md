---
title: 'Lync Server 2013: Configurar o SQL Server para Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efdd9d8fa7b010b420c7c532d422c9b52b6d69ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="9c4f9-102">Configurar o SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4f9-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c4f9-103">_**Tópico da última modificação:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="9c4f9-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="9c4f9-104">Os tópicos desta seção abordam como implantar e configurar o SQL Server para usar em uma implantação empresarial do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="9c4f9-105">Os servidores de edição padrão usam uma versão posicionada do SQL Server Express do SQL Server que está certa para as cargas de trabalho de um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="9c4f9-106">O repositório de gerenciamento central do Lync Server 2013 mantém dados do usuário para todos os servidores da Enterprise Edition dentro de um pool e foi projetado para estar localizado em um servidor back-end baseado no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="9c4f9-107">Como um repositório centralizado, o repositório de gerenciamento central não pode ser instalado no mesmo computador que qualquer outra função do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="9c4f9-108">O repositório de gerenciamento central não pode residir em um servidor Enterprise Edition no pool.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="9c4f9-109">O repositório de gerenciamento central é criado automaticamente quando você publica a topologia pela primeira vez e seleciona a opção para criar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="9c4f9-110">O computador que você designa como o servidor back-end já deve estar executando o software de banco de dados do SQL Server para que a instalação seja bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9c4f9-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9c4f9-111">In This Section</span></span>

  - [<span data-ttu-id="9c4f9-112">Posicionamento de dados do Servidor SQL e do arquivo de log para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4f9-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="9c4f9-113">Configurar SQL Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4f9-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="9c4f9-114">Permissões de implantação para Servidor SQL no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4f9-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="9c4f9-115">Instalação de banco de dados usando o Shell de Gerenciamento do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4f9-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="9c4f9-116">Compreendendo os requisitos de firewall para Servidor SQL com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4f9-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="9c4f9-117">Configurar o cluster do SQL Server para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4f9-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

