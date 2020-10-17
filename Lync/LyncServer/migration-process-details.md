---
title: Processo de migração-detalhes
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c15c5cf8a2eaa207467f53d57d82e6cf4491e13
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527198"
---
# <a name="migration-process---details"></a><span data-ttu-id="bd958-102">Processo de migração-detalhes</span><span class="sxs-lookup"><span data-stu-id="bd958-102">Migration process - details</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd958-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="bd958-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="bd958-104">Use os seguintes pré-requisitos e etapas detalhadas para migrar o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat para o Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bd958-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="bd958-105">Pré-requisitos para migração</span><span class="sxs-lookup"><span data-stu-id="bd958-105">Prerequisites for Migration</span></span>

<span data-ttu-id="bd958-106">Certifique-se de que você tenha atendido aos seguintes pré-requisitos antes de migrar o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat para o Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bd958-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="bd958-107">Implante pelo menos um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd958-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="bd958-108">Se você tiver vários pools do Lync Server 2013, decida qual pool do Lync Server 2013 será o pool de Home para o novo pool do servidor de chat persistente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd958-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="bd958-109">Instale o pool do servidor de chat persistente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd958-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="bd958-110">Ele estará vazio (sem categorias, salas ou suplementos).</span><span class="sxs-lookup"><span data-stu-id="bd958-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="bd958-111">Antes de migrar suas categorias, salas ou suplementos herdados, você pode criar salas, categorias ou suplementos em sua implantação do Lync Server 2013, persistent chat Server.</span><span class="sxs-lookup"><span data-stu-id="bd958-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd958-112">Lembre-se de que esses itens recém-criados podem entrar em conflito com itens herdados migrados.</span><span class="sxs-lookup"><span data-stu-id="bd958-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="bd958-113">Evitar qualquer conflito de nomes; caso contrário, eles serão substituídos quando os dados herdados forem migrados.</span><span class="sxs-lookup"><span data-stu-id="bd958-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="bd958-114">Preparando os dados de origem para migração</span><span class="sxs-lookup"><span data-stu-id="bd958-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="bd958-115">Execute as seguintes etapas para preparar adequadamente os dados de origem para a migração.</span><span class="sxs-lookup"><span data-stu-id="bd958-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="bd958-116">Faça backup dos bancos de dados de origem para o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="bd958-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="bd958-117">Para obter detalhes sobre como fazer backup do SQL Server, consulte "visão geral do backup (SQL Server)" em <https://go.microsoft.com/fwlink/p/?linkid=254851> .</span><span class="sxs-lookup"><span data-stu-id="bd958-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd958-118">Os serviços de domínio do Active Directory devem ser os mesmos.</span><span class="sxs-lookup"><span data-stu-id="bd958-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="bd958-119">Como uma condição para migração, você não pode migrar para um pool em uma implantação diferente (especificamente, em uma floresta diferente do Active Directory).</span><span class="sxs-lookup"><span data-stu-id="bd958-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="bd958-120">Inspecione seu Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat Chat e configuração de categoria.</span><span class="sxs-lookup"><span data-stu-id="bd958-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="bd958-121">Quaisquer alterações em categorias, salas ou suplementos em sua implantação herdada existente serão feitas pela ferramenta de administração de chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="bd958-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="bd958-122">Quaisquer alterações em categorias, salas ou suplementos no Lync Server 2013, implantação de servidor de chat persistente são realizadas pelo painel de controle do Lync Server ou cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd958-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="bd958-123">Siga estas etapas para preparar seu sistema herdado para migração.</span><span class="sxs-lookup"><span data-stu-id="bd958-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="bd958-124">O servidor de chat persistente oferece suporte a um único nível de categorias, ao contrário de um conjunto hierárquico profundo de categorias.</span><span class="sxs-lookup"><span data-stu-id="bd958-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="bd958-125">Após a migração, as subcategorias são prefixadas com nomes de categoria pai completo.</span><span class="sxs-lookup"><span data-stu-id="bd958-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="bd958-126">Convém simplificar e achatar sua estrutura de categorias existente para que a estrutura resultante atenda às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="bd958-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="bd958-127">Verifique os **gerentes** na categoria raiz.</span><span class="sxs-lookup"><span data-stu-id="bd958-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="bd958-128">Se existirem gerentes nesse nível, esses usuários serão adicionados como **gerentes a todas as salas** após a migração.</span><span class="sxs-lookup"><span data-stu-id="bd958-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="bd958-129">Se isso não for um requisito para sua organização, você precisa remover esses gerentes da categoria raiz.</span><span class="sxs-lookup"><span data-stu-id="bd958-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="bd958-130">Verifique o tamanho dos nomes de sala.</span><span class="sxs-lookup"><span data-stu-id="bd958-130">Verify the length of room names.</span></span> <span data-ttu-id="bd958-131">Após a migração, devido às estruturas de categoria simplificadas, se as salas existirem em uma categoria filha, elas serão prefixadas com nomes de categoria pai completo.</span><span class="sxs-lookup"><span data-stu-id="bd958-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="bd958-132">O limite de nomenclatura é de 256 caracteres, incluindo nomes de categoria pai.</span><span class="sxs-lookup"><span data-stu-id="bd958-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="bd958-133">Você deve verificar o tamanho dos nomes de sala e possivelmente diminuir o comprimento, se eles forem muito longos.</span><span class="sxs-lookup"><span data-stu-id="bd958-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="bd958-134">No Lync Server 2013, se as configurações de **convites** de categoria estiverem definidas como true, você poderá escolher true ou false para convites para salas nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="bd958-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="bd958-135">No entanto, se as configurações de convites de categoria estiverem definidas como false, as salas nessa categoria têm convites desativados.</span><span class="sxs-lookup"><span data-stu-id="bd958-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="bd958-136">Antes da migração, você deve redefinir as configurações de convite em sua versão do servidor de chat de grupo do Lync Server herdado, se quiser que a (s) sala (s) exista em uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="bd958-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="bd958-137">Caso contrário, durante a migração, o Lync Server 2013 exibe avisos e define salas como o valor padrão de false.</span><span class="sxs-lookup"><span data-stu-id="bd958-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="bd958-138">Se você usou arquivos em salas de chat, deve usar o XCOPY manualmente os arquivos para o novo repositório de arquivos de chat persistente após a migração.</span><span class="sxs-lookup"><span data-stu-id="bd958-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="bd958-139">As ferramentas não fazem isso.</span><span class="sxs-lookup"><span data-stu-id="bd958-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="bd958-140">Se você tivesse usuários federados e salas com usuários federados, lembre-se de que o servidor de chat persistente não dá suporte à Federação.</span><span class="sxs-lookup"><span data-stu-id="bd958-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="bd958-141">As salas com usuários federados serão migradas; no entanto, os usuários propriamente ditos não poderão acessar o conteúdo, pois o acesso federado não é suportado.</span><span class="sxs-lookup"><span data-stu-id="bd958-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="bd958-142">Identifique as salas que você não deseja migrar e marque-as como desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="bd958-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="bd958-143">Identifique a data além da qual você deseja migrar o conteúdo da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="bd958-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="bd958-144">Por exemplo, talvez você não queira migrar mensagens antes de 1º de janeiro de 2010, pois essas mensagens podem ser obsoletas ou não relevantes para a migração.</span><span class="sxs-lookup"><span data-stu-id="bd958-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="bd958-145">Realizando a migração</span><span class="sxs-lookup"><span data-stu-id="bd958-145">Performing the Migration</span></span>

