---
title: Como configurar os usuários e as configurações de teste do nó do watcher
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: Como configurar contas de usuário de teste e configurações de nó do watcher para Skype for Business Server transações sintéticas.
ms.openlocfilehash: e21842550da1a5a96c96cef5ac7e8c728777799b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849754"
---
# <a name="how-to-configure-watcher-node-test-users-and-settings"></a>Como configurar os usuários e as configurações de teste do nó do watcher
 
**Resumo:** Configure as contas de usuário de teste e as configurações do nó do watcher para Skype for Business Server transações sintéticas.
  
Depois de configurar o computador que atuará como um nó do inspetor, você deve:
  
1. [Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes. Se estiver usando o método de autenticação Negociar, você também deve usar o cmdlet **Set-CsTestUserCredential** para permitir o uso dessas contas de teste no nó do inspetor.
    
2. Atualizar as definições de configuração do nó do inspetor.
    
## <a name="configure-test-user-accounts"></a>Configurar contas de usuário de teste
<a name="testuser"> </a>

As contas de teste não precisam representar pessoas reais, mas devem ser contas válidas do Active Directory. Além disso, essas contas devem ser habilitadas para Skype for Business Server, elas devem ter endereços SIP válidos e devem ser habilitadas para Enterprise Voice (para usar Test-CsPstnPeerToPeerCall transação sintética). 
  
Se você estiver usando o método de autenticação TrustedServer, tudo o que você precisa fazer é garantir que essas contas existam e configurá-las como notadas. Atribua pelo menos dois usuários de teste para cada pool que você deseja testar. Se você estiver usando o método de autenticação Negociar, também deverá usar o cmdlet Set-CsTestUserCredential e o Shell de Gerenciamento Skype for Business Server para permitir que essas contas de teste funcionem com as transações sintéticas. Faça isso executando um comando semelhante ao seguinte (esses comandos pressuem que as duas contas de usuário do Active Directory foram criadas e que essas contas estão habilitadas para Skype for Business Server):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

Você deve incluir não apenas o endereço SIP, mas também o nome de usuário e a senha. Se você não incluir a senha, o cmdlet Set-CsTestUserCredential solicitará que você insira essas informações. O nome de usuário pode ser especificado usando o nome de domínio\formato de nome de usuário mostrado no bloco de código anterior.
  
Para verificar se as credenciais de usuário de teste foram criadas, execute esses comandos no Shell de Gerenciamento Skype for Business Server de teste:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Informações semelhantes às seguintes serão retornadas para cada usuário:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurar um nó do Watcher Básico com as Transações Sintéticas Padrão

Depois que os usuários de teste foram criados, você pode criar um nó do watcher usando um comando semelhante a este:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Esse comando cria um novo nó do inspetor que usa as configurações padrão e executa o conjunto padrão de transações sintéticas. O novo nó do watcher também usa os usuários de teste watcher1@litwareinc.com e watcher2@litwareinc.com. Se o nó do watcher usar a autenticação TrustedServer, as duas contas de teste poderão ser contas de usuário válidas habilitadas para o Active Directory e Skype for Business Server. Se o nó do watcher usar o método negociar autenticação, essas contas de usuário também devem ser habilitadas para o nó do watcher usando o cmdlet Set-CsTestUserCredential.
  
Para validar que a descoberta automática do pool de destino para entrar está configurada corretamente, em vez de direcionar um pool, use essas etapas diretamente:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configurando testes estendidos

Se você quiser habilitar o teste PSTN, que verifica a conectividade com a rede telefônica pública comutado, você precisa fazer alguma configuração adicional ao configurar o nó do verificador. Primeiro, você deve associar seus usuários de teste ao tipo de teste PSTN executando um comando semelhante a este no Shell de Gerenciamento Skype for Business Server:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Os resultados desse comando devem ser armazenados em uma variável. Neste exemplo, a variável é chamada $pstnTest. 
  
Em seguida, você pode usar o cmdlet **New-CsWatcherNodeConfiguration** para associar o tipo de teste (armazenado na variável $pstnTest) a um pool Skype for Business Server. Por exemplo, o comando a seguir cria uma nova configuração de nó do atl-cs-001.litwareinc.com do pool, adicionando os dois usuários de teste criados anteriormente e adicionando o tipo de teste PSTN:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

O comando anterior falhará se você não tiver instalado os arquivos Skype for Business Server principais e o banco de dados RTCLocal no computador do nó do watcher. 
  
Para testar várias políticas de voz, você pode criar um teste estendido para cada política usando o cmdlet **New-CsExtendedTest.** Os usuários fornecidos devem ser configurados com as políticas de voz desejadas. Os testes estendidos são passados para o cmdlet **New-CsWatcherNodeConfiguration** usando delimitadores de vírgula, como:
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
Como o cmdlet **New-CsWatcherNodeConfiguration** foi chamado sem usar o parâmetro Tests, somente as transações sintéticas padrão (e a transação sintética estendida especificada) serão habilitadas para o novo nó do watcher. Portanto, o nó do watcher testará os seguintes componentes:
  
- Registro
    
- Mensagens instantâneas
    
- GroupIM
    
- P2PAV (sessões de áudio/vídeo ponto a ponto)
    
- AvConference (áudio/conferência)
    
- Presença
    
- ABS (serviço do Catálogo de Endereços)
    
- ABWQ (serviço Web do Catálogo de Endereços)
    
Os seguintes componentes não serão testados por padrão:
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Unificação de Mensagens do Exchange)
    
