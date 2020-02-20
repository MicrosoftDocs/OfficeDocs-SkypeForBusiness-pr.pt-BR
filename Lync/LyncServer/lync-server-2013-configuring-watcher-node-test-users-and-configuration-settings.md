---
title: Configurando os usuários de teste do nó do Inspetor e definições de configuração
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d66eb347fbd26f2d50828924d41075680fdcc09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4dfd3-102">Configurando os usuários de teste do nó do Inspetor e definições de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dfd3-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dfd3-103">_**Última modificação do tópico:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="4dfd3-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="4dfd3-104">Depois de configurar o computador que atuará como um nó do inspetor, você deve:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="4dfd3-105">Criar as contas de teste que serão usadas por esses nós de inspetor.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="4dfd3-106">Se estiver usando o método de autenticação Negociar, você também deve usar o cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) para permitir o uso dessas contas de teste no nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="4dfd3-107">Atualizar as definições de configuração do nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="4dfd3-108">Esta seção cobre:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-108">This section covers:</span></span>

  - <span data-ttu-id="4dfd3-109">Configurando contas de usuário de teste</span><span class="sxs-lookup"><span data-stu-id="4dfd3-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="4dfd3-110">Configurando uma Nó do inspetor básico com as Transações sintéticas padrão</span><span class="sxs-lookup"><span data-stu-id="4dfd3-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="4dfd3-111">Configurando Testes estendidos</span><span class="sxs-lookup"><span data-stu-id="4dfd3-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="4dfd3-112">Adicionando e removendo Transações sintéticas</span><span class="sxs-lookup"><span data-stu-id="4dfd3-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="4dfd3-113">Exibindo e testando a configuração do nó inspetor</span><span class="sxs-lookup"><span data-stu-id="4dfd3-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="4dfd3-114">Configurando contas de usuário de teste</span><span class="sxs-lookup"><span data-stu-id="4dfd3-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="4dfd3-115">Os usuários de teste não precisam representar pessoas reais, mas devem ser contas válidas dos serviços de domínio do Active Directory; Além disso, essas contas devem ser habilitadas para o Lync Server 2013, elas devem ter endereços SIP válidos e devem ser habilitadas para o Enterprise Voice (para usar a transação sintética test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="4dfd3-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="4dfd3-116">Se você usar o método de autenticação TrustedServer, então será necessário certificar-se de que essas contas existem e foram configuradas como especificado aqui.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="4dfd3-117">É necessário atribuir pelo menos três usuários de teste a cada pool que deseja testar.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="4dfd3-118">Se você estiver usando o método de autenticação Negotiate, você também deve usar o cmdlet **set-CsTestUserCredential** e o Shell de gerenciamento do Lync Server para permitir que essas contas de teste funcionem com as transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="4dfd3-119">Isso pode ser feito executando um comando semelhante a este.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="4dfd3-120">(Estes comandos presumem que as três contas de usuário do Active Directory já tenham sido criadas e que essas contas tenham sido habilitadas para o Lync Server 2013.):</span><span class="sxs-lookup"><span data-stu-id="4dfd3-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="4dfd3-121">Observe que é necessário incluir não apenas o endereço SIP, mas também o nome e a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="4dfd3-122">Se não incluir a senha, Set-CsTestUserCredential solicitará que você insira essas informações.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="4dfd3-123">O nome de usuário pode ser especificado usando o formato\\nome de usuário do nome de domínio mostrado acima ou usando o nome de usuário do formato name@domain; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="4dfd3-124">Para verificar se as credenciais do usuário de teste foram criadas, execute estes comandos de dentro do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="4dfd3-125">Informações semelhantes a estas devem ser retornadas para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="4dfd3-126">Configurando uma Nó do inspetor básico com as Transações sintéticas padrão</span><span class="sxs-lookup"><span data-stu-id="4dfd3-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="4dfd3-127">Depois que os usuários de teste são criados, você pode criar um nó do inspetor usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="4dfd3-128">Esse comando cria um novo nó do inspetor que usa as configurações padrão e executa o conjunto padrão de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="4dfd3-129">O novo nó do inspetor também usa watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com dos usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="4dfd3-130">Se o nó do Inspetor estiver usando a autenticação do TrustedServer, as três contas de teste poderão ser todas as contas de usuário válidas habilitadas para o Active Directory e o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="4dfd3-131">Se o nó do inspetor está usando o método de autenticação Negociar, você também deve ativar essas contas do usuário para o nó do inspetor usando o cmdlet **Set-CsTestUserCredential**.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="4dfd3-132">Configurando testes estendidos</span><span class="sxs-lookup"><span data-stu-id="4dfd3-132">Configuring Extended Tests</span></span>

<span data-ttu-id="4dfd3-133">Se você desejar ativar a rede telefônica pública comutada (teste da PSTN), que verifica a conectividade com a rede telefônica comutada, será necessário efetuar configurações adicionais ao configurar o nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="4dfd3-134">Primeiro, é necessário associar seus usuários de teste ao tipo de teste da PSTN.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="4dfd3-135">Para fazer isso, execute um comando semelhante a este no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="4dfd3-136">Observe que os resultados desse comando devem ser armazenados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="4dfd3-137">Neste exemplo, é uma variável chamada de $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="4dfd3-138">Neste ponto, você pode usar o cmdlet **New-CsWatcherNodeConfiguration** para associar o tipo de teste (armazenado na variável $pstnTest) a um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="4dfd3-139">Por exemplo, o seguinte comando cria uma nova configuração de nó do inspetor para o pool atl-cs-001.litwareinc.com, adicionando os três usuários de teste que foram criados anteriormente e também adicionando o tipo de teste de PSTN:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="4dfd3-140">Observe que o comando anterior falhará se você não tiver instalado os arquivos principais do Lync Server e o banco de dados RTCLocal no computador do nó do observador.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="4dfd3-141">Para testar várias políticas de voz, é necessário criar um teste estendido para cada política usando o cmdlet **New-CsExtendedTest**.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="4dfd3-142">Os usuários atribuídos ao teste devem ser configurados com as políticas de voz desejadas.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="4dfd3-143">Os testes estendidos são passados para o cmdlet **New-CsWatcherNodeConfiguration** usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="4dfd3-p110">Se New-CsWatcherNodeConfiguration é chamado sem usar o parâmetro Testes, isso significa que somente as transações sintéticas Padrão (e a transação sintética estendida especificada) serão ativadas no novo nó do inspetor. Isso significa que o nó do inspetor testará os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-p110">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="4dfd3-146">Registro</span><span class="sxs-lookup"><span data-stu-id="4dfd3-146">Registration</span></span>

  - <span data-ttu-id="4dfd3-147">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="4dfd3-147">IM</span></span>

  - <span data-ttu-id="4dfd3-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="4dfd3-148">GroupIM</span></span>

  - <span data-ttu-id="4dfd3-149">P2PAV (sessões de áudio/vídeo ponto a ponto)</span><span class="sxs-lookup"><span data-stu-id="4dfd3-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="4dfd3-150">AvConference (áudio/conferência)</span><span class="sxs-lookup"><span data-stu-id="4dfd3-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="4dfd3-151">Presença</span><span class="sxs-lookup"><span data-stu-id="4dfd3-151">Presence</span></span>

  - <span data-ttu-id="4dfd3-152">ABS (serviço do Catálogo de Endereços)</span><span class="sxs-lookup"><span data-stu-id="4dfd3-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="4dfd3-153">ABWQ (serviço Web do Catálogo de Endereços)</span><span class="sxs-lookup"><span data-stu-id="4dfd3-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="4dfd3-p111">PSTN (chamadas de gateway PSTN, especificadas como um teste estendido. Por padrão, a PSTN está desativada. O teste está ativado somente nesse caso, pois o comando ativou a PSTN usando o parâmetro ExtendedTests).</span><span class="sxs-lookup"><span data-stu-id="4dfd3-p111">PSTN (PSTN gateway calls, specified as an extended test. By default, PSTN is disabled. The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="4dfd3-157">Isso também significa que os seguintes componentes não serão testados por padrão:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="4dfd3-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="4dfd3-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="4dfd3-159">MCXP2PIM (mensagens instantâneas de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="4dfd3-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="4dfd3-160">ExumConnectivity (Unificação de Mensagens do Exchange)</span><span class="sxs-lookup"><span data-stu-id="4dfd3-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="4dfd3-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="4dfd3-161">JoinLauncher</span></span>

  - <span data-ttu-id="4dfd3-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="4dfd3-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="4dfd3-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="4dfd3-163">DataConference</span></span>

  - <span data-ttu-id="4dfd3-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="4dfd3-164">XmppIM</span></span>

  - <span data-ttu-id="4dfd3-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="4dfd3-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="4dfd3-166">Adicionando e removendo Transações sintéticas</span><span class="sxs-lookup"><span data-stu-id="4dfd3-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="4dfd3-167">Depois que um nó do inspetor é configurado, é possível usar o cmdlet **Set-CsWatcherNodeConfiguration** para adicionar ou remover transações sintéticas do nó.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="4dfd3-168">Por exemplo, para adicionar o teste PersistentChatMessage ao nó do inspetor, use o método Adicionar e um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="4dfd3-p113">É possível adicionar vários testes separando os nomes de teste com vírgulas. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-p113">Multiple tests can be added by separating the test names by using commas. For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="4dfd3-p114">Observe que um erro ocorrerá se um ou mais desses testes (por exemplo, DataConference) já estiverem ativados no nó do inspetor. Nesse caso, você receberá uma mensagem de erro semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-p114">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="4dfd3-173">Quando esse erro ocorre, nenhuma alteração será aplicada.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="4dfd3-174">O comando deve ser executado novamente com o teste duplicado removido.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="4dfd3-p116">Para remover uma transação sintética do nó do inspetor, use o método Remover em vez de Adicionar. Por exemplo, esse comando remove o teste ABWQ do nó do inspetor:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-p116">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method. For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="4dfd3-p117">É possível usar o método Substituir para substituir todos os testes ativados no momento por um ou mais testes novos. Por exemplo, se desejar que apenas um nó do inspetor execute o teste IM, você pode configurar isso usando este comando:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-p117">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="4dfd3-179">Quando você executa o comando anterior, todas as transações sintéticas no nó do inspetor especificado serão desativadas exceto para IM.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="4dfd3-180">Exibindo e testando a configuração do nó inspetor</span><span class="sxs-lookup"><span data-stu-id="4dfd3-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="4dfd3-181">Se quiser exibir os testes que foram atribuídos ao nó do inspetor, use um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="4dfd3-182">O comando anterior retornará informações semelhantes a essa, dependendo das transações sintéticas atribuídas ao nó:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> <span data-ttu-id="4dfd3-183">Para exibir as transações sintéticas em ordem alfabética, use este comando:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="4dfd3-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span><span class="sxs-lookup"><span data-stu-id="4dfd3-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="4dfd3-185">Para verificar se um nó do inspetor foi criado, digite o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="4dfd3-186">Você receberá informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="4dfd3-187">Para verificar se o nó do inspetor foi configurado corretamente, digite o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="4dfd3-188">O comando anterior testará o nó do inspetor em sua implantação e informará se:</span><span class="sxs-lookup"><span data-stu-id="4dfd3-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="4dfd3-189">A função Registrador necessária foi instalada.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="4dfd3-190">A chave de registro necessária foi criada por você ao executar Set-CsWatcherNodeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="4dfd3-191">Seus servidores estão executando a versão correta do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="4dfd3-192">Suas portas foram configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="4dfd3-193">Seus usuários de teste atribuídos têm as credenciais necessárias.</span><span class="sxs-lookup"><span data-stu-id="4dfd3-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

