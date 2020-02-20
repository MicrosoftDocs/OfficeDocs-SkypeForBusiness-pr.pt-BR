---
title: Configurar usuários e configurações de teste de nó do Inspetor
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: configurar contas de usuário de teste e configurações do nó do inspetor para transações sintéticas do Skype for Business Server.'
ms.openlocfilehash: bfbad6fbeb68100adaaee781c135531d226f43bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150492"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configurar usuários e configurações de teste de nó do Inspetor
 
**Resumo:** Configurar contas de usuário de teste e configurações do nó do inspetor para transações sintéticas do Skype for Business Server.
  
Depois de configurar o computador que atuará como um nó do inspetor, você deve:
  
1. [Configurar contas de usuário de teste](test-users-and-settings-2019.md#testuser) para serem usadas por esses nós do Inspetor. Se estiver usando o método de autenticação Negociar, você também deve usar o cmdlet **Set-CsTestUserCredential** para permitir o uso dessas contas de teste no nó do inspetor.
    
2. Atualizar as definições de configuração do nó do inspetor.
    
## <a name="configure-test-user-accounts"></a>Configurar contas de usuário de teste
<a name="testuser"> </a>

As contas de teste não precisam representar pessoas reais, mas devem ser contas válidas do Active Directory. Além disso, essas contas devem estar habilitadas para o Skype for Business Server, elas devem ter endereços SIP válidos e devem ser habilitadas para o Enterprise Voice (para usar a transação sintética test-CsPstnPeerToPeerCall). 
  
Se você estiver usando o método de autenticação TrustedServer, tudo o que você precisa fazer é verificar se essas contas existem e configurá-las conforme indicado. É necessário atribuir pelo menos três usuários de teste a cada pool que deseja testar. Se você estiver usando o método de autenticação negociar, você também deve usar o cmdlet Set-CsTestUserCredential e o Shell de gerenciamento do Skype for Business Server para permitir que essas contas de teste funcionem com as transações sintéticas. Execute um comando semelhante ao seguinte (estes comandos presumem que as três contas de usuário do Active Directory tenham sido criadas e que essas contas estejam habilitadas para o Skype for Business Server):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

Você deve incluir não apenas o endereço SIP, mas também o nome de usuário e a senha. Se você não incluir a senha, o cmdlet Set-CsTestUserCredential solicitará que você insira essas informações. O nome de usuário pode ser especificado usando o formato de nome de domínio \ mostrado no bloco de código anterior.
  
Para verificar se as credenciais do usuário de teste foram criadas, execute estes comandos do Shell de gerenciamento do Skype for Business Server:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

Informações semelhantes a estas serão retornadas para cada usuário:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System. Security. SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurar um nó do Inspetor básico com as transações sintéticas padrão

Depois que os usuários de teste tiverem sido criados, você poderá criar um nó do Inspetor usando um comando semelhante a este:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

Esse comando cria um novo nó do inspetor que usa as configurações padrão e executa o conjunto padrão de transações sintéticas. O novo nó do inspetor também usa watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com dos usuários de teste. Se o nó do Inspetor usar a autenticação TrustedServer, as três contas de teste poderão ser todas as contas de usuário válidas habilitadas para o Active Directory e o Skype for Business Server. Se o nó do Inspetor usar o método de autenticação Negotiate, essas contas de usuário também deverão ser habilitadas para o nó do observador usando o cmdlet Set-CsTestUserCredential.
  
Para validar que a descoberta automática do pool de destino para entrar está configurada corretamente em vez de direcionar um pool diretamente, use estas etapas:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configurando testes estendidos

Se você deseja habilitar o teste PSTN, que verifica a conectividade com a rede telefônica pública comutada, você precisa fazer algumas configurações adicionais ao configurar o nó do Inspetor. Primeiro, você deve associar seus usuários de teste com o tipo de teste PSTN executando um comando semelhante a este no Shell de gerenciamento do Skype for Business Server:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Os resultados desse comando devem ser armazenados em uma variável. Neste exemplo, a variável é nomeada $pstnTest. 
  
Em seguida, você pode usar o cmdlet **New-CsWatcherNodeConfiguration** para associar o tipo de teste (armazenado na variável $pstnTest) a um pool do Skype for Business Server. Por exemplo, o comando a seguir cria uma nova configuração de nó do observador para o pool atl-cs-001.litwareinc.com, adicionando os três usuários de teste criados anteriormente e adicionando o tipo de teste PSTN:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

O comando anterior falhará se você não tiver instalado os arquivos de núcleo do Skype for Business Server e o banco de dados RTCLocal no computador do nó do Inspetor. 
  
Para testar várias políticas de voz, você pode criar um teste estendido para cada política usando o cmdlet **New-CsExtendedTest** . Os usuários fornecidos devem ser configurados com as políticas de voz desejadas. Os testes estendidos são passados para o cmdlet **New-CsWatcherNodeConfiguration** usando delimitadores de vírgula, como:
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
Como o cmdlet **New-CsWatcherNodeConfiguration** foi chamado sem usar o parâmetro tests, somente as transações sintéticas padrão (e a transação sintética estendida especificada) serão habilitadas para o novo nó do Inspetor. Portanto, o nó do Inspetor testará os seguintes componentes:
  
- Registro
    
- Mensagens instantâneas
    
- GroupIM
    
- P2PAV (sessões de áudio/vídeo ponto a ponto)
    
- AvConference (áudio/conferência)
    
- Presença
    
- ABS (serviço do Catálogo de Endereços)
    
- ABWQ (serviço Web do Catálogo de Endereços)
    
Os seguintes componentes não serão testados por padrão:
  
- Asconferência
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Unificação de Mensagens do Exchange)
    
