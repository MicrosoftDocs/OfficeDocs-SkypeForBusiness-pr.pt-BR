---
title: Configurar usuários e configurações de teste do nó do watcher
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: configure as contas de usuário de teste e as configurações do nó do watcher para transações sintéticas do Skype for Business Server.'
ms.openlocfilehash: 6edce666345e4691d8850e5806eedbebc98e3743
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812761"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="a7d83-103">Configurar usuários e configurações de teste do nó do watcher</span><span class="sxs-lookup"><span data-stu-id="a7d83-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="a7d83-104">**Resumo:** Configure as contas de usuário de teste e as configurações do nó do watcher para transações sintéticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a7d83-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="a7d83-105">Depois de configurar o computador que atuará como um nó do inspetor, você deve:</span><span class="sxs-lookup"><span data-stu-id="a7d83-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="a7d83-106">[Configure contas de usuário de](test-users-and-settings-2019.md#testuser) teste a serem usadas por esses nós do watcher.</span><span class="sxs-lookup"><span data-stu-id="a7d83-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="a7d83-107">Se estiver usando o método de autenticação Negociar, você também deve usar o cmdlet **Set-CsTestUserCredential** para permitir o uso dessas contas de teste no nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="a7d83-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="a7d83-108">Atualizar as definições de configuração do nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="a7d83-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="a7d83-109">Configurar contas de usuário de teste</span><span class="sxs-lookup"><span data-stu-id="a7d83-109">Configure Test User Accounts</span></span>
<span data-ttu-id="a7d83-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="a7d83-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="a7d83-111">As contas de teste não precisam representar pessoas reais, mas devem ser contas válidas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a7d83-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="a7d83-112">Além disso, essas contas devem estar habilitadas para o Skype for Business Server, devem ter endereços SIP válidos e devem ser habilitadas para o Enterprise Voice (para usar a Test-CsPstnPeerToPeerCall sintética).</span><span class="sxs-lookup"><span data-stu-id="a7d83-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="a7d83-113">Se você estiver usando o método de autenticação TrustedServer, tudo o que você precisa fazer é garantir que essas contas existam e configurá-las conforme observado.</span><span class="sxs-lookup"><span data-stu-id="a7d83-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="a7d83-114">É necessário atribuir pelo menos três usuários de teste a cada pool que deseja testar.</span><span class="sxs-lookup"><span data-stu-id="a7d83-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="a7d83-115">Se você estiver usando o método de autenticação Negociar, também deverá usar o cmdlet Set-CsTestUserCredential e o Shell de Gerenciamento do Skype for Business Server para permitir que essas contas de teste funcionem com as transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="a7d83-116">Faça isso executando um comando semelhante ao seguinte (esses comandos presumem que as três contas de usuário do Active Directory foram criadas e que essas contas estão habilitadas para o Skype for Business Server):</span><span class="sxs-lookup"><span data-stu-id="a7d83-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="a7d83-117">Você deve incluir não apenas o endereço SIP, mas também o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="a7d83-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="a7d83-118">Se você não incluir a senha, o cmdlet Set-CsTestUserCredential solicitará que você insira essas informações.</span><span class="sxs-lookup"><span data-stu-id="a7d83-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="a7d83-119">O nome de usuário pode ser especificado usando o formato de nome de domínio \nome de usuário mostrado no bloco de código anterior.</span><span class="sxs-lookup"><span data-stu-id="a7d83-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="a7d83-120">Para verificar se as credenciais do usuário de teste foram criadas, execute estes comandos no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a7d83-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="a7d83-121">Informações semelhantes a essas serão retornadas para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="a7d83-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="a7d83-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="a7d83-122">**UserName**</span></span>|<span data-ttu-id="a7d83-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="a7d83-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a7d83-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="a7d83-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="a7d83-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="a7d83-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="a7d83-126">Configurar um nó do watcher básico com as transações sintéticas padrão</span><span class="sxs-lookup"><span data-stu-id="a7d83-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="a7d83-127">Depois que os usuários de teste são criados, você pode criar um nó do watcher usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="a7d83-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="a7d83-128">Esse comando cria um novo nó do inspetor que usa as configurações padrão e executa o conjunto padrão de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="a7d83-129">O novo nó do inspetor também usa watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com dos usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="a7d83-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="a7d83-130">Se o nó do watcher usar a autenticação TrustedServer, as três contas de teste poderão ser qualquer conta de usuário válida habilitada para o Active Directory e o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a7d83-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="a7d83-131">Se o nó do watcher usar o método de autenticação Negociar, essas contas de usuário também deverão ser habilitadas para o nó do watcher usando o Set-CsTestUserCredential cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7d83-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="a7d83-132">Para validar se a descoberta automática do pool de destino para entrar está configurada corretamente, em vez de direcionar um pool diretamente, use estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a7d83-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="a7d83-133">Configurando testes estendidos</span><span class="sxs-lookup"><span data-stu-id="a7d83-133">Configuring Extended Tests</span></span>

