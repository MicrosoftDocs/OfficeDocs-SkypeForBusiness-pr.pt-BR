---
title: 'Lync Server 2013: publicando a topologia atualizada para adicionar bancos de dados de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f39e5f35dbd088543456f09ddd49f6aa2f9325c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="34f6a-102">Publicando a topologia atualizada para adicionar bancos de dados de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34f6a-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34f6a-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="34f6a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="34f6a-104">Após atualizar sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central antes de poder configurar e usar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="34f6a-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="34f6a-105">Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.</span><span class="sxs-lookup"><span data-stu-id="34f6a-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="34f6a-106">Para publicar sua topologia atualizada</span><span class="sxs-lookup"><span data-stu-id="34f6a-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="34f6a-107">Em um computador que está executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="34f6a-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34f6a-108">Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo <STRONG>Domain admins</STRONG> e o <STRONG>RTCUniversalServer Grupo Administradores</STRONG> e com permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivos do Lync Server 2013 (ou seja, o construtor de topologia pode configurar a lista de controle de acesso discricional necessária (DACLs) ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="34f6a-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="34f6a-109">Abra a topologia que você criou na seção anterior usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="34f6a-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="34f6a-110">Na árvore de console, clique com o botão direito do mouse no **Lync Server 2013**e, em seguida, clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="34f6a-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="34f6a-111">Na página **Publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="34f6a-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="34f6a-112">Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="34f6a-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34f6a-113">Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="34f6a-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="34f6a-114">Para obter detalhes sobre os direitos e permissões de administrador necessários, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permissões de implantação do SQL Server no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="34f6a-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="34f6a-115">Somente bancos de dados em servidores SQL Server dedicados podem ser instalados usando-se o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="34f6a-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="34f6a-116">Bancos de dados em servidores SQL Server que estão posicionados com outros componentes do servidor devem ser instalados executando-se a configuração local nesse computador.</span><span class="sxs-lookup"><span data-stu-id="34f6a-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="34f6a-117">Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="34f6a-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="34f6a-118">Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado.</span><span class="sxs-lookup"><span data-stu-id="34f6a-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="34f6a-119">Para obter detalhes, consulte Configurando o <A href="lync-server-2013-configuring-support-for-archiving.md">suporte para arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="34f6a-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