- JoinLauncher
    
- MCXP2PIM (mensagens instantâneas de dispositivos móveis herdados)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (chamadas de gateway PSTN, especificadas como teste estendido)
    
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

Ocorrerá um erro se um ou mais desses testes (por exemplo, dataconferência) já tiverem sido habilitados no nó do Inspetor. Nesse caso, você receberá uma mensagem de erro semelhante a esta:
  
Set-CsWatcherNodeConfiguration: há uma sequência de chave duplicada ' dataconferência ' para a chave ' urn: Schema: Microsoft. RTC. Management. Settings. WatcherNode. 2010: TestName ' ou a restrição Identity exclusiva.
  
Quando esse erro ocorre, nenhuma alteração será aplicada. O comando deve ser executado novamente com o teste de duplicata removido.
  
Para remover uma transação sintética de um nó do Inspetor, use o método remove. Por exemplo, esse comando remove o teste ABWQ do nó do inspetor:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Você pode usar o método Replace para substituir todos os testes atualmente habilitados por um ou mais testes novos. Por exemplo, se você deseja que um nó do Inspetor apenas execute o teste de mensagens instantâneas, é possível configurá-lo usando este comando:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Quando você executar este comando, todas as transações sintéticas no nó do Inspetor especificado serão desabilitadas, exceto para IM.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Exibindo e testando a configuração do nó inspetor

Se quiser exibir os testes que foram atribuídos ao nó do inspetor, use um comando semelhante a este:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Este comando retornará informações semelhantes a isso, dependendo das transações sintéticas que foram atribuídas ao nó:
  
Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage dataconferência
> [!TIP]
> Para exibir as transações sintéticas em ordem alfabética, use este comando: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Para verificar se um nó do inspetor foi criado, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Você receberá informações semelhantes a estas:
  
Identity: atl-cs-001.litwareinc.com testusers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...} ExtendedTests: {testusers = IList<System. String>; Name = teste PSTN; Te...} TargetFqdn: atl-cs-001.litwareinc.com PortNumber: 5061To Verifique se o nó do inspetor foi configurado corretamente, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Este comando testará cada nó do Inspetor em sua implantação e confirmará se as seguintes ações foram concluídas:
  
- A função registrador necessária está instalada
    
- A chave de registro necessária é criada (concluída quando você executou o cmdlet Set-CsWatcherNodeConfiguration)
    
- Seus servidores estão executando a versão correta do Skype for Business Server
    
- Suas portas estão configuradas corretamente
    
- Seus usuários de teste atribuídos têm as credenciais necessárias
    
