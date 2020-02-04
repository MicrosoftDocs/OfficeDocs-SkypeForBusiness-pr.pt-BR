---
title: 'Lync Server 2013: Failover do Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd62d4037ae1795a553d207cb698f88f9b3b8ab8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="51190-102">Failover do Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51190-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51190-103">_**Tópico da última modificação:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="51190-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="51190-104">O failover do servidor de chat persistente foi projetado para ser principalmente um processo manual.</span><span class="sxs-lookup"><span data-stu-id="51190-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="51190-105">O procedimento de failover baseia-se na pressuposição de que o centro de dados secundário está em funcionamento, mas os serviços persistentes do servidor de chat em que o banco de dados de chat persistente primário está localizado não estão disponíveis, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="51190-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="51190-106">Banco de dados persistente do servidor de chat e banco de dados persistente do servidor de chat persistente estão inativos.</span><span class="sxs-lookup"><span data-stu-id="51190-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="51190-107">O servidor front-end do Lync Server está inoperante.</span><span class="sxs-lookup"><span data-stu-id="51190-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="51190-108">O procedimento é baseado em duas etapas básicas:</span><span class="sxs-lookup"><span data-stu-id="51190-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="51190-109">Recuperar o banco de dados de chat persistente primário (MGC).</span><span class="sxs-lookup"><span data-stu-id="51190-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="51190-110">Estabelecer o espelhamento para o novo banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="51190-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="51190-111">O banco de dados de conformidade de chat persistente (mgccomp) não apresentou failover.</span><span class="sxs-lookup"><span data-stu-id="51190-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="51190-112">O conteúdo deste banco de dados é transitório e é excluído como os processos do adaptador de conformidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="51190-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="51190-113">É sua responsabilidade, como administrador de chat persistente, gerenciar corretamente a saída do adaptador para evitar perda de dados.</span><span class="sxs-lookup"><span data-stu-id="51190-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="51190-114">Para fazer failover do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="51190-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="51190-115">Remova o envio de log do banco de dados de envio de log de backup persistente do servidor de chat.</span><span class="sxs-lookup"><span data-stu-id="51190-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="51190-116">Usando o SQL Server Management Studio, conecte-se à instância do banco de dados em que o banco de dados de backup do servidor de chat persistente MGC está localizado.</span><span class="sxs-lookup"><span data-stu-id="51190-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="51190-117">Abra uma janela Consulta para o banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="51190-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="51190-118">Use o seguinte comando para remover o envio de logs:</span><span class="sxs-lookup"><span data-stu-id="51190-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="51190-119">Copie qualquer arquivo de backup não copiado do compartilhamento de backup para a pasta de destino da cópia do servidor de backup.</span><span class="sxs-lookup"><span data-stu-id="51190-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="51190-120">Use qualquer backup de log de transação não aplicado na sequência para o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="51190-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="51190-121">Para obter detalhes, consulte "como aplicar um backup de log de transação (Transact-SQL)" http://go.microsoft.com/fwlink/p/?linkid=247428em.</span><span class="sxs-lookup"><span data-stu-id="51190-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at http://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="51190-p103">Coloque o banco de dados mgc de backup online. Usando a janela Consulta que é exibida na etapa 1b, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="51190-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="51190-124">Encerre todas as conexões com o banco de dados mgc, se houver:</span><span class="sxs-lookup"><span data-stu-id="51190-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="51190-125">**exec SP\_who2** para identificar as conexões com o banco de dados MGC.</span><span class="sxs-lookup"><span data-stu-id="51190-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="51190-126">\*\*eliminar \<spid\> \*\* para encerrar essas conexões.</span><span class="sxs-lookup"><span data-stu-id="51190-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="51190-127">Coloque o banco de dados online:</span><span class="sxs-lookup"><span data-stu-id="51190-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="51190-128">**Restaurar Banco de Dados mgc com recuperação**.</span><span class="sxs-lookup"><span data-stu-id="51190-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="51190-129">No Shell de gerenciamento do Lync Server, use o comando **set-CsPersistentChatState-Identity "Service: ATL-cs-001.litwareinc.com" – poolstate FailedOver** para fazer failover para o banco de dados de backup do MGC.</span><span class="sxs-lookup"><span data-stu-id="51190-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="51190-130">Não se esqueça de substituir o nome de domínio totalmente qualificado do seu pool de Chat Persistente por atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="51190-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="51190-131">O banco de dados de backup mgc agora serve como o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="51190-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="51190-132">No Shell de gerenciamento do Lync Server, use o cmdlet **install-CsMirrorDatabase** para estabelecer um espelho de alta disponibilidade para o banco de dados de backup que agora funciona como o banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="51190-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="51190-133">Use a instância do banco de dados de backup como o banco de dados primário e a instância do banco de dados de espelho de backup como a instância do espelho.</span><span class="sxs-lookup"><span data-stu-id="51190-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="51190-134">Este não é o mesmo espelho do que aquele inicialmente configurado para o banco de dados primário durante a configuração.</span><span class="sxs-lookup"><span data-stu-id="51190-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="51190-135">Para obter detalhes, consulte a seção "usando cmdlets do Shell de gerenciamento do Lync Server" em [implantando o espelhamento do SQL para servidor back-end alta disponibilidade no Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="51190-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="51190-136">Defina os servidores ativos do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="51190-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="51190-137">No Shell de comando do Lync Server, use o cmdlet **set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.</span><span class="sxs-lookup"><span data-stu-id="51190-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="51190-138">Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="51190-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="51190-139">Nesse ponto, o failover do banco de dados primário do servidor de chat persistente para o banco de dados de backup do servidor de chat persistente é concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="51190-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

