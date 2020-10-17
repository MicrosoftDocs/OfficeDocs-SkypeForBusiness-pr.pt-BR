---
title: 'Lync Server 2013: instalar o banco de dados do servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d4027c02a866769c5b9866f6d315d31c6dcf80c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498658"
---
# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="9f183-102">Instalar o banco de dados do servidor Standard Edition para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f183-102">Install Standard Edition server database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f183-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9f183-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9f183-104">Configurar um servidor Standard Edition como o único servidor em sua infraestrutura que os usuários diferem de outras instalações de servidor, pois há uma seleção no **Assistente de implantação** especificamente para configurar o servidor inicial.</span><span class="sxs-lookup"><span data-stu-id="9f183-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="9f183-105">Para instalar um servidor do Standard Edition</span><span class="sxs-lookup"><span data-stu-id="9f183-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="9f183-106">Faça logon no servidor no qual você instalará o servidor Standard Edition como um administrador local ou um domínio equivalente.</span><span class="sxs-lookup"><span data-stu-id="9f183-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="9f183-107">Se você não tiver preparado os serviços de domínio do Active Directory, primeiro execute esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="9f183-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="9f183-108">Para obter detalhes, consulte [preparando os serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f183-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="9f183-109">No assistente de implantação do Lync Server, clique em **preparar primeiro servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="9f183-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="9f183-110">Na página **Preparar primeiro servidor Standard Edition**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9f183-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="9f183-111">Na página **executando comandos** , o SQL Server 2012 Express é instalado como o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="9f183-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="9f183-112">Regras de firewall necessárias são criadas.</span><span class="sxs-lookup"><span data-stu-id="9f183-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="9f183-113">Quando a instalação do banco de dados e software de pré-requisito estiver concluída, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9f183-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9f183-114">A instalação inicial pode levar algum tempo sem nenhuma atualização visível na tela de resumo de saída do comando.</span><span class="sxs-lookup"><span data-stu-id="9f183-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="9f183-115">Isso ocorre devido à instalação do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="9f183-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="9f183-116">Se você precisa monitorar a instalação do banco de dados, use o Gerenciador de Tarefas para monitorar a configuração.</span><span class="sxs-lookup"><span data-stu-id="9f183-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="9f183-117">Na página Assistente de implantação do Lync Server, clique em **instalar Construtor de topologia** se você ainda não tiver instalado as ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="9f183-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="9f183-118">Para obter detalhes, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9f183-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="9f183-119">Confirme se há marcas de seleção verdes ao lado de “Preparar Active Directory,” “Preparar primeiro servidor Standard Edition” e “Instalar Construtor de Topologias”.</span><span class="sxs-lookup"><span data-stu-id="9f183-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