## <a name="managing-watcher-nodes"></a>Gerenciar nós do Inspetor
<a name="testuser"> </a>

Além de modificar as transações sintéticas que são executadas em um nó do Inspetor, você também pode usar o cmdlet **set-CsWatcherNodeConfiguration** para executar duas outras tarefas importantes: habilitar e desabilitar o nó do Inspetor e configurar o nó do inspetor para usar URLs internas da Web ou URLs da Web externas ao executar seus testes.
  
Por padrão, os nós do Inspetor foram projetados para executar periodicamente todas as suas transações sintéticas habilitadas. Às vezes, no entanto, você pode querer suspender essas transações. Por exemplo, se o nó do Inspetor estiver desconectado temporariamente da rede, não haverá motivo para executar as transações sintéticas. Sem conectividade de rede, essas transações falharão. Para desabilitar temporariamente um nó do Inspetor, execute um comando semelhante a este no Shell de gerenciamento do Skype for Business Server:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Este comando desabilitará a execução de transações sintéticas no nó do Inspetor 001.litwareinc.com do Inspetor do ATL. Para retomar a execução das transações sintéticas, defina a propriedade Enabled de volta como true ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> A propriedade Enabled pode ser usada para ativar ou desativar os nós do Inspetor. Se você quiser excluir permanentemente um nó do Inspetor, use o cmdlet **Remove-CsWatcherNodeConfiguration** :
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Esse comando Remove todas as definições de configuração do nó do observador do computador especificado, o que impede que o computador execute transações sintéticas automaticamente. No entanto, o comando não desinstala os arquivos do agente do System Center ou os arquivos de sistema do Skype for Business Server.
  
Por padrão, os nós do Inspetor usam as URLs da Web externas da organização ao conduzir testes. No entanto, os nós do Inspetor também podem ser configurados para usar as URLs da Web internas da organização. Isso permite que os administradores verifiquem o acesso à URL para usuários localizados dentro da rede de perímetro. Para configurar um nó do inspetor para usar URLs internas em vez de URLs externas, defina a propriedade UseInternalWebURls como true ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

A redefinição dessa propriedade para o valor padrão false ($False) fará com que o Inspetor mais uma vez use as URLs externas:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Instruções Especiais de Configuração para Transações Sintéticas
<a name="special_synthetictrans"> </a>

A maioria das transações sintéticas pode ser executada em um nó do Inspetor como está. Na maioria dos casos, assim que a transação sintética é adicionada às definições de configuração do nó do observador, o nó do Inspetor pode começar a usar essa transação sintética durante o teste. No entanto, há algumas transações sintéticas que exigem instruções de configuração especiais, conforme discutido nas seções a seguir.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transação sintética de conferência de dados

Se o computador do nó do observador estiver localizado fora da rede de perímetro, provavelmente você não poderá executar a transação sintética da conferência de dados, a menos que primeiro desabilite o Windows Internet Explorer® configurações de proxy do navegador da Internet para a rede Conta de serviço realizando as seguintes etapas:
  
1. No computador do nó do Inspetor, clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e clique em **Executar como administrador**.
    
2. Na janela do console, digite o seguinte comando e pressione ENTER. 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Você verá a seguinte mensagem exibida na janela de comando:
  
O BITSAdmin foi preterido e não é garantido estar disponível em versões futuras do Windows. As ferramentas de administração do serviço BITS são agora fornecidas pelos cmdlets do PowerShell do BITS.
  
Configurações de proxy da Internet para a conta NetworkService definida como NO_PROXY. 
  
(conexão = padrão)
  
Essa mensagem indica que você desabilitou as configurações de proxy do Internet Explorer para a conta de serviço de rede.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transação sintética de Unificação de mensagens do Exchange

A transação sintética de Unificação de mensagens (UM) do Exchange verifica se os usuários de teste podem se conectar às contas de caixa postal hospedadas no Exchange.
  
Os usuários de teste precisarão ser pré-configurados com contas de caixa postal. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transação sintética de chat persistente

Para usar a transação sintética de chat persistente, você deve primeiro criar um canal e conceder permissões aos usuários de teste para usá-lo.
  