<span data-ttu-id="a7d83-134">Se você quiser habilitar o teste PSTN, que verifica a conectividade com a rede telefônica pública comutado, será necessário fazer algumas configurações adicionais ao configurar o nó do watcher.</span><span class="sxs-lookup"><span data-stu-id="a7d83-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="a7d83-135">Primeiro, você deve associar seus usuários de teste ao tipo de teste PSTN executando um comando semelhante a este no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a7d83-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="a7d83-136">Os resultados desse comando devem ser armazenados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="a7d83-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="a7d83-137">Neste exemplo, a variável é denominada $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="a7d83-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="a7d83-138">Em seguida, você pode usar o cmdlet **New-CsWatcherNodeConfiguration** para associar o tipo de teste (armazenado na variável $pstnTest) a um pool do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a7d83-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="a7d83-139">Por exemplo, o comando a seguir cria uma nova configuração de nó do watcher para o pool atl-cs-001.litwareinc.com, adicionando os três usuários de teste criados anteriormente e adicionando o tipo de teste PSTN:</span><span class="sxs-lookup"><span data-stu-id="a7d83-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="a7d83-140">O comando anterior falhará se você não tiver instalado os arquivos principais do Skype for Business Server e o banco de dados RTCLocal no computador do nó do watcher.</span><span class="sxs-lookup"><span data-stu-id="a7d83-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="a7d83-141">Para testar várias políticas de voz, você pode criar um teste estendido para cada política usando o cmdlet **New-CsExtendedTest.**</span><span class="sxs-lookup"><span data-stu-id="a7d83-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="a7d83-142">Os usuários fornecidos devem ser configurados com as políticas de voz desejadas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="a7d83-143">Os testes estendidos são passados para o cmdlet **New-CsWatcherNodeConfiguration** usando delimitadores de vírgula, como:</span><span class="sxs-lookup"><span data-stu-id="a7d83-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="a7d83-144">-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="a7d83-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="a7d83-145">Como o cmdlet **New-CsWatcherNodeConfiguration** foi chamado sem usar o parâmetro Tests, somente as transações sintéticas Padrão (e a transação sintética estendida especificada) serão habilitadas para o novo nó do watcher.</span><span class="sxs-lookup"><span data-stu-id="a7d83-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="a7d83-146">Portanto, o nó do watcher testará os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="a7d83-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="a7d83-147">Registro</span><span class="sxs-lookup"><span data-stu-id="a7d83-147">Registration</span></span>
    
- <span data-ttu-id="a7d83-148">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="a7d83-148">IM</span></span>
    
- <span data-ttu-id="a7d83-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="a7d83-149">GroupIM</span></span>
    
- <span data-ttu-id="a7d83-150">P2PAV (sessões de áudio/vídeo ponto a ponto)</span><span class="sxs-lookup"><span data-stu-id="a7d83-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="a7d83-151">AvConference (áudio/conferência)</span><span class="sxs-lookup"><span data-stu-id="a7d83-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="a7d83-152">Presença</span><span class="sxs-lookup"><span data-stu-id="a7d83-152">Presence</span></span>
    
- <span data-ttu-id="a7d83-153">ABS (serviço do Catálogo de Endereços)</span><span class="sxs-lookup"><span data-stu-id="a7d83-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="a7d83-154">ABWQ (serviço Web do Catálogo de Endereços)</span><span class="sxs-lookup"><span data-stu-id="a7d83-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="a7d83-155">Os seguintes componentes não serão testados por padrão:</span><span class="sxs-lookup"><span data-stu-id="a7d83-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="a7d83-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="a7d83-156">ASConference</span></span>
    
