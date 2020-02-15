---
title: Configurar usuários e configurações de teste de nó do Inspetor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Resumo: configurar contas de usuário de teste e configurações do nó do inspetor para transações sintéticas do Skype for Business Server.'
ms.openlocfilehash: 8b586cf4c1d003bb54afa050469a10eee8d113e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005946"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="ffa44-103">Configurar usuários e configurações de teste de nó do Inspetor</span><span class="sxs-lookup"><span data-stu-id="ffa44-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="ffa44-104">**Resumo:** Configurar contas de usuário de teste e configurações do nó do inspetor para transações sintéticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ffa44-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="ffa44-105">Depois de configurar o computador que atuará como um nó do inspetor, você deve:</span><span class="sxs-lookup"><span data-stu-id="ffa44-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="ffa44-106">[Configurar contas de usuário de teste](test-users-and-settings.md#testuser) para serem usadas por esses nós do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="ffa44-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="ffa44-107">Se estiver usando o método de autenticação Negociar, você também deve usar o cmdlet **Set-CsTestUserCredential** para permitir o uso dessas contas de teste no nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="ffa44-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="ffa44-108">Atualizar as definições de configuração do nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="ffa44-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="ffa44-109">Configurar contas de usuário de teste</span><span class="sxs-lookup"><span data-stu-id="ffa44-109">Configure Test User Accounts</span></span>
<span data-ttu-id="ffa44-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="ffa44-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="ffa44-111">As contas de teste não precisam representar pessoas reais, mas devem ser contas válidas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ffa44-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="ffa44-112">Além disso, essas contas devem estar habilitadas para o Skype for Business Server, elas devem ter endereços SIP válidos e devem ser habilitadas para o Enterprise Voice (para usar a transação sintética test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="ffa44-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="ffa44-113">Se você estiver usando o método de autenticação TrustedServer, tudo o que você precisa fazer é verificar se essas contas existem e configurá-las conforme indicado.</span><span class="sxs-lookup"><span data-stu-id="ffa44-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="ffa44-114">Você deve atribuir pelo menos dois usuários de teste para cada pool que você deseja testar.</span><span class="sxs-lookup"><span data-stu-id="ffa44-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="ffa44-115">Se você estiver usando o método de autenticação negociar, você também deve usar o cmdlet Set-CsTestUserCredential e o Shell de gerenciamento do Skype for Business Server para permitir que essas contas de teste funcionem com as transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="ffa44-116">Execute um comando semelhante ao seguinte (estes comandos presumem que as duas contas de usuário do Active Directory tenham sido criadas e que essas contas estejam habilitadas para o Skype for Business Server):</span><span class="sxs-lookup"><span data-stu-id="ffa44-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="ffa44-117">Você deve incluir não apenas o endereço SIP, mas também o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="ffa44-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="ffa44-118">Se você não incluir a senha, o cmdlet Set-CsTestUserCredential solicitará que você insira essas informações.</span><span class="sxs-lookup"><span data-stu-id="ffa44-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="ffa44-119">O nome de usuário pode ser especificado usando o formato de nome de domínio \ mostrado no bloco de código anterior.</span><span class="sxs-lookup"><span data-stu-id="ffa44-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="ffa44-120">Para verificar se as credenciais do usuário de teste foram criadas, execute estes comandos do Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="ffa44-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="ffa44-121">Informações semelhantes a estas serão retornadas para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="ffa44-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="ffa44-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="ffa44-122">**UserName**</span></span>|<span data-ttu-id="ffa44-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="ffa44-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ffa44-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="ffa44-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="ffa44-125">System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="ffa44-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="ffa44-126">Configurar um nó do Inspetor básico com as transações sintéticas padrão</span><span class="sxs-lookup"><span data-stu-id="ffa44-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="ffa44-127">Depois que os usuários de teste tiverem sido criados, você poderá criar um nó do Inspetor usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="ffa44-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="ffa44-128">Esse comando cria um novo nó do inspetor que usa as configurações padrão e executa o conjunto padrão de transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="ffa44-129">O novo nó do Inspetor também usa os usuários de teste watcher1@litwareinc.com e watcher2@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ffa44-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="ffa44-130">Se o nó do Inspetor usar a autenticação TrustedServer, as duas contas de teste poderão ser todas as contas de usuário válidas habilitadas para o Active Directory e o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ffa44-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="ffa44-131">Se o nó do Inspetor usar o método de autenticação Negotiate, essas contas de usuário também deverão ser habilitadas para o nó do observador usando o cmdlet Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="ffa44-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="ffa44-132">Para validar que a descoberta automática do pool de destino para entrar está configurada corretamente em vez de direcionar um pool diretamente, use estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ffa44-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="ffa44-133">Configurando testes estendidos</span><span class="sxs-lookup"><span data-stu-id="ffa44-133">Configuring Extended Tests</span></span>

<span data-ttu-id="ffa44-134">Se você deseja habilitar o teste PSTN, que verifica a conectividade com a rede telefônica pública comutada, você precisa fazer algumas configurações adicionais ao configurar o nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="ffa44-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="ffa44-135">Primeiro, você deve associar seus usuários de teste com o tipo de teste PSTN executando um comando semelhante a este no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="ffa44-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="ffa44-136">Os resultados desse comando devem ser armazenados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="ffa44-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="ffa44-137">Neste exemplo, a variável é nomeada $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="ffa44-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="ffa44-138">Em seguida, você pode usar o cmdlet **New-CsWatcherNodeConfiguration** para associar o tipo de teste (armazenado na variável $pstnTest) a um pool do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ffa44-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="ffa44-139">Por exemplo, o comando a seguir cria uma nova configuração de nó do observador para o pool atl-cs-001.litwareinc.com, adicionando os dois usuários de teste criados anteriormente e adicionando o tipo de teste PSTN:</span><span class="sxs-lookup"><span data-stu-id="ffa44-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="ffa44-140">O comando anterior falhará se você não tiver instalado os arquivos de núcleo do Skype for Business Server e o banco de dados RTCLocal no computador do nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="ffa44-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="ffa44-141">Para testar várias políticas de voz, você pode criar um teste estendido para cada política usando o cmdlet **New-CsExtendedTest** .</span><span class="sxs-lookup"><span data-stu-id="ffa44-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="ffa44-142">Os usuários fornecidos devem ser configurados com as políticas de voz desejadas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="ffa44-143">Os testes estendidos são passados para o cmdlet **New-CsWatcherNodeConfiguration** usando delimitadores de vírgula, como:</span><span class="sxs-lookup"><span data-stu-id="ffa44-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="ffa44-144">-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="ffa44-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="ffa44-145">Como o cmdlet **New-CsWatcherNodeConfiguration** foi chamado sem usar o parâmetro tests, somente as transações sintéticas padrão (e a transação sintética estendida especificada) serão habilitadas para o novo nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="ffa44-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="ffa44-146">Portanto, o nó do Inspetor testará os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="ffa44-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="ffa44-147">Registro</span><span class="sxs-lookup"><span data-stu-id="ffa44-147">Registration</span></span>
    
- <span data-ttu-id="ffa44-148">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="ffa44-148">IM</span></span>
    
- <span data-ttu-id="ffa44-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="ffa44-149">GroupIM</span></span>
    
- <span data-ttu-id="ffa44-150">P2PAV (sessões de áudio/vídeo ponto a ponto)</span><span class="sxs-lookup"><span data-stu-id="ffa44-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="ffa44-151">AvConference (áudio/conferência)</span><span class="sxs-lookup"><span data-stu-id="ffa44-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="ffa44-152">Presença</span><span class="sxs-lookup"><span data-stu-id="ffa44-152">Presence</span></span>
    
- <span data-ttu-id="ffa44-153">ABS (serviço do Catálogo de Endereços)</span><span class="sxs-lookup"><span data-stu-id="ffa44-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="ffa44-154">ABWQ (serviço Web do Catálogo de Endereços)</span><span class="sxs-lookup"><span data-stu-id="ffa44-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="ffa44-155">Os seguintes componentes não serão testados por padrão:</span><span class="sxs-lookup"><span data-stu-id="ffa44-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="ffa44-156">Asconferência</span><span class="sxs-lookup"><span data-stu-id="ffa44-156">ASConference</span></span>
    
- <span data-ttu-id="ffa44-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="ffa44-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="ffa44-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="ffa44-158">DataConference</span></span>
    
- <span data-ttu-id="ffa44-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="ffa44-159">DialinConferencing</span></span>
    
- <span data-ttu-id="ffa44-160">ExumConnectivity (Unificação de Mensagens do Exchange)</span><span class="sxs-lookup"><span data-stu-id="ffa44-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="ffa44-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="ffa44-161">JoinLauncher</span></span>
    
- <span data-ttu-id="ffa44-162">MCXP2PIM (mensagens instantâneas de dispositivos móveis herdados)</span><span class="sxs-lookup"><span data-stu-id="ffa44-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="ffa44-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="ffa44-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="ffa44-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="ffa44-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="ffa44-165">PSTN (chamadas de gateway PSTN, especificadas como teste estendido)</span><span class="sxs-lookup"><span data-stu-id="ffa44-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="ffa44-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="ffa44-166">UcwaConference</span></span>
    
- <span data-ttu-id="ffa44-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="ffa44-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="ffa44-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="ffa44-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="ffa44-169">Adicionando e removendo Transações sintéticas</span><span class="sxs-lookup"><span data-stu-id="ffa44-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="ffa44-170">Depois que um nó do inspetor é configurado, é possível usar o cmdlet Set-CsWatcherNodeConfiguration para adicionar ou remover transações sintéticas do nó.</span><span class="sxs-lookup"><span data-stu-id="ffa44-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="ffa44-171">Por exemplo, para adicionar o teste PersistentChatMessage ao nó do inspetor, use o método Adicionar e um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="ffa44-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="ffa44-172">É possível adicionar vários testes separando os nomes de teste com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="ffa44-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ffa44-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="ffa44-174">Ocorrerá um erro se um ou mais desses testes (por exemplo, dataconferência) já tiverem sido habilitados no nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="ffa44-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="ffa44-175">Nesse caso, você receberá uma mensagem de erro semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="ffa44-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="ffa44-176">Set-CsWatcherNodeConfiguration: há uma sequência de chave duplicada ' dataconferência ' para a chave ' urn: Schema: Microsoft. RTC. Management. Settings. WatcherNode. 2010: TestName ' ou a restrição Identity exclusiva.</span><span class="sxs-lookup"><span data-stu-id="ffa44-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="ffa44-177">Quando esse erro ocorre, nenhuma alteração será aplicada.</span><span class="sxs-lookup"><span data-stu-id="ffa44-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="ffa44-178">O comando deve ser executado novamente com o teste de duplicata removido.</span><span class="sxs-lookup"><span data-stu-id="ffa44-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="ffa44-179">Para remover uma transação sintética de um nó do Inspetor, use o método remove.</span><span class="sxs-lookup"><span data-stu-id="ffa44-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="ffa44-180">Por exemplo, esse comando remove o teste ABWQ do nó do inspetor:</span><span class="sxs-lookup"><span data-stu-id="ffa44-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="ffa44-181">Você pode usar o método Replace para substituir todos os testes atualmente habilitados por um ou mais testes novos.</span><span class="sxs-lookup"><span data-stu-id="ffa44-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="ffa44-182">Por exemplo, se você deseja que um nó do Inspetor apenas execute o teste de mensagens instantâneas, é possível configurá-lo usando este comando:</span><span class="sxs-lookup"><span data-stu-id="ffa44-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="ffa44-183">Quando você executar este comando, todas as transações sintéticas no nó do Inspetor especificado serão desabilitadas, exceto para IM.</span><span class="sxs-lookup"><span data-stu-id="ffa44-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="ffa44-184">Exibindo e testando a configuração do nó inspetor</span><span class="sxs-lookup"><span data-stu-id="ffa44-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="ffa44-185">Se quiser exibir os testes que foram atribuídos ao nó do inspetor, use um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="ffa44-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="ffa44-186">Este comando retornará informações semelhantes a isso, dependendo das transações sintéticas que foram atribuídas ao nó:</span><span class="sxs-lookup"><span data-stu-id="ffa44-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="ffa44-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage dataconferência</span><span class="sxs-lookup"><span data-stu-id="ffa44-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="ffa44-188">Para exibir as transações sintéticas em ordem alfabética, use este comando:</span><span class="sxs-lookup"><span data-stu-id="ffa44-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="ffa44-189">Para verificar se um nó do inspetor foi criado, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="ffa44-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="ffa44-190">Você receberá informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="ffa44-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="ffa44-191">Identidade: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ffa44-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="ffa44-192">Testusers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="ffa44-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="ffa44-193">ExtendedTests: {testusers = IList<System. String>; Name = teste PSTN; Te...}</span><span class="sxs-lookup"><span data-stu-id="ffa44-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="ffa44-194">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ffa44-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="ffa44-195">PortNumber: 5061</span><span class="sxs-lookup"><span data-stu-id="ffa44-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="ffa44-196">Para verificar se o nó do inspetor foi configurado corretamente, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="ffa44-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="ffa44-197">Este comando testará cada nó do Inspetor em sua implantação e confirmará se as seguintes ações foram concluídas:</span><span class="sxs-lookup"><span data-stu-id="ffa44-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="ffa44-198">A função registrador necessária está instalada.</span><span class="sxs-lookup"><span data-stu-id="ffa44-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="ffa44-199">A chave de registro necessária é criada (concluída quando você executou o cmdlet Set-CsWatcherNodeConfiguration).</span><span class="sxs-lookup"><span data-stu-id="ffa44-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="ffa44-200">Seus servidores estão executando a versão correta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ffa44-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="ffa44-201">Suas portas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="ffa44-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="ffa44-202">Seus usuários de teste atribuídos têm as credenciais necessárias.</span><span class="sxs-lookup"><span data-stu-id="ffa44-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="ffa44-203">Gerenciar nós do Inspetor</span><span class="sxs-lookup"><span data-stu-id="ffa44-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="ffa44-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="ffa44-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="ffa44-205">Além de modificar as transações sintéticas que são executadas em um nó do Inspetor, você também pode usar o cmdlet **set-CsWatcherNodeConfiguration** para executar duas outras tarefas importantes: habilitar e desabilitar o nó do Inspetor e configurar o nó do inspetor para usar URLs internas da Web ou URLs da Web externas ao executar seus testes.</span><span class="sxs-lookup"><span data-stu-id="ffa44-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="ffa44-206">Por padrão, os nós do Inspetor foram projetados para executar periodicamente todas as suas transações sintéticas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="ffa44-207">Às vezes, no entanto, você pode querer suspender essas transações.</span><span class="sxs-lookup"><span data-stu-id="ffa44-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="ffa44-208">Por exemplo, se o nó do Inspetor estiver desconectado temporariamente da rede, não haverá motivo para executar as transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="ffa44-209">Sem conectividade de rede, essas transações falharão.</span><span class="sxs-lookup"><span data-stu-id="ffa44-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="ffa44-210">Para desabilitar temporariamente um nó do Inspetor, execute um comando semelhante a este no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="ffa44-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="ffa44-211">Este comando desabilitará a execução de transações sintéticas no nó do Inspetor 001.litwareinc.com do Inspetor do ATL.</span><span class="sxs-lookup"><span data-stu-id="ffa44-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="ffa44-212">Para retomar a execução das transações sintéticas, defina a propriedade Enabled de volta como true ($True):</span><span class="sxs-lookup"><span data-stu-id="ffa44-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="ffa44-213">A propriedade Enabled pode ser usada para ativar ou desativar os nós do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="ffa44-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="ffa44-214">Se você quiser excluir permanentemente um nó do Inspetor, use o cmdlet **Remove-CsWatcherNodeConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="ffa44-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="ffa44-215">Esse comando Remove todas as definições de configuração do nó do observador do computador especificado, o que impede que o computador execute transações sintéticas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ffa44-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="ffa44-216">No entanto, o comando não desinstala os arquivos do agente do System Center ou os arquivos de sistema do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ffa44-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="ffa44-217">Por padrão, os nós do Inspetor usam as URLs da Web externas da organização ao conduzir testes.</span><span class="sxs-lookup"><span data-stu-id="ffa44-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="ffa44-218">No entanto, os nós do Inspetor também podem ser configurados para usar as URLs da Web internas da organização.</span><span class="sxs-lookup"><span data-stu-id="ffa44-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="ffa44-219">Isso permite que os administradores verifiquem o acesso à URL para usuários localizados dentro da rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="ffa44-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="ffa44-220">Para configurar um nó do inspetor para usar URLs internas em vez de URLs externas, defina a propriedade UseInternalWebURls como true ($True):</span><span class="sxs-lookup"><span data-stu-id="ffa44-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="ffa44-221">A redefinição dessa propriedade para o valor padrão false ($False) fará com que o Inspetor mais uma vez use as URLs externas:</span><span class="sxs-lookup"><span data-stu-id="ffa44-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="ffa44-222">Instruções Especiais de Configuração para Transações Sintéticas</span><span class="sxs-lookup"><span data-stu-id="ffa44-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="ffa44-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="ffa44-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="ffa44-224">A maioria das transações sintéticas pode ser executada em um nó do Inspetor como está.</span><span class="sxs-lookup"><span data-stu-id="ffa44-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="ffa44-225">Na maioria dos casos, assim que a transação sintética é adicionada às definições de configuração do nó do observador, o nó do Inspetor pode começar a usar essa transação sintética durante o teste.</span><span class="sxs-lookup"><span data-stu-id="ffa44-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="ffa44-226">No entanto, há algumas transações sintéticas que exigem instruções de configuração especiais, conforme discutido nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="ffa44-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="ffa44-227">Transação sintética de conferência de dados</span><span class="sxs-lookup"><span data-stu-id="ffa44-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="ffa44-228">Se o computador do nó do observador estiver localizado fora da rede de perímetro, provavelmente você não poderá executar a transação sintética da conferência de dados, a menos que primeiro desabilite o Windows Internet Explorer® configurações de proxy do navegador da Internet para a rede Conta de serviço realizando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ffa44-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="ffa44-229">No computador do nó do Inspetor, clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="ffa44-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="ffa44-230">Na janela do console, digite o seguinte comando e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="ffa44-230">In the console window, type the following command and then press ENTER.</span></span> 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    <span data-ttu-id="ffa44-231">Você verá a seguinte mensagem exibida na janela de comando:</span><span class="sxs-lookup"><span data-stu-id="ffa44-231">You will see the following message displayed in the command window:</span></span>

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    <span data-ttu-id="ffa44-232">Essa mensagem indica que você desabilitou as configurações de proxy do Internet Explorer para a conta de serviço de rede.</span><span class="sxs-lookup"><span data-stu-id="ffa44-232">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="ffa44-233">Transação sintética de Unificação de mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="ffa44-233">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="ffa44-234">A transação sintética de Unificação de mensagens (UM) do Exchange verifica se os usuários de teste podem se conectar às contas de caixa postal hospedadas no Exchange.</span><span class="sxs-lookup"><span data-stu-id="ffa44-234">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="ffa44-235">Os usuários de teste precisarão ser pré-configurados com contas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="ffa44-235">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="ffa44-236">Transação sintética de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ffa44-236">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="ffa44-237">Para usar a transação sintética de chat persistente, você deve primeiro criar um canal e conceder permissões aos usuários de teste para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="ffa44-237">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="ffa44-238">Você pode usar a transação sintética de chat persistente para configurar este canal:</span><span class="sxs-lookup"><span data-stu-id="ffa44-238">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="ffa44-239">Você deve executar esta tarefa de configuração para ser executada de dentro da empresa:</span><span class="sxs-lookup"><span data-stu-id="ffa44-239">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="ffa44-240">Se executado de uma máquina não servidor, o usuário que executa o cmdlet deve ser um membro da função CsPersistentChatAdministrators para o controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="ffa44-240">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="ffa44-241">Se executado no próprio servidor, o usuário que executa o cmdlet deve ser um membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ffa44-241">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="ffa44-242">Transação sintética de chamada ponto a ponto PSTN</span><span class="sxs-lookup"><span data-stu-id="ffa44-242">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="ffa44-243">A transação sintética test-CsPstnPeerToPeerCall verifica a capacidade de colocar e receber chamadas através de uma PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="ffa44-243">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="ffa44-244">Para executar essa transação sintética, você deve configurar:</span><span class="sxs-lookup"><span data-stu-id="ffa44-244">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="ffa44-245">Dois usuários de teste habilitados para UC (um chamador e um receptor).</span><span class="sxs-lookup"><span data-stu-id="ffa44-245">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="ffa44-246">Números DID (Discagem Interna Direta) para cada conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ffa44-246">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="ffa44-247">Políticas de VoIP e rotas de voz que permitem que chamadas para o número do receptor cheguem ao gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ffa44-247">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="ffa44-248">Um gateway PSTN que aceita chamadas e mídias que roteiam chamadas de volta para o pool de casa de um receptor, com base no número discado.</span><span class="sxs-lookup"><span data-stu-id="ffa44-248">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="ffa44-249">Transação sintética do repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="ffa44-249">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="ffa44-250">A transação sintética do repositório unificado de contatos verifica a capacidade do Skype for Business Server de recuperar contatos em nome de um usuário do Exchange.</span><span class="sxs-lookup"><span data-stu-id="ffa44-250">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="ffa44-251">Para usar essa transação sintética, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="ffa44-251">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="ffa44-252">Lyss-a autenticação do Exchange Server para servidor deve ser configurada.</span><span class="sxs-lookup"><span data-stu-id="ffa44-252">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="ffa44-253">Os usuários de teste devem ter uma caixa de correio do Exchange válida.</span><span class="sxs-lookup"><span data-stu-id="ffa44-253">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="ffa44-254">Depois que essas condições forem atendidas, você pode executar o seguinte cmdlet do Windows PowerShell para migrar as listas de contatos dos usuários de teste para o Exchange:</span><span class="sxs-lookup"><span data-stu-id="ffa44-254">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="ffa44-255">Pode levar algum tempo para que as listas de contatos de usuário de teste migrem para o Exchange.</span><span class="sxs-lookup"><span data-stu-id="ffa44-255">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="ffa44-256">Para monitorar o progresso da migração, a mesma linha de comando pode ser executada sem o sinalizador de instalação:</span><span class="sxs-lookup"><span data-stu-id="ffa44-256">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="ffa44-257">Essa linha de comando será bem-sucedida após a conclusão da migração.</span><span class="sxs-lookup"><span data-stu-id="ffa44-257">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="ffa44-258">Transação sintética XMPP</span><span class="sxs-lookup"><span data-stu-id="ffa44-258">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="ffa44-259">A transação sintética de IM XMPP (Extensible Messaging and Presence Protocol) exige que você configure o recurso XMPP com um ou mais domínios federados.</span><span class="sxs-lookup"><span data-stu-id="ffa44-259">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="ffa44-260">Para habilitar a transação sintética XMPP, você deve fornecer um parâmetro XmppTestReceiverMailAddress com uma conta de usuário em um domínio XMPP roteável.</span><span class="sxs-lookup"><span data-stu-id="ffa44-260">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="ffa44-261">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ffa44-261">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="ffa44-262">Neste exemplo, uma regra do Skype for Business Server precisará existir para rotear mensagens para o litwareinc.com para um Gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="ffa44-262">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="ffa44-263">Os gateways e proxies do XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ffa44-263">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ffa44-264">Consulte [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ffa44-264">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="ffa44-265">Transação sintética de VIS (servidor de interoperabilidade de vídeo)</span><span class="sxs-lookup"><span data-stu-id="ffa44-265">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="ffa44-266">A transação sintética do VIS (servidor de interoperabilidade de vídeo) exige que você baixe e instale os arquivos de suporte de transação sintética ([VISSTSupportPackage. msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="ffa44-266">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="ffa44-267">Para instalar o VISSTSupportPackage. msi, verifique se as dependências (em requisitos do sistema) para o MSI já estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-267">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="ffa44-268">Execute o VISSTSupportPackage. msi para fazer uma instalação simples.</span><span class="sxs-lookup"><span data-stu-id="ffa44-268">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="ffa44-269">O. msi instala todos os arquivos no seguinte caminho: "pacote de suporte à transação sintética do%ProgramFiles%\VIS".</span><span class="sxs-lookup"><span data-stu-id="ffa44-269">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="ffa44-270">Para obter mais detalhes sobre como executar a transação sintética do VIS, consulte a documentação do cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ffa44-270">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="ffa44-271">Alterar a frequência de execução de transações sintéticas</span><span class="sxs-lookup"><span data-stu-id="ffa44-271">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="ffa44-272"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="ffa44-272"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="ffa44-273">Por padrão, as transações sintéticas serão executadas com os usuários configurados a cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="ffa44-273">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="ffa44-274">As transações sintéticas são executadas de forma seqüencial dentro de um conjunto de usuários para evitar que duas transações sintéticas entrem em conflito entre si.</span><span class="sxs-lookup"><span data-stu-id="ffa44-274">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="ffa44-275">Um intervalo mais longo é necessário para fornecer tempo para que todas as transações sintéticas sejam concluídas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-275">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="ffa44-276">Se for desejável executar transações sintéticas com mais frequência, o número de transações sintéticas executadas com um determinado conjunto de usuários deve ser reduzido para que os testes possam ser concluídos no intervalo de tempo desejado com algum buffer para atrasos de rede ocasionais.</span><span class="sxs-lookup"><span data-stu-id="ffa44-276">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="ffa44-277">Se a execução de mais transações sintéticas for desejável, crie mais conjuntos de usuários para executar transações sintéticas adicionais.</span><span class="sxs-lookup"><span data-stu-id="ffa44-277">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="ffa44-278">Para alterar a frequência na qual as transações sintéticas são executadas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ffa44-278">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="ffa44-279">Abra o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ffa44-279">Open System Center Operations Manager.</span></span> <span data-ttu-id="ffa44-280">Clique em seção de criação.</span><span class="sxs-lookup"><span data-stu-id="ffa44-280">Click Authoring section.</span></span> <span data-ttu-id="ffa44-281">Clique em seção de regras (em criação).</span><span class="sxs-lookup"><span data-stu-id="ffa44-281">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="ffa44-282">Na seção regras, localize a regra com o nome "regra de coleta de desempenho do executor de transações sintéticas" principal.</span><span class="sxs-lookup"><span data-stu-id="ffa44-282">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="ffa44-283">Clique com o botão direito do mouse na regra e selecione substituições, selecione substituir a regra e, em seguida, selecione "para todos os objetos da classe: Inspetor de pool".</span><span class="sxs-lookup"><span data-stu-id="ffa44-283">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="ffa44-284">Na janela substituir Propriedades, selecione nome do parâmetro "frequência" e defina o valor de substituição para o desejado.</span><span class="sxs-lookup"><span data-stu-id="ffa44-284">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="ffa44-285">Na mesma janela, selecione o pacote de gerenciamento para o qual essa substituição precisa ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="ffa44-285">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="ffa44-286">Usando Registro em Log Sofisticado para Transações Sintéticas</span><span class="sxs-lookup"><span data-stu-id="ffa44-286">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="ffa44-287"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="ffa44-287"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="ffa44-288">As transações sintéticas são extremamente úteis para ajudar a identificar problemas com o sistema.</span><span class="sxs-lookup"><span data-stu-id="ffa44-288">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="ffa44-289">Por exemplo, o cmdlet Test-CsRegistration poderia alertar os administradores sobre o fato de que os usuários estavam tendo dificuldade para registrar-se no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ffa44-289">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="ffa44-290">No entanto, detalhes adicionais podem ser necessários para determinar a causa real de uma falha.</span><span class="sxs-lookup"><span data-stu-id="ffa44-290">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="ffa44-291">Por esse motivo, as transações sintéticas fornecem logs avançados.</span><span class="sxs-lookup"><span data-stu-id="ffa44-291">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="ffa44-292">Com o registro em log avançado, para cada atividade que uma transação sintética é executada, as seguintes informações são registradas:</span><span class="sxs-lookup"><span data-stu-id="ffa44-292">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="ffa44-293">A hora em que a atividade foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="ffa44-293">The time that the activity started.</span></span>
    
- <span data-ttu-id="ffa44-294">A hora em que a atividade foi concluída.</span><span class="sxs-lookup"><span data-stu-id="ffa44-294">The time that the activity finished.</span></span>
    
- <span data-ttu-id="ffa44-295">A ação que foi executada (por exemplo, criar, ingressar ou sair de uma conferência; fazer logon no Skype for Business Server; enviar uma mensagem instantânea).</span><span class="sxs-lookup"><span data-stu-id="ffa44-295">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="ffa44-296">Mensagens informativas, detalhadas, de aviso ou de erro geradas quando a atividade foi executada.</span><span class="sxs-lookup"><span data-stu-id="ffa44-296">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="ffa44-297">Mensagens de registro SIP.</span><span class="sxs-lookup"><span data-stu-id="ffa44-297">SIP registration messages.</span></span>
    
- <span data-ttu-id="ffa44-298">Registros de exceção ou códigos de diagnóstico gerados quando a atividade foi executada.</span><span class="sxs-lookup"><span data-stu-id="ffa44-298">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="ffa44-299">O resultado líquido da execução da atividade.</span><span class="sxs-lookup"><span data-stu-id="ffa44-299">The net result of running the activity.</span></span>
    
<span data-ttu-id="ffa44-300">Essas informações são geradas automaticamente cada vez que uma transação sintética é executada, mas não é automaticamente exibida ou salva em um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="ffa44-300">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="ffa44-301">Se você estiver executando uma transação sintética manualmente, poderá usar o parâmetro OutLoggerVariable para especificar uma variável do Windows PowerShell na qual as informações serão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-301">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="ffa44-302">A partir daí, você tem a opção de usar um dos dois métodos para salvar e/ou exibir mensagens de erro no log avançado em formato XML ou HTML.</span><span class="sxs-lookup"><span data-stu-id="ffa44-302">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="ffa44-303">Para recuperar as informações de solução de problemas, especifique o parâmetro OutLoggerVariable, seguido de um nome de variável que você escolher:</span><span class="sxs-lookup"><span data-stu-id="ffa44-303">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="ffa44-304">Não use o caractere $ como prefixo do nome da variável.</span><span class="sxs-lookup"><span data-stu-id="ffa44-304">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="ffa44-305">Use um nome de variável como RegistrationTest (não $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="ffa44-305">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="ffa44-306">Ao executar este comando, você verá um resultado semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="ffa44-306">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="ffa44-307">FQDN de destino: atl-cs-001.litwareinc.com resultado: latência de falha: 00:00:00 mensagem de erro: esta máquina não tem nenhum certificado atribuído.</span><span class="sxs-lookup"><span data-stu-id="ffa44-307">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="ffa44-308">Diagnóstico: você pode acessar informações muito mais detalhadas para essa falha do que apenas a mensagem de erro mostrada aqui.</span><span class="sxs-lookup"><span data-stu-id="ffa44-308">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="ffa44-309">Para acessar essas informações no formato HTML, use um comando semelhante a este para salvar as informações armazenadas na variável RegistrationTest em um arquivo HTML:</span><span class="sxs-lookup"><span data-stu-id="ffa44-309">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="ffa44-310">Como alternativa, é possível usar o método ToXML() para salvar os dados em um arquivo XML:</span><span class="sxs-lookup"><span data-stu-id="ffa44-310">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="ffa44-311">Você pode exibir esses arquivos usando o Windows Internet Explorer, o Microsoft Visual Studio ou qualquer outro aplicativo capaz de abrir arquivos HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="ffa44-311">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="ffa44-312">As transações sintéticas executadas de dentro do System Center Operations Manager gerarão automaticamente esses arquivos de log para falhas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-312">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="ffa44-313">Esses logs não serão gerados se a execução falhar antes do Skype for Business Server PowerShell poder carregar e executar a transação sintética.</span><span class="sxs-lookup"><span data-stu-id="ffa44-313">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ffa44-314">Por padrão, o Skype for Business Server salva arquivos de log em uma pasta que não é compartilhada.</span><span class="sxs-lookup"><span data-stu-id="ffa44-314">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="ffa44-315">Para tornar esses logs prontamente acessíveis, você deve compartilhar esta pasta.</span><span class="sxs-lookup"><span data-stu-id="ffa44-315">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="ffa44-316">Por exemplo: \\ATL-Watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="ffa44-316">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