- JoinLauncher
    
- MCXP2PIM (mensagens instantâneas de dispositivo móvel herdado)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (chamadas de gateway PSTN, especificadas como um teste estendido)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Adicionando e removendo Transações sintéticas

Depois que um nó do inspetor é configurado, é possível usar o cmdlet Set-CsWatcherNodeConfiguration para adicionar ou remover transações sintéticas do nó. Por exemplo, para adicionar o teste PersistentChatMessage ao nó do inspetor, use o método Adicionar e um comando semelhante a este:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

É possível adicionar vários testes separando os nomes de teste com vírgulas. Por exemplo:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Ocorrerá um erro se um ou mais desses testes (por exemplo, DataConference) já tiver sido habilitado no nó do watcher. Nesse caso, você receberá uma mensagem de erro semelhante a esta:
  
Set-CsWatcherNodeConfiguration : há uma sequência de chaves duplicada 'DataConference' para a 'urn:schema:Microsoft.Rtc.Management. Configurações. WatcherNode.2010:TestName' key or unique identity constraint.
  
Quando esse erro ocorre, nenhuma alteração será aplicada. O comando deve ser executado de novo com o teste duplicado removido.
  
Para remover uma transação sintética de um nó do watcher, use o método Remove. Por exemplo, esse comando remove o teste ABWQ do nó do inspetor:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Você pode usar o método Replace para substituir todos os testes habilitados no momento por um ou mais novos testes. Por exemplo, se você quiser que um nó do watcher execute apenas o teste de IM, você pode configurá-lo usando este comando:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Quando você executar esse comando, todas as transações sintéticas no nó do watcher especificado serão desabilitadas, exceto por IM.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Exibindo e testando a configuração do nó inspetor

Se quiser exibir os testes que foram atribuídos ao nó do inspetor, use um comando semelhante a este:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Este comando retornará informações semelhantes a essa, dependendo das transações sintéticas atribuídas ao nó:
  
GroupIM de IM de Registro P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> Para exibir as transações sintéticas em ordem alfabética, use este comando: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Para verificar se um nó do watcher foi criado, digite o seguinte comando do Shell de Gerenciamento Skype for Business Server:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Você receberá informações semelhantes a esta:
  
Identidade : atl-cs-001.litwareinc.com <br/>
TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}<br/>
ExtendedTests : {TestUsers=IList<System.String>; Teste Name=PSTN; Te...}<br/>
TargetFqdn : atl-cs-001.litwareinc.com<br/>
PortNumber : 5061<br/>

Para verificar se o nó do watcher foi configurado corretamente, digite o seguinte comando do Shell de Gerenciamento Skype for Business Server:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Este comando testará cada nó do watcher em sua implantação e confirmará se as seguintes ações foram concluídas:
  
