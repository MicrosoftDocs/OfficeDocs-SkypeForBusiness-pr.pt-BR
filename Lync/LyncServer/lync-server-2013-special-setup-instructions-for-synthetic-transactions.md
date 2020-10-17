---
title: 'Lync Server 2013: instruções de configuração especiais para transações sintéticas'
description: 'Lync Server 2013: instruções de configuração especiais para transações sintéticas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e288a9d7f15f4b84df591d152a912509c77129a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551317"
---
# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="95a0d-103">Instruções especiais de configuração para transações sintéticas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a0d-103">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95a0d-104">_**Última modificação do tópico:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="95a0d-104">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="95a0d-p101">A maioria das transações sintéticas pode ser executada em um nó do inspetor no estado em que se encontram, ou seja, assim que uma transação sintética é adicionada às configurações do nó do inspetor, ele pode começar a usá-la durante as fases de teste. No entanto, isso não ocorre para todas as transações sintéticas. As exceções (transações que exigem instruções de configuração especiais) são abordadas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="95a0d-p101">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes. However, this is not true for all synthetic transactions. The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="95a0d-108">Lidando com erros de tempo limite do servidor</span><span class="sxs-lookup"><span data-stu-id="95a0d-108">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="95a0d-109">Em alguns casos, você pode descobrir que suas transações sintéticas estão falhando com erros de tempo limite do servidor (código de erro 504).</span><span class="sxs-lookup"><span data-stu-id="95a0d-109">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="95a0d-110">Esses erros costumam ocorrer devido a problemas de firewall.</span><span class="sxs-lookup"><span data-stu-id="95a0d-110">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="95a0d-111">Quando uma transação sintética é executada, essa transação é executada no processo de MonitoringHost.exe; por sua vez, MonitoringHost.exe inicia uma instância do processo de PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="95a0d-111">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="95a0d-112">Se MonitoringHost.exe ou PowerShell.exe for bloqueado pelo firewall, a transação sintética falhará e gerará um erro 504.</span><span class="sxs-lookup"><span data-stu-id="95a0d-112">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="95a0d-113">Para resolver esse problema, você deve criar manualmente regras de firewall de entrada para MonitoringHost.exe e PowerShell.exe na máquina local.</span><span class="sxs-lookup"><span data-stu-id="95a0d-113">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="95a0d-114">Isso pode ser feito por meio do firewall do Windows ou de um software de firewall local de terceiros, dependendo da configuração preexistente do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="95a0d-114">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="95a0d-115">Se você estiver usando um dispositivo de firewall de rede entre a máquina de host de transação sintética e os servidores Lync que você está tentando monitorar, você deve tratar o host como uma máquina cliente e o observador de todos os requisitos de porta de firewall de [portas e protocolos para servidores internos no Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="95a0d-115">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="95a0d-116">Transações sintéticas de conferência de dados</span><span class="sxs-lookup"><span data-stu-id="95a0d-116">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="95a0d-117">Se o computador do nó do observador estiver localizado fora da rede de perímetro, provavelmente você não poderá executar a transação sintética de audioconferência, a menos que primeiro desabilite as configurações de proxy do Internet Explorer para a conta de serviço de rede.</span><span class="sxs-lookup"><span data-stu-id="95a0d-117">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="95a0d-118">Para desabilitar as configurações de proxy para esse serviço, execute o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="95a0d-118">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="95a0d-119">No computador do nó do observador, clique em **Iniciar**, em **Todos os programas**, em **Acessórios**, clique com o botão direito no **Prompt de comando** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="95a0d-119">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="95a0d-120">Na janela do console, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="95a0d-120">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="95a0d-121">A seguinte mensagem será exibida na janela de comando:</span><span class="sxs-lookup"><span data-stu-id="95a0d-121">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="95a0d-122">Essa mensagem significa que você desabilitou as configurações de proxy do Internet Explorer para a conta de serviço de rede.</span><span class="sxs-lookup"><span data-stu-id="95a0d-122">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="95a0d-123">Transações sintéticas de Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="95a0d-123">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="95a0d-124">A transação sintética de Unificação de mensagens (UM) do Exchange verifica se os usuários de teste podem se conectar às contas de caixa postal hospedadas no Exchange.</span><span class="sxs-lookup"><span data-stu-id="95a0d-124">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="95a0d-125">Esses usuários de teste precisarão ser pré-configurados com contas de caixa postal para poderem usar os testes de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="95a0d-125">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="95a0d-126">Transações sintéticas de chat persistente</span><span class="sxs-lookup"><span data-stu-id="95a0d-126">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="95a0d-127">Para usar a transação sintética de chat persistente, os administradores devem primeiro criar um canal e conceder permissões aos usuários de teste para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="95a0d-127">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="95a0d-128">O cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) pode ser usado para configurar corretamente os usuários de teste:</span><span class="sxs-lookup"><span data-stu-id="95a0d-128">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="95a0d-129">Esta tarefa de configuração deve ser realizada de dentro da empresa:</span><span class="sxs-lookup"><span data-stu-id="95a0d-129">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="95a0d-130">Se ela for realizada de uma máquina que não é um servidor, o usuário que executar o cmdlet deverá ser um membro da função PersistentChatAdministrators do RBAC (Controle de Acesso Baseado em Função).</span><span class="sxs-lookup"><span data-stu-id="95a0d-130">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="95a0d-131">Se ela for realizada a partir do próprio servidor, o usuário que executar o cmdlet deverá ser um membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="95a0d-131">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="95a0d-132">No comando anterior, o parâmetro Setup foi incluído e definido como True ($True).</span><span class="sxs-lookup"><span data-stu-id="95a0d-132">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="95a0d-133">Se você incluir o parâmetro setup, Test-CsPersistentChatMessage criará uma sala de chat persistente especial e preencherá essa sala com os usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="95a0d-133">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="95a0d-134">Isso ajudará a garantir que haja uma sala de chat real disponível para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="95a0d-134">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="95a0d-135">Observe que o parâmetro Setup deve ser executado apenas de um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="95a0d-135">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="95a0d-136">A sala de chat criada por Test-CsPersistentChatMessage só pode ser excluída por um administrador.</span><span class="sxs-lookup"><span data-stu-id="95a0d-136">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="95a0d-137">Transações sintéticas de chamada ponto a ponto PSTN</span><span class="sxs-lookup"><span data-stu-id="95a0d-137">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="95a0d-138">A transação sintética [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) verifica a capacidade de colocar e receber chamadas através da rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="95a0d-138">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="95a0d-139">Para executar essa transação sintética, os administradores devem configurar:</span><span class="sxs-lookup"><span data-stu-id="95a0d-139">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="95a0d-140">Dois usuários de teste (um chamador e um receptor) habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="95a0d-140">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="95a0d-141">Números DID (Discagem Interna Direta) para cada conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="95a0d-141">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="95a0d-142">Políticas e rotas de voz que permitem que chamadas para o número do receptor cheguem ao gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="95a0d-142">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="95a0d-143">Um gateway PSTN que aceita chamadas e mídia que encaminha os retornos de chamada para o pool primário de um receptor com base no número discado.</span><span class="sxs-lookup"><span data-stu-id="95a0d-143">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="95a0d-144">Transações sintéticas do repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="95a0d-144">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="95a0d-145">A transação sintética do repositório unificado de contatos verifica se o Lync Server 2013 pode recuperar contatos em nome de um usuário do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="95a0d-145">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="95a0d-146">Para usar essa transação sintética, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="95a0d-146">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="95a0d-147">[Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) deve ser configurado entre o lync Server 2013 e o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="95a0d-147">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="95a0d-148">Os usuários de teste devem ter uma caixa de correio do Exchange 2013 válida.</span><span class="sxs-lookup"><span data-stu-id="95a0d-148">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="95a0d-149">Depois que essas condições forem atendidas, os administradores poderão executar o seguinte comando para verificar se o usuário com o endereço SIP kenmyer@litwareinc.com pode recuperar seus contatos do repositório unificado de contatos:</span><span class="sxs-lookup"><span data-stu-id="95a0d-149">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="95a0d-150">Observe o uso do parâmetro setup usado no comando anterior.</span><span class="sxs-lookup"><span data-stu-id="95a0d-150">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="95a0d-151">Se o parâmetro setup estiver incluído ao executar Test-CsUnifiedContactStore, os contatos do usuário especificado (neste caso, sip:kenmyer@litwareinc.com) serão movidos para o repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="95a0d-151">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="95a0d-152">(Obviamente, se os contatos do usuário já estiverem no repositório unificado de contatos, eles não precisarão ser movidos.) Normalmente, o parâmetro Setup é usado apenas uma vez (a primeira vez que o Test-CsUnifiedContactStore é executado) e só deve ser usado com usuários de teste; ou seja, com contas de usuário que nunca serão realmente conectadas ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95a0d-152">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="95a0d-153">Após o usuário de teste ter sido migrado para o repositório unificado de contatos, você pode verificar se os contatos do usuário podem ser recuperados chamando Test-CsUnifiedContactStore sem o parâmetro setup:</span><span class="sxs-lookup"><span data-stu-id="95a0d-153">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="95a0d-154">Transações sintéticas XMPP</span><span class="sxs-lookup"><span data-stu-id="95a0d-154">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="95a0d-155">A transação sintética de IM do protocolo XMPP exige que o recurso XMPP seja configurado com um ou mais domínios federados.</span><span class="sxs-lookup"><span data-stu-id="95a0d-155">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="95a0d-156">Para habilitar a transação sintética XMPP, um parâmetro XmppTestReceiverMailAddress deve ser fornecido com uma conta de usuário em um domínio XMPP roteável.</span><span class="sxs-lookup"><span data-stu-id="95a0d-156">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="95a0d-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="95a0d-157">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="95a0d-158">Neste exemplo, uma regra do Lync Server 2013 precisará existir para rotear mensagens para o litwareinc.com para um Gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="95a0d-158">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

