---
title: 'Lync Server 2013: configurar o SQL Server para o Lync Server'
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
ms.openlocfilehash: 20c35f1d82913c71523412c791d9b6a945f443e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535128"
---
# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="37466-102">Configurar o SQL Server para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37466-102">Configure SQL Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37466-103">_**Última modificação do tópico:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="37466-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="37466-104">Os tópicos desta seção discutem como implantar e configurar o SQL Server para usar em uma implantação corporativa do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37466-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="37466-105">Os servidores Standard Edition usam uma versão do SQL Server Express posicionada do SQL Server, que é o tamanho certo para as cargas de trabalho de um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="37466-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="37466-106">O repositório de gerenciamento central do Lync Server 2013 contém dados de usuário para todos os servidores Enterprise Edition dentro de um pool e foi projetado para estar localizado em um servidor back-end baseado em SQL Server.</span><span class="sxs-lookup"><span data-stu-id="37466-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="37466-107">Como um repositório centralizado, o repositório de gerenciamento central não pode ser instalado no mesmo computador que qualquer outra função do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37466-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="37466-108">O repositório de gerenciamento central não pode residir em um servidor Enterprise Edition no pool.</span><span class="sxs-lookup"><span data-stu-id="37466-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="37466-109">O repositório de gerenciamento central é criado automaticamente quando você publica a topologia pela primeira vez e seleciona criar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="37466-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="37466-110">O computador que você designou como servidor de back-end já deve estar executando o software de banco de dados do SQL Server para que a instalação seja bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="37466-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37466-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="37466-111">In This Section</span></span>

  - [<span data-ttu-id="37466-112">Posicionamento de arquivos de log e dados do SQL Server para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37466-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="37466-113">Configurar o SQL Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37466-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="37466-114">Permissões de implantação para o SQL Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37466-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="37466-115">Instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37466-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="37466-116">Noções básicas sobre requisitos de firewall para o SQL Server com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37466-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="37466-117">Configurar o cluster do SQL Server para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37466-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