- A função de Registrador necessária está instalada.
    
- A chave de registro necessária é criada (concluída quando você Set-CsWatcherNodeConfiguration cmdlet).
    
- Seus servidores estão executando a versão correta do Skype for Business Server.
    
- Suas portas estão configuradas corretamente.
    
- Seus usuários de teste atribuídos têm as credenciais necessárias.
    
## <a name="managing-watcher-nodes"></a>Gerenciando nós do Watcher
<a name="testuser"> </a>

Além de modificar as transações sintéticas executadas em um nó do watcher, você também pode usar o cmdlet **Set-CsWatcherNodeConfiguration** para realizar duas outras tarefas importantes: habiltar e desabilitar o nó do watcher e configurar o nó do watcher para usar URLs Web internas ou URLs web externas ao executar seus testes.
  
Por padrão, os nós do watcher são projetados para executar periodicamente todas as transações sintéticas habilitadas. Às vezes, no entanto, talvez você queira suspender essas transações. Por exemplo, se o nó do watcher estiver temporariamente desconectado da rede, não há motivo para executar as transações sintéticas. Sem conectividade de rede, essas transações falharão. Para desabilitar temporariamente um nó do watcher, execute um comando semelhante a este no Shell de Gerenciamento Skype for Business Server:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Este comando desabilitará a execução de transações sintéticas no nó do watcher atl watcher 001.litwareinc.com. Para retomar a execução das transações sintéticas, de definir a propriedade Enabled de volta como True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> A propriedade Enabled pode ser usada para ativar ou desativar nós do watcher. Se você quiser excluir permanentemente um nó do watcher, use o cmdlet **Remove-CsWatcherNodeConfiguration:**
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Esse comando remove todas as configurações do nó do watcher do computador especificado, o que impede que o computador executa automaticamente transações sintéticas. No entanto, o comando não desinstala os arquivos System Center do agente ou os arquivos Skype for Business Server do sistema.
  
Por padrão, nós do watcher usam URLs Web externas de uma organização ao realizar testes. No entanto, nós do watcher também podem ser configurados para usar as URLs Web internas da organização. Isso permite que os administradores verifiquem o acesso à URL para usuários localizados dentro da rede de perímetro. Para configurar um nó do watcher para usar URLs internas em vez de URLs externas, defina a propriedade UseInternalWebURls como True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Redefinir essa propriedade para o valor padrão de False ($False) fará com que o watcher use novamente as URLs externas:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Instruções Especiais de Configuração para Transações Sintéticas
<a name="special_synthetictrans"> </a>

A maioria das transações sintéticas pode ser executado em um nó do watcher como está. Na maioria dos casos, assim que a transação sintética é adicionada às configurações do nó do watcher, o nó do watcher pode começar a usar essa transação sintética durante suas passagens de teste. No entanto, há algumas transações sintéticas que exigem instruções especiais de instalação, conforme discutido nas seções a seguir.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transação sintética de conferência de dados

Se o computador do nó do watcher estiver localizado fora da sua rede de perímetro, você provavelmente não poderá executar a Transação Sintética de Conferência de Dados, a menos que primeiro desabilite as configurações de proxy do navegador do Internet Explorer® do Windows internet para a conta de Serviço de Rede, concluindo as seguintes etapas:
  
1. No computador do nó do observador, clique em **Iniciar**, em **Todos os programas**, em **Acessórios**, clique com o botão direito no **Prompt de comando** e clique em **Executar como administrador**.
    
2. Na janela do console, digite o seguinte comando e pressione ENTER. 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    Você verá a seguinte mensagem exibida na janela de comando:

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    Esta mensagem indica que você desabilitou as configurações de proxy do Internet Explorer para a conta de Serviço de Rede.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange Transação sintética de Unificação de Mensagens

A Exchange de unificação de mensagens (UM) verifica se os usuários de teste podem se conectar a contas de caixa postal em casa Exchange.
  
Os usuários de teste precisarão ser pré-configurados com contas de caixa postal. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transação sintética de chat persistente