- <span data-ttu-id="a7d83-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="a7d83-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="a7d83-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="a7d83-158">DataConference</span></span>
    
- <span data-ttu-id="a7d83-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="a7d83-159">DialinConferencing</span></span>
    
- <span data-ttu-id="a7d83-160">ExumConnectivity (Unificação de Mensagens do Exchange)</span><span class="sxs-lookup"><span data-stu-id="a7d83-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="a7d83-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="a7d83-161">JoinLauncher</span></span>
    
- <span data-ttu-id="a7d83-162">MCXP2PIM (mensagens instantâneas de dispositivo móvel herdado)</span><span class="sxs-lookup"><span data-stu-id="a7d83-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="a7d83-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="a7d83-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="a7d83-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="a7d83-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="a7d83-165">PSTN (chamadas de gateway PSTN, especificadas como um teste estendido)</span><span class="sxs-lookup"><span data-stu-id="a7d83-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="a7d83-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="a7d83-166">UcwaConference</span></span>
    
- <span data-ttu-id="a7d83-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="a7d83-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="a7d83-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="a7d83-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="a7d83-169">Adicionando e removendo Transações sintéticas</span><span class="sxs-lookup"><span data-stu-id="a7d83-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="a7d83-170">Depois que um nó do inspetor é configurado, é possível usar o cmdlet Set-CsWatcherNodeConfiguration para adicionar ou remover transações sintéticas do nó.</span><span class="sxs-lookup"><span data-stu-id="a7d83-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="a7d83-171">Por exemplo, para adicionar o teste PersistentChatMessage ao nó do inspetor, use o método Adicionar e um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="a7d83-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="a7d83-172">É possível adicionar vários testes separando os nomes de teste com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="a7d83-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a7d83-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="a7d83-174">Ocorrerá um erro se um ou mais desses testes (por exemplo, DataConference) já tiver sido habilitado no nó do watcher.</span><span class="sxs-lookup"><span data-stu-id="a7d83-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="a7d83-175">Nesse caso, você receberá uma mensagem de erro semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="a7d83-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="a7d83-176">Set-CsWatcherNodeConfiguration : há uma sequência de chaves duplicada 'DataConference' para a chave 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' ou restrição de identidade exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a7d83-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="a7d83-177">Quando esse erro ocorre, nenhuma alteração será aplicada.</span><span class="sxs-lookup"><span data-stu-id="a7d83-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="a7d83-178">O comando deve ser executado de novo com o teste duplicado removido.</span><span class="sxs-lookup"><span data-stu-id="a7d83-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="a7d83-179">Para remover uma transação sintética de um nó do watcher, use o método Remove.</span><span class="sxs-lookup"><span data-stu-id="a7d83-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="a7d83-180">Por exemplo, esse comando remove o teste ABWQ do nó do inspetor:</span><span class="sxs-lookup"><span data-stu-id="a7d83-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="a7d83-181">Você pode usar o método Replace para substituir todos os testes habilitados no momento por um ou mais testes novos.</span><span class="sxs-lookup"><span data-stu-id="a7d83-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="a7d83-182">Por exemplo, se quiser que um nó do watcher apenas execute o teste de IM, você pode configurá-lo usando este comando:</span><span class="sxs-lookup"><span data-stu-id="a7d83-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="a7d83-183">Quando você executar esse comando, todas as transações sintéticas no nó do watcher especificado serão desabilitadas, exceto para IM.</span><span class="sxs-lookup"><span data-stu-id="a7d83-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="a7d83-184">Exibindo e testando a configuração do nó inspetor</span><span class="sxs-lookup"><span data-stu-id="a7d83-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="a7d83-185">Se quiser exibir os testes que foram atribuídos ao nó do inspetor, use um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="a7d83-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="a7d83-186">Este comando retornará informações semelhantes a esta, dependendo das transações sintéticas que foram atribuídas ao nó:</span><span class="sxs-lookup"><span data-stu-id="a7d83-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="a7d83-187">Registro de IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="a7d83-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="a7d83-188">Para exibir as transações sintéticas em ordem alfabética, use este comando:</span><span class="sxs-lookup"><span data-stu-id="a7d83-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="a7d83-189">Para verificar se um nó do watcher foi criado, digite o seguinte comando do Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a7d83-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="a7d83-190">Você receberá informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="a7d83-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="a7d83-191">Identidade : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="a7d83-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="a7d83-192">ExtendedTests : {TestUsers=IList<System.String>; Name=Teste PSTN; Te...}</span><span class="sxs-lookup"><span data-stu-id="a7d83-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="a7d83-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verificar se o nó do watcher foi configurado corretamente, digite o seguinte comando do Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a7d83-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="a7d83-194">Este comando testará cada nó do watcher em sua implantação e confirmará se as seguintes ações foram concluídas:</span><span class="sxs-lookup"><span data-stu-id="a7d83-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="a7d83-195">A função registradora necessária está instalada</span><span class="sxs-lookup"><span data-stu-id="a7d83-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="a7d83-196">A chave do Registro necessária é criada (concluída quando você Set-CsWatcherNodeConfiguration cmdlet)</span><span class="sxs-lookup"><span data-stu-id="a7d83-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="a7d83-197">Seus servidores estão executando a versão correta do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a7d83-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="a7d83-198">Suas portas estão configuradas corretamente</span><span class="sxs-lookup"><span data-stu-id="a7d83-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="a7d83-199">Os usuários de teste atribuídos têm as credenciais necessárias</span><span class="sxs-lookup"><span data-stu-id="a7d83-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="a7d83-200">Gerenciando nós do watcher</span><span class="sxs-lookup"><span data-stu-id="a7d83-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="a7d83-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="a7d83-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="a7d83-202">Além de modificar as transações sintéticas que são executadas em um nó do watcher, você também pode usar o cmdlet **Set-CsWatcherNodeConfiguration** para realizar duas outras tarefas importantes: ativar e desabilitar o nó do watcher e configurar o nó do watcher para usar URLs da Web internas ou EXTERNAs ao executar seus testes.</span><span class="sxs-lookup"><span data-stu-id="a7d83-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="a7d83-203">Por padrão, os nós do watcher são projetados para executar periodicamente todas as suas transações sintéticas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="a7d83-204">Às vezes, no entanto, talvez você queira suspender essas transações.</span><span class="sxs-lookup"><span data-stu-id="a7d83-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="a7d83-205">Por exemplo, se o nó do watcher estiver temporariamente desconectado da rede, não há motivo para executar as transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="a7d83-206">Sem conectividade de rede, essas transações falharão.</span><span class="sxs-lookup"><span data-stu-id="a7d83-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="a7d83-207">Para desabilitar temporariamente um nó do watcher, execute um comando semelhante a este no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a7d83-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="a7d83-208">Esse comando desabilitará a execução de transações sintéticas no nó do watcher atl watcher 001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a7d83-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="a7d83-209">Para retomar a execução das transações sintéticas, de definida a propriedade Enabled novamente como True ($True):</span><span class="sxs-lookup"><span data-stu-id="a7d83-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="a7d83-210">A propriedade Enabled pode ser usada para ativar ou desativar nós do watcher.</span><span class="sxs-lookup"><span data-stu-id="a7d83-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="a7d83-211">Se você quiser excluir permanentemente um nó do watcher, use o cmdlet **Remove-CsWatcherNodeConfiguration:**</span><span class="sxs-lookup"><span data-stu-id="a7d83-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="a7d83-212">Esse comando remove todas as definições de configuração do nó do watcher do computador especificado, o que impede que o computador automaticamente executar transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="a7d83-213">No entanto, o comando não desinstala os arquivos de agente do System Center ou os arquivos do sistema do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a7d83-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="a7d83-214">Por padrão, os nós do watcher usam AS URLs da Web externas da organização ao realizar testes.</span><span class="sxs-lookup"><span data-stu-id="a7d83-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="a7d83-215">No entanto, os nós do watcher também podem ser configurados para usar as URLs da Web internas da organização.</span><span class="sxs-lookup"><span data-stu-id="a7d83-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="a7d83-216">Isso permite que os administradores verifiquem o acesso à URL para usuários localizados dentro da rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="a7d83-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="a7d83-217">Para configurar um nó do watcher para usar URLs internas em vez de URLs externas, defina a propriedade UseInternalWebURls como True ($True):</span><span class="sxs-lookup"><span data-stu-id="a7d83-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="a7d83-218">Redefinir essa propriedade para o valor padrão False ($False) fará com que o watcher use novamente as URLs externas:</span><span class="sxs-lookup"><span data-stu-id="a7d83-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="a7d83-219">Instruções Especiais de Configuração para Transações Sintéticas</span><span class="sxs-lookup"><span data-stu-id="a7d83-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="a7d83-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="a7d83-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="a7d83-221">A maioria das transações sintéticas pode ser executado em um nó do watcher como está.</span><span class="sxs-lookup"><span data-stu-id="a7d83-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="a7d83-222">Na maioria dos casos, assim que a transação sintética é adicionada às definições de configuração do nó do watcher, o nó do watcher pode começar a usar essa transação sintética durante suas passagens de teste.</span><span class="sxs-lookup"><span data-stu-id="a7d83-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="a7d83-223">No entanto, existem algumas transações sintéticas que exigem instruções especiais de configuração, conforme discutido nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="a7d83-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="a7d83-224">Transação Sintética de Conferência de Dados</span><span class="sxs-lookup"><span data-stu-id="a7d83-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="a7d83-225">Se o computador do nó do seu watcher estiver localizado fora da rede de perímetro, você provavelmente não poderá executar a Transação Sintética de Conferência de Dados, a menos que primeiro desabilite as configurações de proxy do navegador Internet do Windows Internet Explorer® para a conta serviço de rede concluindo as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a7d83-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="a7d83-226">No computador do nó do watcher, clique em **Iniciar,** **em** Todos os **Programas,** em Acessórios, clique com o botão direito do mouse no **Prompt** de Comando e clique em Executar **como administrador.**</span><span class="sxs-lookup"><span data-stu-id="a7d83-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="a7d83-227">Na janela do console, digite o comando a seguir e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="a7d83-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="a7d83-228">Você verá a seguinte mensagem exibida na janela de comando:</span><span class="sxs-lookup"><span data-stu-id="a7d83-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="a7d83-229">BITSAdmin foi preterido e não há garantia de estar disponível em versões futuras do Windows.</span><span class="sxs-lookup"><span data-stu-id="a7d83-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="a7d83-230">As ferramentas de administração para o serviço BITS agora são fornecidas pelos cmdlets bits do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7d83-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="a7d83-231">Configurações de proxy da Internet para a conta NetworkService definidas como NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="a7d83-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="a7d83-232">(connection = default)</span><span class="sxs-lookup"><span data-stu-id="a7d83-232">(connection = default)</span></span>
  