Você pode usar a transação sintética de chat persistente para configurar este canal: 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Você deve executar esta tarefa de configuração para ser executada de dentro da empresa:
  
- Se executado de uma máquina não servidor, o usuário que executa o cmdlet deve ser um membro da função CsPersistentChatAdministrators para o controle de acesso baseado em função (RBAC).
    
- Se executado no próprio servidor, o usuário que executa o cmdlet deve ser um membro do grupo RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transação sintética de chamada ponto a ponto PSTN

A transação sintética test-CsPstnPeerToPeerCall verifica a capacidade de colocar e receber chamadas através de uma PSTN (rede telefônica pública comutada).
  
Para executar essa transação sintética, você deve configurar:
  
- Dois usuários de teste habilitados para UC (um chamador e um receptor).
    
- Números DID (Discagem Interna Direta) para cada conta de usuário.
    
- Políticas de VoIP e rotas de voz que permitem que chamadas para o número do receptor cheguem ao gateway PSTN.
    
- Um gateway PSTN que aceita chamadas e mídias que roteiam chamadas de volta para o pool de casa de um receptor, com base no número discado.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transação sintética do repositório unificado de contatos

A transação sintética do repositório unificado de contatos verifica a capacidade do Skype for Business Server de recuperar contatos em nome de um usuário do Exchange.
  
Para usar essa transação sintética, as seguintes condições devem ser atendidas:
  
- Lyss-a autenticação do Exchange Server para servidor deve ser configurada.
    
- Os usuários de teste devem ter uma caixa de correio do Exchange válida.
    
Depois que essas condições forem atendidas, você pode executar o seguinte cmdlet do Windows PowerShell para migrar as listas de contatos dos usuários de teste para o Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Pode levar algum tempo para que as listas de contatos de usuário de teste migrem para o Exchange. Para monitorar o progresso da migração, a mesma linha de comando pode ser executada sem o sinalizador de instalação:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Essa linha de comando será bem-sucedida após a conclusão da migração.
  
### <a name="xmpp-synthetic-transaction"></a>Transação sintética XMPP

A transação sintética de IM XMPP (Extensible Messaging and Presence Protocol) exige que você configure o recurso XMPP com um ou mais domínios federados.
  
Para habilitar a transação sintética XMPP, você deve fornecer um parâmetro XmppTestReceiverMailAddress com uma conta de usuário em um domínio XMPP roteável. Por exemplo:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

Neste exemplo, uma regra do Skype for Business Server precisará existir para rotear mensagens para o litwareinc.com para um Gateway XMPP.

> [!NOTE]
> Os gateways e proxies do XMPP estavam disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrating XMPP Federation](../migration/migrating-xmpp-federation.md) para obter mais informações.
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transação sintética de VIS (servidor de interoperabilidade de vídeo)

