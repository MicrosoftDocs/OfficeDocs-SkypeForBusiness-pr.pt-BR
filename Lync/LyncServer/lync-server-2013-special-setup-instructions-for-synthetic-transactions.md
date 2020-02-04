---
title: 'Lync Server 2013: instruções de configuração especiais para transações sintéticas'
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
ms.openlocfilehash: a15177a3c4548b235bf01a10274168e4a830fad3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="bd83c-102">Instruções de configuração especiais para transações sintéticas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd83c-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd83c-103">_**Tópico da última modificação:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="bd83c-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="bd83c-104">A maioria das transações sintéticas pode ser executada em um nó de Inspetor como está; ou seja, assim que a transação sintética tiver sido adicionada às configurações do nó do Inspetor, o nó do Inspetor poderá começar a usar a transação sintética durante o teste.</span><span class="sxs-lookup"><span data-stu-id="bd83c-104">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes.</span></span> <span data-ttu-id="bd83c-105">No entanto, isso não é verdade para todas as transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="bd83c-105">However, this is not true for all synthetic transactions.</span></span> <span data-ttu-id="bd83c-106">As exceções – transações sintéticas que exigem instruções de configuração especiais – são discutidas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="bd83c-106">The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="bd83c-107">Lidando com erros de tempo limite do servidor</span><span class="sxs-lookup"><span data-stu-id="bd83c-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="bd83c-108">Em alguns casos, você pode descobrir que suas transações sintéticas estão falhando com erros de tempo limite do servidor (código de erro 504).</span><span class="sxs-lookup"><span data-stu-id="bd83c-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="bd83c-109">Esses erros costumam ocorrer devido a problemas de firewall.</span><span class="sxs-lookup"><span data-stu-id="bd83c-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="bd83c-110">Quando uma transação sintética é executada, essa transação é executada no processo MonitoringHost. exe; por sua vez, o MonitoringHost. exe inicia uma instância do processo PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="bd83c-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="bd83c-111">Se o MonitoringHost. exe ou o PowerShell. exe estiverem bloqueados pelo seu firewall, a transação sintética falhará e gerará um erro do 504.</span><span class="sxs-lookup"><span data-stu-id="bd83c-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="bd83c-112">Para solucionar esse problema, você deve criar manualmente regras de firewall de entrada para MonitoringHost. exe e PowerShell. exe no computador local.</span><span class="sxs-lookup"><span data-stu-id="bd83c-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="bd83c-113">Isso pode ser feito pelo firewall do Windows ou por um software de firewall local de terceiros, dependendo da configuração pré-existente do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="bd83c-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="bd83c-114">Se você estiver empregando um dispositivo de firewall de rede entre a máquina de host de transação sintética e os servidores do Lync que está tentando monitorar, deve tratar o host como uma máquina cliente e usar o observador de todos os requisitos de porta do firewall de [portas e protocolos para servidores internos no Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="bd83c-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="bd83c-115">Transações sintéticas de conferência de dados</span><span class="sxs-lookup"><span data-stu-id="bd83c-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="bd83c-116">Se o seu computador do nó do observador estiver localizado fora de sua rede de perímetro, provavelmente não será possível executar a transação sintética de data Conferencing, a menos que você primeiro desabilite as configurações de proxy do Internet Explorer para a conta de serviço de rede.</span><span class="sxs-lookup"><span data-stu-id="bd83c-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="bd83c-117">Para desativar as configurações de proxy para esse serviço, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="bd83c-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="bd83c-118">No computador do nó do Inspetor, clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="bd83c-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="bd83c-119">Na janela do console, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="bd83c-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="bd83c-120">A seguinte mensagem aparecerá na janela de comando:</span><span class="sxs-lookup"><span data-stu-id="bd83c-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="bd83c-121">Essa mensagem significa que você desabilitou as configurações de proxy do Internet Explorer para a conta de serviço de rede.</span><span class="sxs-lookup"><span data-stu-id="bd83c-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="bd83c-122">Transações sintéticas da Unificação de mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="bd83c-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="bd83c-123">A transação sintética de Unificação de Mensagens do Exchange verifica se usuários de teste podem se conectar a contas de correio de voz hospedadas no Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd83c-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="bd83c-124">Esses usuários de teste precisarão ser pré-configurados com contas de correio de voz antes de poderem usar os testes de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd83c-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="bd83c-125">Transações sintéticas de chat persistente</span><span class="sxs-lookup"><span data-stu-id="bd83c-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="bd83c-126">Para usar a transação de chat sintética persistente, os administradores devem primeiro criar um canal e conceder permissões aos usuários de teste para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="bd83c-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="bd83c-127">O cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) pode ser usado para configurar corretamente esses usuários de teste:</span><span class="sxs-lookup"><span data-stu-id="bd83c-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="bd83c-128">Esta tarefa de configuração deve ser executada dentro da empresa:</span><span class="sxs-lookup"><span data-stu-id="bd83c-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="bd83c-129">Se executado de um computador que não seja do servidor, o usuário que executa o cmdlet deve ser um membro da função PersistentChatAdministrators para o controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="bd83c-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="bd83c-130">Se executado do próprio servidor, o usuário que executa o cmdlet deve ser um membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bd83c-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="bd83c-131">No comando anterior, o parâmetro setup foi incluído e definido como true ($True).</span><span class="sxs-lookup"><span data-stu-id="bd83c-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="bd83c-132">Se você incluir o parâmetro setup, Test-CsPersistentChatMessage criará uma sala de chat persistente especial e preencherá essa sala com os usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="bd83c-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="bd83c-133">Isso ajuda a garantir que, na verdade, não há uma sala de chat disponível para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="bd83c-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="bd83c-134">Observe que o parâmetro setup só deve ser executado em um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="bd83c-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="bd83c-135">A sala de chat criada por Test-CsPersistentChatMessage pode ser excluída somente por um administrador.</span><span class="sxs-lookup"><span data-stu-id="bd83c-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="bd83c-136">Transações sintéticas de chamada ponto a ponto PSTN</span><span class="sxs-lookup"><span data-stu-id="bd83c-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="bd83c-137">A transação sintética [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) verifica a capacidade de colocar e receber chamadas por meio da rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="bd83c-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="bd83c-138">Para executar essa transação sintética, os administradores devem configurar:</span><span class="sxs-lookup"><span data-stu-id="bd83c-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="bd83c-139">Dois usuários de teste (um chamador e um receptor) habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bd83c-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="bd83c-140">Números DID (Discagem Interna Direta) para cada conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="bd83c-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="bd83c-141">Políticas de voz e rotas de voz que permitem que as chamadas para o número do destinatário atinjam o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="bd83c-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="bd83c-142">Um gateway PSTN que aceita chamadas e mídia que roteia chamadas para o pool inicial de um receptor com base no número discado.</span><span class="sxs-lookup"><span data-stu-id="bd83c-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="bd83c-143">Transações sintéticas de repositório de contatos unificado</span><span class="sxs-lookup"><span data-stu-id="bd83c-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="bd83c-144">A transação sintética do repositório de contatos unificado verifica se o Lync Server 2013 é capaz de recuperar contatos em nome de um usuário do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd83c-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="bd83c-145">Para usar essa transação sintética, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="bd83c-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="bd83c-146">[Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) deve ser configurado entre o lync Server 2013 e o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="bd83c-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="bd83c-147">Os usuários de teste devem ter uma caixa de correio válida do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="bd83c-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="bd83c-148">Depois que essas condições forem atendidas, os administradores poderão executar o seguinte comando para verificar se o usuário com o endereço SIP kenmyer@litwareinc.com pode recuperar seus contatos do repositório de contatos unificado:</span><span class="sxs-lookup"><span data-stu-id="bd83c-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="bd83c-149">Observe o uso do parâmetro setup usado no comando anterior.</span><span class="sxs-lookup"><span data-stu-id="bd83c-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="bd83c-150">Se o parâmetro setup estiver incluído ao executar Test-CsUnifiedContactStore, os contatos do usuário especificado (neste caso, sip:kenmyer@litwareinc.com) serão movidos para o repositório de contatos unificado.</span><span class="sxs-lookup"><span data-stu-id="bd83c-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="bd83c-151">(Naturalmente, se os contatos do usuário já estiverem no repositório de contatos unificado, eles não precisam ser movidos.) O parâmetro setup geralmente é usado apenas uma vez (a primeira vez que o CsUnifiedContactStore é executado) e só deve ser usado com usuários de teste; ou seja, com contas de usuário que nunca serão realmente conectadas ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd83c-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="bd83c-152">Após o usuário do teste ter sido migrado para o repositório de contatos unificado, você pode verificar se os contatos do usuário podem ser recuperados chamando Test-CsUnifiedContactStore sem o parâmetro setup:</span><span class="sxs-lookup"><span data-stu-id="bd83c-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="bd83c-153">Transações sintéticas XMPP</span><span class="sxs-lookup"><span data-stu-id="bd83c-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="bd83c-154">A transação sintética de mensagem de chat XMPP (Extensible Messaging and Presence Protocol) requer que o recurso XMPP seja configurado com um ou mais domínios federados.</span><span class="sxs-lookup"><span data-stu-id="bd83c-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="bd83c-155">Para habilitar a transação sintética XMPP, um parâmetro XmppTestReceiverMailAddress deve ser fornecido com uma conta de usuário em um domínio de XMPP roteável.</span><span class="sxs-lookup"><span data-stu-id="bd83c-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="bd83c-156">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bd83c-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="bd83c-157">Neste exemplo, será preciso existir uma regra do Lync Server 2013 para direcionar as mensagens para o litwareinc.com para um Gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="bd83c-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

