---
title: Configurar usuários de teste e configurações do nó do inspetor
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Resumo: Configure contas de usuário de teste e configurações de nó do observador do Skype para transações sintéticas do Business Server.'
ms.openlocfilehash: ee5330f10dd97e8ecc8a3e3e30962e6e8a69555b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569872"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="82040-103">Configurar usuários de teste e configurações do nó do inspetor</span><span class="sxs-lookup"><span data-stu-id="82040-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="82040-104">**Resumo:** Configure contas de usuário de teste e configurações de nó do observador do Skype para transações sintéticas do Business Server.</span><span class="sxs-lookup"><span data-stu-id="82040-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="82040-105">Depois de configurar o computador que atuará como um nó do inspetor, você deve:</span><span class="sxs-lookup"><span data-stu-id="82040-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="82040-106">[Configurar contas de usuário de teste](test-users-and-settings.md#testuser) a ser usado por esses nós do observador.</span><span class="sxs-lookup"><span data-stu-id="82040-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="82040-107">Se estiver usando o método de autenticação Negociar, você também deve usar o cmdlet **Set-CsTestUserCredential** para permitir o uso dessas contas de teste no nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="82040-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="82040-108">Atualizar as definições de configuração do nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="82040-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="82040-109">Configurar contas de usuário de teste</span><span class="sxs-lookup"><span data-stu-id="82040-109">Configure Test User Accounts</span></span>
<span data-ttu-id="82040-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="82040-110"></span></span>

<span data-ttu-id="82040-111">Contas de teste não precisará representam pessoas reais, mas eles devem ser contas válidas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82040-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="82040-112">Além disso, essas contas devem ser habilitadas para Skype para Business Server 2015, eles devem ter endereços válidos de SIP e eles devem ser habilitados para o Enterprise Voice (usar a transação sintética de Test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="82040-112">In addition, these accounts must be enabled for Skype for Business Server 2015, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="82040-113">Se você estiver usando o método de autenticação TrustedServer, tudo o que você precisa fazer é certificar-se de que essas contas existem e configurá-las como observado.</span><span class="sxs-lookup"><span data-stu-id="82040-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="82040-114">É necessário atribuir pelo menos três usuários de teste a cada pool que deseja testar.</span><span class="sxs-lookup"><span data-stu-id="82040-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="82040-115">Se você estiver usando o método de autenticação negociar, você também deve usar o cmdlet Set-CsTestUserCredential e do Skype para Business Server Management Shell habilitar essas contas para trabalhar com as transações sintéticas de teste.</span><span class="sxs-lookup"><span data-stu-id="82040-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="82040-116">Fazer isso executando um comando semelhante ao seguinte (esses comandos assumem que as três contas de usuário do Active Directory foram criadas e que essas contas estão habilitadas para Skype para Business Server 2015):</span><span class="sxs-lookup"><span data-stu-id="82040-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server 2015):</span></span>
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="82040-p104">É necessário incluir não apenas o endereço SIP, mas também o nome e a senha do usuário. Se você não incluir a senha, o cmdlet Set-CsTestUserCredential solicitará que você insira essas informações. O nome de usuário pode ser especificado usando-se o formato de nome de domínio\nome de usuário indicado no bloqueio do código anterior.</span><span class="sxs-lookup"><span data-stu-id="82040-p104">You must include not only the SIP address, but also the user name and password. If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information. The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="82040-120">Para verificar se as credenciais de usuário de teste foram criadas, execute estes comandos do Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="82040-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="82040-121">Informações semelhantes a estas devem ser retornadas para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="82040-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="82040-122">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="82040-122">**UserName**</span></span>|<span data-ttu-id="82040-123">**Senha**</span><span class="sxs-lookup"><span data-stu-id="82040-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="82040-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="82040-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="82040-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="82040-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="82040-126">Configurar um nó básico do inspetor com as transações sintéticas padrão</span><span class="sxs-lookup"><span data-stu-id="82040-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="82040-127">Depois que os usuários de teste são criados, você pode criar um nó do inspetor usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="82040-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="82040-p105">Esse comando cria um novo nó do inspetor que usa as configurações padrão e executa o conjunto padrão de transações sintéticas. O novo nó do inspetor também usa os usuários de teste watcher1@litwareinc.com, watcher2@litwareinc.com, e watcher3@litwareinc.com. Se o nó do inspetor usa autenticação TrustedServer, as três contas de teste podem ser quaisquer contas válidas habilitadas para Active Directory e o Skype for Business Server. Se o nó do inspetor usa o método de autenticação Negociar, estas contas de usuário também deve ser ativadas para o nó do inspetor usando o cmdlet Set-Cs TestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="82040-p105">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions. The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com. If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server. If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="82040-132">Para validar se a descoberta automática de pool de destino a ser inserida está configurada corretamente, ao invés de direcionar um pool diretamente, siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="82040-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="82040-133">Configurando testes estendidos</span><span class="sxs-lookup"><span data-stu-id="82040-133">Configuring Extended Tests</span></span>

<span data-ttu-id="82040-p106">Se quiser habilitar o teste PSTN, que verifica a conectividade com a rede telefônica pública comutada, você precisará fazer algumas configurações adicionais ao configurar o nó do inspetor. Primeiro, você deve associar seus usuários de teste ao tipo de teste da PSTN executando um comando semelhante a este no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="82040-p106">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node. First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="82040-p107">Os resultados desse comando devem ser armazenados em uma variável. Neste exemplo, é uma variável chamada de $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="82040-p107">The results of this command must be stored in a variable. In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="82040-p108">Nesse ponto, você pode usar o cmdlet **New-CsWatcherNodeConfiguration** para associar o tipo de teste (armazenado na variável $pstnTest) a um pool do Skype for Business Server 2015. Por exemplo, o seguinte comando cria uma nova configuração de nó do inspetor para o pool atl-cs-001.litwareinc.com, adicionando os três usuários de teste que foram criados anteriormente e também adicionando o tipo de teste de PSTN:</span><span class="sxs-lookup"><span data-stu-id="82040-p108">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server 2015 pool. For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="82040-140">O comando anterior falhará se você não tiver instalado os arquivos de núcleo do Skype for Business Server 2015 e o banco de dados RTCLocal no computador do nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="82040-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="82040-p109">Para testar várias políticas de voz, você pode criar um teste estendido para cada política usando o cmdlet **New-CsExtendedTest**. Os usuários fornecidos devem ser configurados com as políticas de voz desejadas. Os testes estendidos são passados para o cmdlet **New-CsWatcherNodeConfiguration** separados por vírgula, como indicado:</span><span class="sxs-lookup"><span data-stu-id="82040-p109">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet. The users provided should be configured with the desired voice policies. The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="82040-144">-ExtendedTests @{adicionar = US $pstnTest1, $pstnTest2, $pstnTest3}</span><span class="sxs-lookup"><span data-stu-id="82040-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="82040-p110">Como o cmdlet **New-CsWatcherNodeConfiguration** foi chamado sem usar o parâmetro Tests, isso significa que somente as transações sintéticas Padrão (e a transação sintética estendida especificada) serão ativadas no novo nó do inspetor. Portanto, o nó do inspetor testará os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="82040-p110">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="82040-147">Registro</span><span class="sxs-lookup"><span data-stu-id="82040-147">Registration</span></span>
    
- <span data-ttu-id="82040-148">IM</span><span class="sxs-lookup"><span data-stu-id="82040-148">IM</span></span>
    
- <span data-ttu-id="82040-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="82040-149">GroupIM</span></span>
    
- <span data-ttu-id="82040-150">P2PAV (sessões de áudio/vídeo ponto a ponto)</span><span class="sxs-lookup"><span data-stu-id="82040-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="82040-151">AvConference (áudio/conferência)</span><span class="sxs-lookup"><span data-stu-id="82040-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="82040-152">Presença</span><span class="sxs-lookup"><span data-stu-id="82040-152">Presence</span></span>
    
- <span data-ttu-id="82040-153">ABS (serviço do Catálogo de Endereços)</span><span class="sxs-lookup"><span data-stu-id="82040-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="82040-154">ABWQ (serviço Web do Catálogo de Endereços)</span><span class="sxs-lookup"><span data-stu-id="82040-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="82040-155">Os seguintes componentes não serão testados por padrão:</span><span class="sxs-lookup"><span data-stu-id="82040-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="82040-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="82040-156">ASConference</span></span>
    
- <span data-ttu-id="82040-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="82040-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="82040-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="82040-158">DataConference</span></span>
    
- <span data-ttu-id="82040-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="82040-159">DialinConferencing</span></span>
    
- <span data-ttu-id="82040-160">ExumConnectivity (Unificação de Mensagens do Exchange)</span><span class="sxs-lookup"><span data-stu-id="82040-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="82040-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="82040-161">JoinLauncher</span></span>
    
- <span data-ttu-id="82040-162">MCXP2PIM (mensagens instantâneas do dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="82040-162">MCXP2PIM (mobile device instant messaging)</span></span>
    
- <span data-ttu-id="82040-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="82040-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="82040-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="82040-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="82040-165">PSTN (chamadas de gateway PSTN, especificadas como um teste estendido)</span><span class="sxs-lookup"><span data-stu-id="82040-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="82040-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="82040-166">UcwaConference</span></span>
    
- <span data-ttu-id="82040-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="82040-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="82040-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="82040-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="82040-169">Adicionando e removendo transações sintéticas</span><span class="sxs-lookup"><span data-stu-id="82040-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="82040-p111">Depois que um nó do inspetor é configurado, é possível usar o cmdlet  Set-CsWatcherNodeConfiguration para adicionar ou remover transações sintéticas do nó. Por exemplo, para adicionar o teste PersistentChatMessage ao nó do inspetor, use o método Add e um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="82040-p111">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node. For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="82040-p112">É possível adicionar vários testes separando os nomes de teste com vírgulas. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="82040-p112">Multiple tests can be added by separating the test names by using commas. For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="82040-p113">Um erro ocorrerá se um ou mais desses testes (por exemplo, DataConference) já estiverem ativados no nó do inspetor. Nesse caso, você receberá uma mensagem de erro semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="82040-p113">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="82040-176">Set-CsWatcherNodeConfiguration : Há uma sequência principal duplicada 'DataConference' para 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' ou restrição de identidade única.</span><span class="sxs-lookup"><span data-stu-id="82040-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="82040-177">Quando esse erro ocorre, nenhuma alteração será aplicada.</span><span class="sxs-lookup"><span data-stu-id="82040-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="82040-178">O comando deve ser executado novamente com o teste duplicado removido.</span><span class="sxs-lookup"><span data-stu-id="82040-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="82040-p115">Para remover uma transação sintética do nó do inspetor, use o método Remove. Por exemplo, esse comando remove o teste ABWQ do nó do inspetor:</span><span class="sxs-lookup"><span data-stu-id="82040-p115">To remove a synthetic transaction from a watcher node, use the Remove method. For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="82040-p116">É possível usar o método Replace para substituir todos os testes ativados no momento por um ou mais testes novos. Por exemplo, se desejar que apenas um nó do inspetor execute o teste IM, você pode configurar isso usando este comando:</span><span class="sxs-lookup"><span data-stu-id="82040-p116">You can use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="82040-183">Quando você executa o comando anterior, todas as transações sintéticas no nó do inspetor especificado serão desativadas exceto para IM.</span><span class="sxs-lookup"><span data-stu-id="82040-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="82040-184">Exibindo e testando a configuração do nó do inspetor</span><span class="sxs-lookup"><span data-stu-id="82040-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="82040-185">Se quiser exibir os testes que foram atribuídos ao nó do inspetor, use um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="82040-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="82040-186">O comando anterior retornará informações semelhantes a essa, dependendo das transações sintéticas atribuídas ao nó:</span><span class="sxs-lookup"><span data-stu-id="82040-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="82040-187">Registro IM GroupIM P2PAV AvConference presença PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="82040-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="82040-188">Para exibir as transações sintéticas em ordem alfabética, use este comando:</span><span class="sxs-lookup"><span data-stu-id="82040-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="82040-189">Para verificar se um nó do inspetor foi criado, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="82040-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="82040-190">Você receberá informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="82040-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="82040-191">Identidade: atl-cs-001 TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="82040-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="82040-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="82040-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="82040-193">TargetFqdn: número da porta atl-cs-001: 5061To verificar que o nó do Inspetor foi configurado corretamente, digite o seguinte comando do Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="82040-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="82040-194">Este comando testará o nó do inspetor em sua implantação e confirmará se as seguintes ações foram concluídas:</span><span class="sxs-lookup"><span data-stu-id="82040-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="82040-195">A função Registrador Avançado necessária foi instalada.</span><span class="sxs-lookup"><span data-stu-id="82040-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="82040-196">A chave de registro necessária for criada (concluída ao executar o cmdlet Set-CsWatcherNodeConfiguration)</span><span class="sxs-lookup"><span data-stu-id="82040-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="82040-197">Seus servidores estão executando a versão correta do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="82040-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="82040-198">Suas portas foram configuradas corretamente</span><span class="sxs-lookup"><span data-stu-id="82040-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="82040-199">Seus usuários de teste atribuídos têm as credenciais necessárias</span><span class="sxs-lookup"><span data-stu-id="82040-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="82040-200">Gerenciar nós do inspetor</span><span class="sxs-lookup"><span data-stu-id="82040-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="82040-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="82040-201"></span></span>

<span data-ttu-id="82040-202">Além de modificar as transações sintéticas que são executadas em um nó do inspetor, você também podem usar o cmdlet **Set-CsWatcherNodeConfiguration** para realizar duas outras tarefas importantes: habilitar e desabilitar o nó do inspetor e configurá-lo para usar URLs da Web internas ou externas durante a execução de testes.</span><span class="sxs-lookup"><span data-stu-id="82040-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="82040-p118">Por padrão, os nós do inspetor são projetados para executar periodicamente todas as transações sintéticas habilitadas. Às vezes, no entanto, você pode querer suspender essas transações. Por exemplo, se o nó do inspetor estiver temporariamente desconectado da rede, não há motivo para executar as transações sintéticas. Sem conectividade de rede, essas transações falharão. Para desabilitar o nó do inspetor temporariamente, execute um comando semelhante a este no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="82040-p118">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions. At times, however, you may want to suspend those transactions. For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions. Without network connectivity, those transactions will fail. To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="82040-p119">Esse comando desabilitará a execução das transações sintéticas no nó do inspetor atl-watcher- 001.litwareinc.com. Para retomar a execução das transações sintéticas, defina a propriedade Enabled novamente como True ($True):</span><span class="sxs-lookup"><span data-stu-id="82040-p119">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="82040-p120">A propriedade Enabled pode ser usada para habilitar e desabilitar os nós do inspetor. Se você desejar excluir permanentemente um nó do inspetor, use o cmdlet **Remove-CsWatcherNodeConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="82040-p120">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="82040-p121">Esse comando remove todas as configurações de nó do inspetor do computador especificado, o que impede que o computador execute transações sintéticas automaticamente. No entanto, o comando não desinstala os arquivos de agente do System Center nem os arquivos de sistema do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="82040-p121">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions. However, the command does not uninstall the System Center agent files or the Skype for Business Server 2015 system files.</span></span>
  
<span data-ttu-id="82040-p122">Por padrão, os nós do inspetor usam as URLs da Web externas de uma organização durante a realização de seus testes. No entanto, também é possível configurá-los para usar as URLs da Web internas da organização. Isso permite que os administradores verifiquem o acesso a URLs para os usuários localizados dentro da rede de perímetro. Para configurar um nó do inspetor para usar as URLs internas em vez das externas, defina a propriedade UseInternalWebUrls como True ($True):</span><span class="sxs-lookup"><span data-stu-id="82040-p122">By default, watcher nodes use an organization's external Web URLs when conducting tests. However, watcher nodes can also be configured to use the organization's internal Web URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="82040-218">A redefinição dessa propriedade para o valor padrão False ($False) fará com que o inspetor mais uma vez use as URLs externas:</span><span class="sxs-lookup"><span data-stu-id="82040-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="82040-219">Instruções Especiais de Configuração para Transações Sintéticas</span><span class="sxs-lookup"><span data-stu-id="82040-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="82040-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="82040-220"></span></span>

<span data-ttu-id="82040-p123">A maioria das transações sintéticas pode ser executada em um nó do inspetor como está. Na maioria dos casos, assim que uma transação sintética é adicionada às configurações do nó do inspetor, o nó do inspetor pode começar usando essa transação sintética durante suas fases de teste. No entanto, existem algumas transações sintéticas que exigem instruções especiais de configuração, conforme discutido nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="82040-p123">Most synthetic transactions can run on a watcher node as-is. In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes. However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="82040-224">Transação Sintética de Conferência de Dados</span><span class="sxs-lookup"><span data-stu-id="82040-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="82040-225">Se o computador de nó do inspetor estiver localizado fora da sua rede de perímetro, você provavelmente não será capaz de executar a transação sintética de conferência de dados, a menos que primeiro desabilite as configurações de proxy do navegador do Windows Internet Explorer® para a conta Serviço de Rede completando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="82040-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="82040-226">No computador de nó do inspetor, clique em **Iniciar**, em **Todos os Programas**, em **Acessórios**, clique com o botão direito do mouse em **Prompt de Comando**, e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="82040-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="82040-227">Na janela do console, digite o seguinte comando e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="82040-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="82040-228">Você verá a seguinte mensagem exibida na janela de comando:</span><span class="sxs-lookup"><span data-stu-id="82040-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="82040-p124">BITSAdmin é deprecada e nada garante que estará disponível em versões futuras do Windows. Ferramentas de Administração para o serviço BITS agora são fornecidas pelos cmdlets BITS PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82040-p124">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="82040-231">As configurações de proxy da Internet para conta Serviço de Rede estão definidas como NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="82040-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="82040-232">(conexão = padrão)</span><span class="sxs-lookup"><span data-stu-id="82040-232">(connection = default)</span></span>
  
<span data-ttu-id="82040-233">Esta mensagem indica que você desabilitou as configurações de proxy do Internet Explorer para a conta Serviço de Rede.</span><span class="sxs-lookup"><span data-stu-id="82040-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="82040-234">Transações sintéticas de Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="82040-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="82040-235">A transação sintética de Unificação de Mensagens do Exchange verifica se usuários de teste podem se conectar a contas de correio de voz hospedadas no Exchange.</span><span class="sxs-lookup"><span data-stu-id="82040-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="82040-236">Os usuários de teste precisarão ser pré-configurados com contas de correio de voz.</span><span class="sxs-lookup"><span data-stu-id="82040-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="82040-237">Transação Sintética de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="82040-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="82040-238">Para usar a transação sintética do chat persistente, você deve primeiro criar um canal e conceder aos usuários de teste permissões para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="82040-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="82040-239">Você pode usar a transação sintética de chat persistente para configurar esse canal:</span><span class="sxs-lookup"><span data-stu-id="82040-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="82040-240">Você deve executar esta tarefa de configuração de dentro da empresa:</span><span class="sxs-lookup"><span data-stu-id="82040-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="82040-241">Se ela for realizada de uma máquina que não é um servidor, o usuário que executar o cmdlet deverá ser um membro da função CsPersistentChatAdministrators do RBAC (Controle de Acesso Baseado em Função).</span><span class="sxs-lookup"><span data-stu-id="82040-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="82040-242">Se ela for realizada a partir do próprio servidor, o usuário que executar o cmdlet deverá ser um membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="82040-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="82040-243">Transações sintéticas de chamada ponto a ponto PSTN</span><span class="sxs-lookup"><span data-stu-id="82040-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="82040-244">A transação sintética de Test-CSPstnPeerToPeerCall verifica a capacidade de realizar e receber chamadas através de uma PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="82040-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="82040-245">Para executar essa transação sintética, você deve configurar:</span><span class="sxs-lookup"><span data-stu-id="82040-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="82040-246">Dois usuários de teste habilitados em UC (um chamador e um receptor).</span><span class="sxs-lookup"><span data-stu-id="82040-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="82040-247">Números DID (Discagem Interna Direta) para cada conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="82040-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="82040-248">Rotas de voz e políticas de VoIP que permitem que chamadas para o número do receptor cheguem ao gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="82040-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="82040-249">Um gateway PSTN que aceita chamadas e mídia que encaminharão as chamadas de volta ao pool primário de um receptor, com base no número discado.</span><span class="sxs-lookup"><span data-stu-id="82040-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="82040-250">Transações Sintéticas do Repositório Unificado de Contatos</span><span class="sxs-lookup"><span data-stu-id="82040-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="82040-251">A transação sintética do Repositório Unificado de Contatos verifica a capacidade do Skype for Business Server 2015 recuperar contatos em nome de um usuário do Exchange.</span><span class="sxs-lookup"><span data-stu-id="82040-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server 2015 to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="82040-252">Para usar essa transação sintética, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="82040-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="82040-253">A autenticação de servidor para servidor do Lyss-Exchange deve ser configurada.</span><span class="sxs-lookup"><span data-stu-id="82040-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="82040-254">Os usuários de teste devem ter uma caixa de entrada válida do Exchange.</span><span class="sxs-lookup"><span data-stu-id="82040-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="82040-255">Depois que essas condições forem atendidas, você pode executar o seguinte cmdlet do Windows PowerShell para migrar as listas de contatos dos usuários de teste para o Exchange:</span><span class="sxs-lookup"><span data-stu-id="82040-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="82040-256">Pode levar algum tempo para que as listas de contato do usuário de teste migrem para o Exchange.</span><span class="sxs-lookup"><span data-stu-id="82040-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="82040-257">Para monitorar o andamento da migração, a mesma linha de comando pode ser executada sem o - sinalizador de instalação:</span><span class="sxs-lookup"><span data-stu-id="82040-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="82040-258">Esta linha de comando será bem-sucedida após a conclusão da migração.</span><span class="sxs-lookup"><span data-stu-id="82040-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="82040-259">Transação Sintética XMPP</span><span class="sxs-lookup"><span data-stu-id="82040-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="82040-260">A transação sintética de IM do protocolo XMPP (Extensible Messaging and Presence Protocol) exige que o recurso XMPP seja configurado com um ou mais domínios federados.</span><span class="sxs-lookup"><span data-stu-id="82040-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="82040-261">Para habilitar a transação sintética XMPP, um parâmetro XmppTestReceiverMailAddress deve ser fornecido com uma conta de usuário em um domínio XMPP roteável.</span><span class="sxs-lookup"><span data-stu-id="82040-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="82040-262">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="82040-262">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="82040-263">No exemplo, uma regra do Skype for Business Server 2015 precisará existir para encaminhar mensagens de litwareinc.com para um gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="82040-263">In this example, a Skype for Business Server 2015 rule will need to exist to route messages for litwareinc.com to an XMPP gateway</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="82040-264">Transação sintética do Servidor de Interoperabilidade de Vídeo (VIS)</span><span class="sxs-lookup"><span data-stu-id="82040-264">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="82040-265">A transação sintética do servidor de interoperabilidade de vídeo (VIS) requer que você baixe e instale os arquivos de suporte de transação sintética ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="82040-265">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="82040-266">Para instalar VISSTSupportPackage.msi, certifique-se de que as dependências (em Requisitos de Sistema) para o msi já se encontram instaladas.</span><span class="sxs-lookup"><span data-stu-id="82040-266">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="82040-267">Executar VISSTSupportPackage.msi para realizar uma instalação simples.</span><span class="sxs-lookup"><span data-stu-id="82040-267">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="82040-268">O arquivo. msi instala todos os arquivos no seguinte caminho: "%ProgramFiles%\VIS pacote de suporte de transação sintética".</span><span class="sxs-lookup"><span data-stu-id="82040-268">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="82040-269">Para obter mais detalhes sobre como executar a transação sintética de VIS consulte a documentação para o cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="82040-269">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="82040-270">Alterar a Frequência de Execução para Transações Sintéticas</span><span class="sxs-lookup"><span data-stu-id="82040-270">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="82040-271"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="82040-271"></span></span>

<span data-ttu-id="82040-272">Por padrão, as transações sintéticas serão executadas com usuários configurados a cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="82040-272">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="82040-273">As transações sintéticas são executados em sequência dentro de um conjunto de usuários para evitar que duas transações sintéticas entrem em conflito.</span><span class="sxs-lookup"><span data-stu-id="82040-273">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="82040-274">Um intervalo mais longo é necessária para permitir que todas as transações sintéticas sejam concluídas a tempo.</span><span class="sxs-lookup"><span data-stu-id="82040-274">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="82040-275">Se você desejar executar transações sintéticas com mais frequência, o número de transações sintéticas executadas com um determinado conjunto de usuários deve ser diminuída a fim de que os testes possam ser concluídos em um intervalo de tempo desejado com algum buffer para eventuais atrasos na rede.</span><span class="sxs-lookup"><span data-stu-id="82040-275">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="82040-276">Se você desejar executar mais transações sintéticas, crie mais conjuntos de usuário para executar transações sintéticas adicionais.</span><span class="sxs-lookup"><span data-stu-id="82040-276">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="82040-277">Para alterar a frequência de execução das transações sintéticas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="82040-277">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="82040-278">Abrir o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="82040-278">Open System Center Operations Manager.</span></span> <span data-ttu-id="82040-279">Clique na seção Criação.</span><span class="sxs-lookup"><span data-stu-id="82040-279">Click Authoring section.</span></span> <span data-ttu-id="82040-280">Clique na seção Regras (sob Criação)</span><span class="sxs-lookup"><span data-stu-id="82040-280">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="82040-281">Na seção regras, encontre a regra com o nome "Main sintética transação Runner desempenho conjunto regra"</span><span class="sxs-lookup"><span data-stu-id="82040-281">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="82040-282">A regra, clique com botão direito e selecione substituições, selecione a regra de substituição e selecione "para todos os objetos da classe: Inspetor de Pool"</span><span class="sxs-lookup"><span data-stu-id="82040-282">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="82040-283">Na janela de substituir propriedades, selecione o nome do parâmetro "Frequência" e defina o valor de substituição para aquela desejada.</span><span class="sxs-lookup"><span data-stu-id="82040-283">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="82040-284">Na mesma janela, selecione o pacote de Gerenciamento ao qual esta substituição deve ser aplicada</span><span class="sxs-lookup"><span data-stu-id="82040-284">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="82040-285">Usando Registro Avançado em Log para Transações Sintéticas</span><span class="sxs-lookup"><span data-stu-id="82040-285">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="82040-286"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="82040-286"></span></span>

<span data-ttu-id="82040-287">As transações sintéticas são extremamente úteis para ajudar a identificar problemas com o sistema.</span><span class="sxs-lookup"><span data-stu-id="82040-287">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="82040-288">Por exemplo, o cmdlet Test-CsRegistration pode alertar os administradores para o fato de que usuários estavam enfrentando dificuldades de registro com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="82040-288">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="82040-289">No entanto, detalhes adicionais podem ser necessários para determinar a causa real de uma falha.</span><span class="sxs-lookup"><span data-stu-id="82040-289">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="82040-p132">Por esse motivo, as transações sintéticas oferecem registro avançado em log. Com o registro avançado em log, para cada atividade assumida por uma transação sintética, as seguintes informações são registradas:</span><span class="sxs-lookup"><span data-stu-id="82040-p132">For this reason, synthetic transactions provide rich logging. With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="82040-292">A hora em que a atividade foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="82040-292">The time that the activity started.</span></span>
    
- <span data-ttu-id="82040-293">A hora em que a atividade foi concluída.</span><span class="sxs-lookup"><span data-stu-id="82040-293">The time that the activity finished.</span></span>
    
- <span data-ttu-id="82040-294">A ação que foi executada (por exemplo, criar, participar ou sair de uma conferência; fazer logon no Skype for Business Server; enviar uma mensagem instantânea).</span><span class="sxs-lookup"><span data-stu-id="82040-294">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="82040-295">Mensagens informativas, detalhadas, de advertência ou de erro geradas quando a atividade foi executada</span><span class="sxs-lookup"><span data-stu-id="82040-295">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="82040-296">Mensagens de registro de SIP.</span><span class="sxs-lookup"><span data-stu-id="82040-296">SIP registration messages.</span></span>
    
- <span data-ttu-id="82040-297">Registros de exceção ou códigos de diagnóstico gerados quando a atividade foi executada.</span><span class="sxs-lookup"><span data-stu-id="82040-297">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="82040-298">O resultado líquido da execução da atividade.</span><span class="sxs-lookup"><span data-stu-id="82040-298">The net result of running the activity.</span></span>
    
<span data-ttu-id="82040-p133">Essas informações são geradas automaticamente sempre que uma transação sintética for executada, mas não são exibidas automaticamente ou salvas em um arquivo de log. Se você estiver executando manualmente uma transação sintética, você pode usar o parâmetro OutLoggerVariable para especificar uma variável do Windows PowerShell no qual as informações serão armazenadas. A partir daqui, você tem a opção de usar um dos dois métodos a seguir para salvar e/ou visualizar mensagens de erro em log avançado no formato XML ou HTML.</span><span class="sxs-lookup"><span data-stu-id="82040-p133">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file. If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored. From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="82040-302">Para recuperar as informações sobre a solução, especifique o parâmetro OutLoggerVariable, seguido por um nome da variável que você escolher:</span><span class="sxs-lookup"><span data-stu-id="82040-302">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="82040-303">: Não preceda o nome da variável com o caractere $.</span><span class="sxs-lookup"><span data-stu-id="82040-303">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="82040-304">Use um nome de variável como RegistrationTest (não $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="82040-304">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="82040-305">Quando executar este comando, você verá um resultado semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="82040-305">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="82040-306">Fqdn de destino: atl-cs-001 resultado: latência de falha: 00:00:00 mensagem de erro: esta máquina não tem todos os certificados atribuídos.</span><span class="sxs-lookup"><span data-stu-id="82040-306">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="82040-307">Diagnóstico: você pode acessar informações muito mais detalhadas para essa falha que apenas a mensagem de erro mostrada aqui.</span><span class="sxs-lookup"><span data-stu-id="82040-307">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="82040-308">Para acessar essas informações em formato HTML, use um comando semelhante a este para salvar as informações armazenadas na variável RegistrationTest em um arquivo HTML:</span><span class="sxs-lookup"><span data-stu-id="82040-308">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="82040-309">Como alternativa, é possível usar o método ToXML() para salvar os dados em um arquivo XML:</span><span class="sxs-lookup"><span data-stu-id="82040-309">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="82040-310">Você pode exibir esses arquivos usando o Windows Internet Explorer, o Microsoft Visual Studio ou qualquer outro aplicativo capaz de abrir arquivos HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="82040-310">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="82040-311">Transações sintéticas executadas a partir de dentro do System Center Operations Manager irá gerar automaticamente esses arquivos de log para falhas.</span><span class="sxs-lookup"><span data-stu-id="82040-311">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="82040-312">Esses logs não serão gerados se a execução falhar antes que o Skype for Business Server PowerShell seja capaz de carregar e executar a transação sintética.</span><span class="sxs-lookup"><span data-stu-id="82040-312">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="82040-313">Por padrão, o  Skype for Business Server 2015 salva arquivos de log em uma pasta que não é compartilhada.</span><span class="sxs-lookup"><span data-stu-id="82040-313">By default, Skype for Business Server 2015 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="82040-314">Para tornar esses logs prontamente acessíveis, é preciso compartilhar essa pasta.</span><span class="sxs-lookup"><span data-stu-id="82040-314">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="82040-315">Por exemplo: \\atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="82040-315">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 