<span data-ttu-id="a7d83-233">Esta mensagem indica que você desabilitou as configurações de proxy do Internet Explorer para a conta de Serviço de Rede.</span><span class="sxs-lookup"><span data-stu-id="a7d83-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="a7d83-234">Transação sintética da Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="a7d83-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="a7d83-235">A transação sintética da Unificação de Mensagens (UM) do Exchange verifica se os usuários de teste podem se conectar a contas de caixa postal que estão no Exchange.</span><span class="sxs-lookup"><span data-stu-id="a7d83-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="a7d83-236">Os usuários de teste precisarão ser pré-configurados com contas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="a7d83-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="a7d83-237">Transação Sintética de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="a7d83-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="a7d83-238">Para usar a transação sintética de Chat Persistente, você deve primeiro criar um canal e dar aos usuários de teste permissões para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="a7d83-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="a7d83-239">Você pode usar a transação sintética de Chat Persistente para configurar este canal:</span><span class="sxs-lookup"><span data-stu-id="a7d83-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="a7d83-240">Você deve executar essa tarefa de configuração de dentro da empresa:</span><span class="sxs-lookup"><span data-stu-id="a7d83-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="a7d83-241">Se for executado de uma máquina que não seja de servidor, o usuário que executar o cmdlet deverá ser membro da função CsPersistentChatAdministrators para Role-Based Access Control (RBAC).</span><span class="sxs-lookup"><span data-stu-id="a7d83-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="a7d83-242">Se for executado a partir do próprio servidor, o usuário que executar o cmdlet deverá ser membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a7d83-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="a7d83-243">Transação sintética de chamada ponto a ponto PSTN</span><span class="sxs-lookup"><span data-stu-id="a7d83-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="a7d83-244">A Test-CsPstnPeerToPeerCall sintética verifica a capacidade de fazer e receber chamadas por meio de uma PSTN (rede telefônica pública comutado).</span><span class="sxs-lookup"><span data-stu-id="a7d83-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="a7d83-245">Para executar essa transação sintética, você deve configurar:</span><span class="sxs-lookup"><span data-stu-id="a7d83-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="a7d83-246">Dois usuários de teste habilitados para UC (um chamador e um receptor).</span><span class="sxs-lookup"><span data-stu-id="a7d83-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="a7d83-247">Números DID (Discagem Interna Direta) para cada conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="a7d83-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="a7d83-248">Políticas VoIP e rotas de voz que permitem que as chamadas para o número do receptor cheguem ao gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="a7d83-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="a7d83-249">Um gateway PSTN que aceita chamada e mídia que encaminhará chamadas de volta para o pool base de um receptor, com base no número discado.</span><span class="sxs-lookup"><span data-stu-id="a7d83-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="a7d83-250">Transação sintética do armazenamento unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="a7d83-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="a7d83-251">A transação sintética do Armazenamento unificado de contatos verifica a capacidade do Skype for Business Server de recuperar contatos em nome de um usuário do Exchange.</span><span class="sxs-lookup"><span data-stu-id="a7d83-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="a7d83-252">Para usar essa transação sintética, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="a7d83-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="a7d83-253">Lyss-Exchange autenticação de servidor para servidor deve ser configurada.</span><span class="sxs-lookup"><span data-stu-id="a7d83-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="a7d83-254">Os usuários de teste devem ter uma caixa de correio válida do Exchange.</span><span class="sxs-lookup"><span data-stu-id="a7d83-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="a7d83-255">Depois que essas condições são atendidas, você pode executar o seguinte cmdlet do Windows PowerShell para migrar as listas de contatos dos usuários de teste para o Exchange:</span><span class="sxs-lookup"><span data-stu-id="a7d83-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="a7d83-256">Pode levar algum tempo para que as listas de contatos do usuário de teste migrem para o Exchange.</span><span class="sxs-lookup"><span data-stu-id="a7d83-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="a7d83-257">Para monitorar o progresso da migração, a mesma linha de comando pode ser executado sem o sinalizador -Setup:</span><span class="sxs-lookup"><span data-stu-id="a7d83-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="a7d83-258">Essa linha de comando será bem-sucedida após a conclusão da migração.</span><span class="sxs-lookup"><span data-stu-id="a7d83-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="a7d83-259">Transação sintética XMPP</span><span class="sxs-lookup"><span data-stu-id="a7d83-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="a7d83-260">A transação sintética XMPP (Extensible Messaging and Presence Protocol) exige que você configure o recurso XMPP com um ou mais domínios federados.</span><span class="sxs-lookup"><span data-stu-id="a7d83-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="a7d83-261">Para habilitar a transação sintética XMPP, você deve fornecer um parâmetro XmppTestReceiverMailAddress com uma conta de usuário em um domínio XMPP que pode ser remetido.</span><span class="sxs-lookup"><span data-stu-id="a7d83-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="a7d83-262">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a7d83-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="a7d83-263">Neste exemplo, uma regra do Skype for Business Server precisará existir para rotear mensagens de litwareinc.com para um gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="a7d83-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="a7d83-264">Gateways XMPP e proxies estavam disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a7d83-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a7d83-265">Consulte [Migrando federação XMPP](../migration/migrating-xmpp-federation.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a7d83-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="a7d83-266">Transação sintética do Vis (Servidor de Interop de Vídeo)</span><span class="sxs-lookup"><span data-stu-id="a7d83-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="a7d83-267">A transação sintética do ViS (Servidor de Interop de Vídeo) exige que você baixe e instale os arquivos de suporte de transação sintética[ (VISSTSupportPackage.msi). ](https://www.microsoft.com/download/details.aspx?id=46921)</span><span class="sxs-lookup"><span data-stu-id="a7d83-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="a7d83-268">Para instalar VISSTSupportPackage.msi verifique se as dependências (em Requisitos do Sistema) para o msi já estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="a7d83-269">Execute VISSTSupportPackage.msi para fazer uma instalação simples.</span><span class="sxs-lookup"><span data-stu-id="a7d83-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="a7d83-270">O .msi instala todos os arquivos no seguinte caminho: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span><span class="sxs-lookup"><span data-stu-id="a7d83-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="a7d83-271">Para obter mais detalhes sobre como executar a Transação Sintética vis, consulte a documentação do cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV.](https://technet.microsoft.com/library/dn985894.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7d83-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="a7d83-272">Alterando a frequência de executar transações sintéticas</span><span class="sxs-lookup"><span data-stu-id="a7d83-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="a7d83-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="a7d83-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="a7d83-274">Por padrão, as transações sintéticas serão executados com os usuários configurados a cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a7d83-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="a7d83-275">As transações sintéticas são executados sequencialmente dentro de um conjunto de usuários para evitar que duas transações sintéticas conflitam entre si.</span><span class="sxs-lookup"><span data-stu-id="a7d83-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="a7d83-276">Um intervalo mais longo é necessário para fornecer tempo para a conclusão de todas as transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="a7d83-277">Se desejar executar transações sintéticas com mais frequência, o número de transações sintéticas que são executados com um determinado conjunto de usuários deve ser diminuído para que os testes possam ser concluídos no intervalo de tempo desejado com algum buffer para atrasos ocasionais na rede.</span><span class="sxs-lookup"><span data-stu-id="a7d83-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="a7d83-278">Se for desejável executar mais transações sintéticas, crie mais conjuntos de usuários para executar transações sintéticas adicionais.</span><span class="sxs-lookup"><span data-stu-id="a7d83-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="a7d83-279">Para alterar a frequência na qual as transações sintéticas são executados, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a7d83-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="a7d83-280">Abra o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a7d83-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="a7d83-281">Clique na seção Autoria.</span><span class="sxs-lookup"><span data-stu-id="a7d83-281">Click Authoring section.</span></span> <span data-ttu-id="a7d83-282">Seção Click Rules (em Authoring)</span><span class="sxs-lookup"><span data-stu-id="a7d83-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="a7d83-283">Na seção Regras, encontre a regra com o nome "Regra principal de coleta de desempenho do final da transação sintética"</span><span class="sxs-lookup"><span data-stu-id="a7d83-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="a7d83-284">Clique com o botão direito do mouse na regra e selecione Substituições, selecione Substituir a Regra e selecione "Para todos os objetos da classe: Pool Watcher"</span><span class="sxs-lookup"><span data-stu-id="a7d83-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="a7d83-285">Na janela Substituir Propriedades, selecione Nome do Parâmetro "Freqüência" e de definida o Valor de Substituição como o desejado.</span><span class="sxs-lookup"><span data-stu-id="a7d83-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="a7d83-286">Na mesma janela, selecione o pacote de gerenciamento ao qual essa substituição precisa ser aplicada</span><span class="sxs-lookup"><span data-stu-id="a7d83-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="a7d83-287">Usando Registro em Log Sofisticado para Transações Sintéticas</span><span class="sxs-lookup"><span data-stu-id="a7d83-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="a7d83-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="a7d83-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="a7d83-289">As transações sintéticas são extremamente úteis para ajudar a identificar problemas com o sistema.</span><span class="sxs-lookup"><span data-stu-id="a7d83-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="a7d83-290">Por exemplo, o Test-CsRegistration cmdlet pode alertar os administradores para o fato de que os usuários estavam com dificuldades para se registrar no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a7d83-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="a7d83-291">No entanto, detalhes adicionais podem ser necessários para determinar a causa real de uma falha.</span><span class="sxs-lookup"><span data-stu-id="a7d83-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="a7d83-292">Por esse motivo, as transações sintéticas fornecem registro em log rico.</span><span class="sxs-lookup"><span data-stu-id="a7d83-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="a7d83-293">Com o registro em log rico, para cada atividade assumida por uma transação sintética, as seguintes informações são registradas:</span><span class="sxs-lookup"><span data-stu-id="a7d83-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="a7d83-294">A hora em que a atividade foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="a7d83-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="a7d83-295">A hora em que a atividade foi concluída.</span><span class="sxs-lookup"><span data-stu-id="a7d83-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="a7d83-296">A ação que foi executada (por exemplo, criar, ingressar ou sair de uma conferência; entrar no Skype for Business Server; enviar uma mensagem instantânea).</span><span class="sxs-lookup"><span data-stu-id="a7d83-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="a7d83-297">Mensagens informativas, detalhadas, de advertência ou de erro geradas quando a atividade foi executada</span><span class="sxs-lookup"><span data-stu-id="a7d83-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="a7d83-298">Mensagens de registro SIP.</span><span class="sxs-lookup"><span data-stu-id="a7d83-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="a7d83-299">Registros de exceção ou códigos de diagnóstico gerados quando a atividade foi realizada.</span><span class="sxs-lookup"><span data-stu-id="a7d83-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="a7d83-300">O resultado líquido da execução da atividade.</span><span class="sxs-lookup"><span data-stu-id="a7d83-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="a7d83-301">Essas informações são geradas automaticamente sempre que uma transação sintética é executado, mas não são exibidas ou salvas automaticamente em um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="a7d83-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="a7d83-302">Se você estiver executando manualmente uma transação sintética, poderá usar o parâmetro OutLoggerVariable para especificar uma variável do Windows PowerShell na qual as informações serão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="a7d83-303">A partir daí, você tem a opção de usar um dos dois métodos para salvar e/ou exibir mensagens de erro no log rich no formato XML ou HTML.</span><span class="sxs-lookup"><span data-stu-id="a7d83-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="a7d83-304">Para recuperar as informações de solução de problemas, especifique o parâmetro OutLoggerVariable, seguido de um nome de variável que você escolher:</span><span class="sxs-lookup"><span data-stu-id="a7d83-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="a7d83-305">: Não prefigurar o nome da variável com o caractere $.</span><span class="sxs-lookup"><span data-stu-id="a7d83-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="a7d83-306">Use um nome de variável como RegistrationTest (não $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="a7d83-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="a7d83-307">Ao executar esse comando, você verá uma saída semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="a7d83-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="a7d83-308">Fqdn de Destino : atl-cs-001.litwareinc.com Resultado : Latência de Falha : 00:00:00 Mensagem de Erro: Esta máquina não tem certificados atribuídos.</span><span class="sxs-lookup"><span data-stu-id="a7d83-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="a7d83-309">Diagnóstico:Você pode acessar informações muito mais detalhadas para essa falha do que apenas a mensagem de erro mostrada aqui.</span><span class="sxs-lookup"><span data-stu-id="a7d83-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="a7d83-310">Para acessar essas informações no formato HTML, use um comando semelhante a este para salvar as informações armazenadas na variável RegistrationTest em um arquivo HTML:</span><span class="sxs-lookup"><span data-stu-id="a7d83-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="a7d83-311">Como alternativa, é possível usar o método ToXML() para salvar os dados em um arquivo XML:</span><span class="sxs-lookup"><span data-stu-id="a7d83-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="a7d83-312">Você pode exibir esses arquivos usando o Windows Internet Explorer, o Microsoft Visual Studio ou qualquer outro aplicativo capaz de abrir arquivos HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="a7d83-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="a7d83-313">As transações sintéticas que são executados de dentro do System Center Operations Manager gerarão automaticamente esses arquivos de log para falhas.</span><span class="sxs-lookup"><span data-stu-id="a7d83-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="a7d83-314">Esses logs não serão gerados se a execução falhar antes que o PowerShell do Skype for Business Server possa carregar e executar a transação sintética.</span><span class="sxs-lookup"><span data-stu-id="a7d83-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a7d83-315">Por padrão, o Skype for Business Server salva arquivos de log em uma pasta que não é compartilhada.</span><span class="sxs-lookup"><span data-stu-id="a7d83-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="a7d83-316">Para tornar esses logs prontamente acessíveis, você deve compartilhar essa pasta.</span><span class="sxs-lookup"><span data-stu-id="a7d83-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="a7d83-317">Por exemplo: \\ atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="a7d83-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