A transação sintética do VIS (servidor de interoperabilidade de vídeo) exige que você baixe e instale os arquivos de suporte de transação sintética ([VISSTSupportPackage. msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Para instalar o VISSTSupportPackage. msi, verifique se as dependências (em requisitos do sistema) para o MSI já estão instaladas. Execute o VISSTSupportPackage. msi para fazer uma instalação simples. O. msi instala todos os arquivos no seguinte caminho: "pacote de suporte à transação sintética do%ProgramFiles%\VIS".
  
Para obter mais detalhes sobre como executar a transação sintética do VIS, consulte a documentação do cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Alterar a frequência de execução de transações sintéticas
<a name="special_synthetictrans"> </a>

Por padrão, as transações sintéticas serão executadas com os usuários configurados a cada 15 minutos. As transações sintéticas são executadas de forma seqüencial dentro de um conjunto de usuários para evitar que duas transações sintéticas entrem em conflito entre si. Um intervalo mais longo é necessário para fornecer tempo para que todas as transações sintéticas sejam concluídas.
  
Se for desejável executar transações sintéticas com mais frequência, o número de transações sintéticas executadas com um determinado conjunto de usuários deve ser reduzido para que os testes possam ser concluídos no intervalo de tempo desejado com algum buffer para atrasos de rede ocasionais. Se a execução de mais transações sintéticas for desejável, crie mais conjuntos de usuários para executar transações sintéticas adicionais.
  
Para alterar a frequência na qual as transações sintéticas são executadas, siga estas etapas:
  
1. Abra o System Center Operations Manager. Clique em seção de criação. Seção de regras de clique (sob criação)
    
2. Na seção regras, encontre a regra com o nome "regra de coleta de desempenho do executor de transações sintéticas" principal
    
3. Clique com o botão direito do mouse na regra e selecione substituições, selecione substituir a regra e, em seguida, selecione "para todos os objetos da classe: Inspetor de pool"
    
4. Na janela substituir Propriedades, selecione nome do parâmetro "frequência" e defina o valor de substituição para o desejado.
    
5. Na mesma janela, selecione o pacote de gerenciamento para o qual essa substituição precisa ser aplicada
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Usando Registro em Log Sofisticado para Transações Sintéticas
<a name="special_synthetictrans"> </a>

As transações sintéticas são extremamente úteis para ajudar a identificar problemas com o sistema. Por exemplo, o cmdlet Test-CsRegistration poderia alertar os administradores sobre o fato de que os usuários estavam tendo dificuldade para registrar-se no Skype for Business Server. No entanto, detalhes adicionais podem ser necessários para determinar a causa real de uma falha.
  
Por esse motivo, as transações sintéticas fornecem logs avançados. Com o registro em log avançado, para cada atividade que uma transação sintética é executada, as seguintes informações são registradas:
  
- A hora em que a atividade foi iniciada.
    
- A hora em que a atividade foi concluída.
    
- A ação que foi executada (por exemplo, criar, ingressar ou sair de uma conferência; fazer logon no Skype for Business Server; enviar uma mensagem instantânea).
    
- Mensagens informativas, detalhadas, de advertência ou de erro geradas quando a atividade foi executada
    
- Mensagens de registro SIP.
    
- Registros de exceção ou códigos de diagnóstico gerados quando a atividade foi executada.
    
- O resultado líquido da execução da atividade.
    
Essas informações são geradas automaticamente cada vez que uma transação sintética é executada, mas não é automaticamente exibida ou salva em um arquivo de log. Se você estiver executando uma transação sintética manualmente, poderá usar o parâmetro OutLoggerVariable para especificar uma variável do Windows PowerShell na qual as informações serão armazenadas. A partir daí, você tem a opção de usar um dos dois métodos para salvar e/ou exibir mensagens de erro no log avançado em formato XML ou HTML. 
  
Para recuperar as informações de solução de problemas, especifique o parâmetro OutLoggerVariable, seguido de um nome de variável que você escolher:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : Não preceda o nome da variável com o caractere $. Use um nome de variável como RegistrationTest (não $RegistrationTest). 
  
Ao executar este comando, você verá um resultado semelhante a este:
  
FQDN de destino: atl-cs-001.litwareinc.com resultado: latência de falha: 00:00:00 mensagem de erro: esta máquina não tem nenhum certificado atribuído. Diagnóstico: você pode acessar informações muito mais detalhadas para essa falha do que apenas a mensagem de erro mostrada aqui. Para acessar essas informações no formato HTML, use um comando semelhante a este para salvar as informações armazenadas na variável RegistrationTest em um arquivo HTML:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Como alternativa, é possível usar o método ToXML() para salvar os dados em um arquivo XML:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Você pode exibir esses arquivos usando o Windows Internet Explorer, o Microsoft Visual Studio ou qualquer outro aplicativo capaz de abrir arquivos HTML/XML.
  
As transações sintéticas executadas de dentro do System Center Operations Manager gerarão automaticamente esses arquivos de log para falhas. Esses logs não serão gerados se a execução falhar antes do Skype for Business Server PowerShell poder carregar e executar a transação sintética. 
  
> [!IMPORTANT]
> Por padrão, o Skype for Business Server salva arquivos de log em uma pasta que não é compartilhada. Para tornar esses logs prontamente acessíveis, você deve compartilhar esta pasta. Por exemplo: \\ATL-Watcher-001. litwareinc. com\WatcherNode. 