Para usar a transação sintética de Chat Persistente, primeiro você deve criar um canal e dar aos usuários de teste permissões para usá-lo.
  
Você pode usar a transação sintética de Chat Persistente para configurar este canal: 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Execute essa tarefa de instalação de dentro da empresa:
  
- Se for executado de uma máquina que não seja do servidor, o usuário que executar o cmdlet deverá ser membro da função CsPersistentChatAdministrators para Role-Based Access Control (RBAC).
    
- Se for executado do próprio servidor, o usuário que executar o cmdlet deverá ser membro do grupo RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transação sintética de chamada ponto a ponto PSTN

A Test-CsPstnPeerToPeerCall sintética verifica a capacidade de fazer e receber chamadas por meio de uma PSTN (rede telefônica pública comutado).
  
Para executar essa transação sintética, você deve configurar:
  
- Dois usuários de teste habilitados para UC (um chamador e um receptor).
    
- Números DID (Discagem Interna Direta) para cada conta de usuário.
    
- Políticas voIP e rotas de voz que permitem que as chamadas para o número do receptor cheguem ao gateway PSTN.
    
- Um gateway PSTN que aceita chamadas e mídia que encaminhará chamadas de volta para o pool principal de um receptor, com base no número discado.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transação sintética do Armazenamento de Contatos Unificado

A transação sintética do Unified Contact Store verifica a capacidade de Skype for Business Server recuperar contatos em nome de um usuário de Exchange.
  
Para usar essa transação sintética, as seguintes condições devem ser atendidas:
  
- Lyss-Exchange autenticação de servidor para servidor deve ser configurada.
    
- Os usuários de teste devem ter uma caixa Exchange caixa de correio válida.
    
Depois que essas condições são atendidas, você pode executar o seguinte cmdlet Windows PowerShell migrar as listas de contatos dos usuários de teste para Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Pode levar algum tempo para as listas de contatos do usuário de teste migrarem para Exchange. Para monitorar o progresso da migração, a mesma linha de comando pode ser executado sem o sinalizador -Setup:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Essa linha de comando terá êxito depois que a migração for concluída.
  
### <a name="xmpp-synthetic-transaction"></a>Transação sintética XMPP

A transação sintética XMPP (Extensible Messaging and Presence Protocol) exige que você configure o recurso XMPP com um ou mais domínios federados.
  
Para habilitar a transação sintética XMPP, você deve fornecer um parâmetro XmppTestReceiverMailAddress com uma conta de usuário em um domínio XMPP instável. Por exemplo:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

Neste exemplo, uma regra de Skype for Business Server precisará existir para roteá-litwareinc.com para um gateway XMPP.

> [!NOTE]
> Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não são mais suportados no Skype for Business Server 2019. Para obter mais informações, consulte [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md).
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transação sintética do VIS (Servidor de Interop de Vídeo)

A transação sintética do VIS (Servidor de Interop de Vídeo) exige que você baixe e instale os arquivos de suporte à transação sintética ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Para instalar VISSTSupportPackage.msi as dependências (em Requisitos do Sistema) para o msi já estão instaladas. Execute VISSTSupportPackage.msi para fazer uma instalação simples. O .msi instala todos os arquivos no seguinte caminho: "%ProgramFiles%\VIS Synthetic Transaction Support Package".
  
Para obter mais informações sobre como executar a Transação Sintética do VIS, consulte a documentação do cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV.](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV)
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Alterando a frequência de executar transações sintéticas
<a name="special_synthetictrans"> </a>

Por padrão, as transações sintéticas serão executados com os usuários configurados a cada 15 minutos. As transações sintéticas são executados sequencialmente em um conjunto de usuários para evitar que duas transações sintéticas conflitam entre si. Um intervalo maior é necessário para fornecer tempo para que todas as transações sintéticas seja concluída.
  
Se for desejável executar transações sintéticas com mais frequência, o número de transações sintéticas executados com um determinado conjunto de usuários deve ser reduzido para que os testes possam ser concluídos no intervalo de tempo desejado com algum buffer para atrasos ocasionais na rede. Se executar mais transações sintéticas for desejável, crie mais conjuntos de usuários para executar transações sintéticas adicionais.
  
