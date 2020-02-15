---
title: Executar compatibilidade com versões anteriores para servidor de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 329415e7bae43bbbfd3a77da39e99049f4fe617e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="98a50-102">Executar compatibilidade com versões anteriores para servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="98a50-102">Run backward compatibility for Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98a50-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="98a50-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="98a50-104">O ponto de extremidade do Lync Server 2013, do servidor de chat persistente oferece uma maneira de criar uma URL simples que aponta para um pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98a50-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="98a50-105">Isso é útil para clientes herdados (Microsoft Office Communications Server 2007 R2 Group Chat Server ou Lync Server 2010, chat de grupo) porque os usuários podem inserir uma URL simples na configuração manual ao tentar apontar o cliente herdado para um computador que executa o Lync 2013, Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98a50-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="98a50-106">Este ponto de extremidade não é usado pelo chat persistente e é necessário somente para clientes herdados.</span><span class="sxs-lookup"><span data-stu-id="98a50-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="98a50-107">Isso é útil para o período provisório onde as salas podem ser migradas, mas os clientes do Lync 2013 não foram implantados em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="98a50-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="98a50-108">Os usuários que executam o Lync 2010 Group Chat (cliente) ainda podem se conectar ao servidor back-end do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98a50-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="98a50-109">Você não precisa criar vários pontos de extremidade do servidor de chat persistente; Você só precisa de um para cada pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98a50-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="98a50-110">Os administradores podem criar vários pontos de extremidade (um por pool), mas os clientes herdados podem estar configurados para conectar-se somente a um pool por vez.</span><span class="sxs-lookup"><span data-stu-id="98a50-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="98a50-111">No cenário habitual ou importante, a implantação herdade é somente um pool.</span><span class="sxs-lookup"><span data-stu-id="98a50-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="98a50-112">Uma nova implantação geralmente migra esse pool para um novo Lync Server 2013 e pode adicionar alguns novos pools de servidores de chat persistentes adicionais.</span><span class="sxs-lookup"><span data-stu-id="98a50-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="98a50-113">Esse cenário indispensável, geralmente, segue esse padrão:</span><span class="sxs-lookup"><span data-stu-id="98a50-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="98a50-114">Você administra usuários com um Lync Server 2010, pool de chat de grupo e seus clientes de chat de grupo do Lync 2010 se conectam a esse pool usando alguns usuários conhecidos (SIP padrão\<: OCSChat@ DomainName\>. com ou semelhante a um).</span><span class="sxs-lookup"><span data-stu-id="98a50-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="98a50-115">Os usuários são serviços de domínio do Active Directory habilitados para SIP e o serviço de pesquisa registra com eles para receber solicitações de entrada.</span><span class="sxs-lookup"><span data-stu-id="98a50-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="98a50-116">Em seguida, você instala um servidor de chat persistente do Lync Server 2013 e um pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98a50-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="98a50-117">Durante um período no qual os usuários, geralmente, estão offline (por exemplo, um fim de semana):</span><span class="sxs-lookup"><span data-stu-id="98a50-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="98a50-118">Desative o Lync Server 2010, chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="98a50-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="98a50-119">Migre dados do Lync Server 2010, pool de chat de grupo para o pool do servidor de chat persistente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98a50-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="98a50-120">Exclua o usuário conhecido dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98a50-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="98a50-121">Crie um novo *ponto de extremidade herdado* com o mesmo URI do SIP do usuário conhecido excluído anteriormente.</span><span class="sxs-lookup"><span data-stu-id="98a50-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="98a50-122">Inicie os servidores de chat persistente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98a50-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="98a50-123">Os usuários fazem logon novamente usando seu chat de grupo do Lync 2010 (cliente) e se conectam aos seus dados sem precisar alterar nenhuma configuração.</span><span class="sxs-lookup"><span data-stu-id="98a50-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="98a50-124">Mais tarde, você pode encerrar o Lync Server 2010, o chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="98a50-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="98a50-125">Subsequentemente, você pode implantar o Lync Server 2013, o servidor de chat persistente e instalar novos pools do servidor de chat persistente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98a50-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="98a50-126">Para obter detalhes sobre como migrar do Lync Server 2010, o chat de grupo para o Lync Server 2013, servidor de chat persistente, consulte [migração do Lync server 2010, chat de grupo ou Office Communications Server 2007 R2 Group Chat to Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="98a50-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="98a50-127">Para executar a compatibilidade com versões anteriores (para criar um ponto de extremidade de servidor de chat persistente que aponta para um pool de servidor de chat persistente, que pode ser usado por clientes do pool de chat de grupo herdado):</span><span class="sxs-lookup"><span data-stu-id="98a50-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="98a50-128">Em seguida, configure os clientes de chat persistente para usar esse endereço SIP como objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="98a50-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="98a50-129">O endereço SIP é criado com o cmdlet **New-CsPersistentChatEndpoint** para um pool de servidor de chat persistente específico.</span><span class="sxs-lookup"><span data-stu-id="98a50-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="98a50-130">Para adicionar o ponto de extremidade do servidor de chat persistente usando a interface de linha de comando do Windows PowerShell, considere o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="98a50-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="98a50-131">Neste caso, você está configurando o  objeto de contato para ser chamado de "persistentchat" na topologia "contoso.com", no qual o nome de domínio totalmente qualificado (FQDN) do pool é "pcpool.contoso.com":</span><span class="sxs-lookup"><span data-stu-id="98a50-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="98a50-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="98a50-132">See Also</span></span>


[<span data-ttu-id="98a50-133">Migração do Lync Server 2010, Chat em Grupo ou Office Communications Server 2007 R2 Group Chat para Lync Server 2013, Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="98a50-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