<span data-ttu-id="bd958-146">Execute as seguintes etapas para migrar seu servidor de chat de grupo herdado.</span><span class="sxs-lookup"><span data-stu-id="bd958-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="bd958-147">Desligue o Lync Server 2010, o chat de grupo, o Office Communications Server 2007 R2 Group Chat ou o Lync Server 2013, serviços do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bd958-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="bd958-148">Todos os serviços devem ser interrompidos, portanto, planeje isso de cada vez, quando houver tempo de inatividade suficiente.</span><span class="sxs-lookup"><span data-stu-id="bd958-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="bd958-149">Conforme descrito anteriormente, certifique-se de fazer backup do banco de dados de chat de grupo atual.</span><span class="sxs-lookup"><span data-stu-id="bd958-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="bd958-150">Execute o cmdlet **Export-CsPersistentChatData** do Windows PowerShell como membro da função RBAC do administrador de chat persistente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="bd958-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="bd958-151">Para obter detalhes sobre os cmdlets Export/Import, consulte [Solucionando problemas de configuração do servidor de chat persistente usando cmdlets do Windows PowerShell no Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="bd958-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="bd958-152">Inspecione o conteúdo exportado.</span><span class="sxs-lookup"><span data-stu-id="bd958-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="bd958-153">Antes de estar pronto para importar, desative o Lync Server 2013, serviços do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bd958-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="bd958-154">Todos os serviços precisam ser interrompidos, portanto, planeje isso por vez, quando houver tempo de inatividade suficiente.</span><span class="sxs-lookup"><span data-stu-id="bd958-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="bd958-155">Execute um backup do banco de dados de chat persistente se você tiver criado quaisquer categorias, salas ou suplementos na sua implantação do Lync Server 2013 antes da migração.</span><span class="sxs-lookup"><span data-stu-id="bd958-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="bd958-156">O processo de exportação/importação será capaz de mesclar os dados herdados na implantação do Lync Server 2013, mas você desejará fazer o backup do banco de dados caso o conteúdo seja substituído inadvertidamente (por exemplo, se ainda existirem conflitos de nomenclatura).</span><span class="sxs-lookup"><span data-stu-id="bd958-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="bd958-157">Execute o cmdlet **Import-CsPersistentChatData** do Windows PowerShell (ferramenta de importação), com um comando **WhatIf** para preencher o servidor back-end do pool do servidor de chat persistente com os dados migrados.</span><span class="sxs-lookup"><span data-stu-id="bd958-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="bd958-158">Algumas conversões acontecem no processo para acomodar o modelo de administração simplificado.</span><span class="sxs-lookup"><span data-stu-id="bd958-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="bd958-159">Correção de erros ou avisos exibidos.</span><span class="sxs-lookup"><span data-stu-id="bd958-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="bd958-160">Execute o servidor de chat persistente do Windows PowerShell **Import-CsPersistentChatData** cmdlet como um membro da função RBAC do administrador de chat persistente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="bd958-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="bd958-161">Para obter detalhes sobre os cmdlets Export/Import, consulte [Solucionando problemas de configuração do servidor de chat persistente usando cmdlets do Windows PowerShell no Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="bd958-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="bd958-162">Você deve XCOPY todos os arquivos carregados (a pasta inteira) para o novo repositório de arquivos de chat persistente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd958-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd958-163">O Lync 2013 (cliente) não suporta carregar ou exibir arquivos em salas de chat.</span><span class="sxs-lookup"><span data-stu-id="bd958-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="bd958-164">Você ainda pode usar o cliente herdado para postar e exibir arquivos na sala.</span><span class="sxs-lookup"><span data-stu-id="bd958-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="bd958-165">Port o Lync Server 2010, o chat de grupo ou o URI do servidor de pesquisa de chat do grupo do Office Communications Server 2007 R2 para o Lync Server 2013, o objeto de contato do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bd958-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="bd958-166">As etapas a seguir são necessárias se seus clientes de chat de grupo do Lync 2010 ou do Office Communicator 2007 R2 precisarem se conectar ao Lync 2013, persistente chat (cliente) mais recente após a migração sem qualquer alteração de configuração do lado do cliente:</span><span class="sxs-lookup"><span data-stu-id="bd958-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="bd958-167">Exclua a \<domainName\> conta de usuário do servidor de pesquisa do OCSChat@. com.</span><span class="sxs-lookup"><span data-stu-id="bd958-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="bd958-168">Isso foi usado para apontar para o serviço de pesquisa no Lync Server 2010, chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="bd958-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="bd958-169">Você pode desinstalar o pool e remover as entradas confiáveis mais tarde.</span><span class="sxs-lookup"><span data-stu-id="bd958-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="bd958-170">Crie um ponto de extremidade herdado (objeto de contato do servidor de chat persistente) executando o cmdlet do Windows PowerShell, **New-CsPersistentChatEndpoint**, com o URI SIP idêntico para que o cliente herdado funcione efetivamente quando o serviço for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="bd958-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="bd958-171">O processo de migração obrigatório está completo neste ponto.</span><span class="sxs-lookup"><span data-stu-id="bd958-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="bd958-172">Lync 2010 Group Chat (clientes) ou Office Communicator 2007 R2 Group Chat (clientes) podem se conectar ao novo pool de servidor de chat persistente agora, de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="bd958-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="bd958-173">Siga estas etapas adicionais de descomissionamento para o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="bd958-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="bd958-174">Inicie os serviços do servidor de chat persistente, ativando todos os computadores no novo pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bd958-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="bd958-175">Use o painel de controle do Lync Server e os cmdlets do Windows PowerShell para verificar se os dados foram migrados com êxito.</span><span class="sxs-lookup"><span data-stu-id="bd958-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="bd958-176">Desinstalar o Lync 2010 Group Chat ou o chat de grupo do Office Communicator 2007 R2 dos computadores no pool do servidor de chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="bd958-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="bd958-177">Exclua o aplicativo confiável e o pool de aplicativos confiáveis usando os cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd958-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="bd958-178">Isso exclui esses itens do repositório de gerenciamento central e das entradas de serviço confiáveis (TSEs) associadas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bd958-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="bd958-179">Como alternativa, essa etapa funciona usando o construtor de topologias (os aplicativos/pools confiáveis têm um nó dedicado, também).</span><span class="sxs-lookup"><span data-stu-id="bd958-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="bd958-180">Agora você pode começar a habilitar a funcionalidade do servidor de chat persistente através dos novos clientes.</span><span class="sxs-lookup"><span data-stu-id="bd958-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="bd958-181">Para obter detalhes sobre como habilitar o servidor de chat persistente, consulte [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd958-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd958-182">O Lync Server 2013 oferece suporte a vários pools de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bd958-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="bd958-183">No entanto, damos suporte à migração de um chat de grupo do Lync 2010 ou do pool de chat de grupo do Office Communications Server 2007 R2 &nbsp; para um único servidor Lync server 2013, persistente pool do servidor de chat.</span><span class="sxs-lookup"><span data-stu-id="bd958-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="bd958-184">Você pode adicionar novos pools de servidores de chat persistentes à sua implantação para atender às necessidades normativas (por exemplo, manter dados dentro de uma determinada Geografia).</span><span class="sxs-lookup"><span data-stu-id="bd958-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