Para alterar a frequência na qual as transações sintéticas são executados, siga estas etapas:
  
1. Abra System Center Operations Manager. Clique na seção Autoria. Clique na seção Regras (em Autoria).
    
2. Na seção Regras, encontre a regra com o nome "Regra de Coleta de Desempenho do Runner de Transações Sintéticas Principais".
    
3. Clique com o botão direito do mouse na regra e selecione Substituições, selecione Substituir a Regra e selecione "Para Todos os objetos da classe: Pool Watcher".
    
4. Na janela Substituir Propriedades, selecione Nome do Parâmetro "Frequência" e de definir o Valor de Substituição como o desejado.
    
5. Na mesma janela, selecione o pacote de gerenciamento ao qual essa substituição precisa ser aplicada.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Usando Registro em Log Sofisticado para Transações Sintéticas
<a name="special_synthetictrans"> </a>

Transações sintéticas são muito úteis para ajudar a identificar problemas com o sistema. Por exemplo, o cmdlet Test-CsRegistration pode alertar os administradores para o fato de que os usuários estavam com dificuldades para se registrar com Skype for Business Server. No entanto, mais detalhes podem ser necessários para determinar a causa real de uma falha.
  
Por esse motivo, as transações sintéticas fornecem log rico. Com o registro em log rico, para cada atividade que uma transação sintética realiza, as seguintes informações são registradas:
  
- A hora em que a atividade foi iniciada.
    
- A hora em que a atividade foi concluída.
    
- A ação que foi executada (por exemplo, criar, ingressar ou sair de uma conferência; entrar em uma Skype for Business Server; enviar uma mensagem instantânea).
    
- Mensagens informativas, detalhadas, de aviso ou de erro geradas quando a atividade foi realizada.
    
- Mensagens de registro SIP.
    
- Registros de exceção ou códigos de diagnóstico gerados quando a atividade foi realizada.
    
- O resultado líquido da execução da atividade.
    
Essas informações são geradas automaticamente sempre que uma transação sintética é executado, mas não é automaticamente exibida ou salva em um arquivo de log. Se você estiver executando manualmente uma transação sintética, poderá usar o parâmetro OutLoggerVariable para especificar uma Windows PowerShell variável na qual as informações serão armazenadas. A partir daí, você tem a opção de usar um dos dois métodos para salvar e/ou exibir mensagens de erro no log rich no formato XML ou HTML. 
  
Para recuperar as informações de solução de problemas, especifique o parâmetro OutLoggerVariable, seguido de um nome de variável escolhido:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Não use o caractere $ como prefixo do nome da variável. Use um nome de variável como RegistrationTest (não $RegistrationTest). 
  
Ao executar este comando, você verá uma saída semelhante a esta:
  
Fqdn de destino : atl-cs-001.litwareinc.com Resultado : Latência de Falha : 00:00:00 Mensagem de Erro : Este computador não tem certificados atribuídos. Diagnóstico :Você pode acessar informações muito mais detalhadas para essa falha do que apenas a mensagem de erro mostrada aqui.

Para acessar essas informações no formato HTML, use um comando semelhante a este para salvar as informações armazenadas na variável RegistrationTest em um arquivo HTML:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Como alternativa, é possível usar o método ToXML() para salvar os dados em um arquivo XML:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Você pode exibir esses arquivos usando Windows Internet Explorer, Microsoft Visual Studio ou qualquer outro aplicativo capaz de abrir arquivos HTML/XML.
  
As transações sintéticas são executados de dentro do System Center Operations Manager gerarão automaticamente esses arquivos de log para falhas. Esses logs não serão gerados se a execução falhar antes Skype for Business Server o PowerShell for capaz de carregar e executar a transação sintética. 
  
> [!IMPORTANT]
> Por padrão, Skype for Business Server salva arquivos de log em uma pasta que não é compartilhada. Para tornar esses logs prontamente acessíveis, você deve compartilhar essa pasta. Por exemplo: \\ atl-watcher-001.litwareinc.com\WatcherNode.
