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
ms.openlocfilehash: 257814108a276d049ed4ac9173fde6dfa4473ff2
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789388"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configurar usuários de teste e configurações do nó do inspetor
 
**Resumo:** Configure contas de usuário de teste e configurações de nó do observador do Skype para transações sintéticas do Business Server.
  
Depois de configurar o computador que atuará como um nó do inspetor, você deve:
  
1. [Configurar contas de usuário de teste](test-users-and-settings.md#testuser) a ser usado por esses nós do observador. Se estiver usando o método de autenticação Negociar, você também deve usar o cmdlet **Set-CsTestUserCredential** para permitir o uso dessas contas de teste no nó do inspetor.
    
2. Atualizar as definições de configuração do nó do inspetor.
    
## <a name="configure-test-user-accounts"></a>Configurar contas de usuário de teste
<a name="testuser"> </a>

Contas de teste não precisará representam pessoas reais, mas eles devem ser contas válidas do Active Directory. Além disso, essas contas devem ser habilitadas para Skype para Business Server, eles devem ter endereços válidos de SIP e eles devem ser habilitados para o Enterprise Voice (usar a transação sintética de Test-CsPstnPeerToPeerCall). 
  
Se você estiver usando o método de autenticação TrustedServer, tudo o que você precisa fazer é certificar-se de que essas contas existem e configurá-las como observado. Você deve atribuir pelo menos dois usuários de teste para cada pool que você deseja testar. Se você estiver usando o método de autenticação negociar, você também deve usar o cmdlet Set-CsTestUserCredential e do Skype para Business Server Management Shell habilitar essas contas para trabalhar com as transações sintéticas de teste. Fazer isso executando um comando semelhante ao seguinte (esses comandos assumem que as duas contas de usuário do Active Directory foram criadas e que essas contas estão habilitadas para Skype para Business Server):
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

É necessário incluir não apenas o endereço SIP, mas também o nome e a senha do usuário. Se você não incluir a senha, o cmdlet Set-CsTestUserCredential solicitará que você insira essas informações. O nome de usuário pode ser especificado usando-se o formato de nome de domínio\nome de usuário indicado no bloqueio do código anterior.
  
Para verificar se as credenciais de usuário de teste foram criadas, execute estes comandos do Skype do Shell de gerenciamento do servidor de negócios:
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Informações semelhantes a estas devem ser retornadas para cada usuário:
  
|**Nome de usuário**|**Senha**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurar um nó básico do inspetor com as transações sintéticas padrão

Depois que os usuários de teste são criados, você pode criar um nó do inspetor usando um comando semelhante a este:
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Esse comando cria um novo nó do inspetor que usa as configurações padrão e executa o conjunto padrão de transações sintéticas. O novo nó do observador também usa o teste usuários watcher1@litwareinc.com e watcher2@litwareinc.com. Se o nó do Inspetor usa a autenticação de TrustedServer, as duas contas de teste podem ser qualquer conta de usuário válido habilitada para o Active Directory e Skype para Business Server. Se o nó do inspetor usa o método de autenticação Negociar, estas contas de usuário também deve ser ativadas para o nó do inspetor usando o cmdlet Set-Cs TestUserCredential.
  
Para validar se a descoberta automática de pool de destino a ser inserida está configurada corretamente, ao invés de direcionar um pool diretamente, siga as etapas abaixo:
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configurando testes estendidos

Se quiser habilitar o teste PSTN, que verifica a conectividade com a rede telefônica pública comutada, você precisará fazer algumas configurações adicionais ao configurar o nó do inspetor. Primeiro, você deve associar seus usuários de teste ao tipo de teste da PSTN executando um comando semelhante a este no Shell de Gerenciamento do Skype for Business Server:
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Os resultados desse comando devem ser armazenados em uma variável. Neste exemplo, é uma variável chamada de $pstnTest. 
  
Em seguida, você pode usar o cmdlet **New-CsWatcherNodeConfiguration** para associar o tipo de teste (armazenado na variável $pstnTest) para um Skype para pool de servidores de negócios. Por exemplo, o comando a seguir cria uma nova configuração de nó de inspetor para o pool atl-cs-001, adicionando os dois usuários de teste criados anteriormente, e adicionando o PSTN tipo de teste:
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

O comando anterior falhará se você não tiver instalado os arquivos de núcleo do Skype for Business Server 2015 e o banco de dados RTCLocal no computador do nó do inspetor. 
  
Para testar várias políticas de voz, você pode criar um teste estendido para cada política usando o cmdlet **New-CsExtendedTest**. Os usuários fornecidos devem ser configurados com as políticas de voz desejadas. Os testes estendidos são passados para o cmdlet **New-CsWatcherNodeConfiguration** separados por vírgula, como indicado:
  
-ExtendedTests @{adicionar = US $pstnTest1, $pstnTest2, $pstnTest3}
  
Como o cmdlet **New-CsWatcherNodeConfiguration** foi chamado sem usar o parâmetro Tests, isso significa que somente as transações sintéticas Padrão (e a transação sintética estendida especificada) serão ativadas no novo nó do inspetor. Portanto, o nó do inspetor testará os seguintes componentes:
  
- Registro
    
- IM
    
- GroupIM (mensagens instantâneas de grupo)
    
- P2PAV (sessões de áudio/vídeo ponto a ponto)
    
- AvConference (áudio/conferência)
    
- Presença
    
- ABS (serviço do Catálogo de Endereços)
    
- ABWQ (serviço Web do Catálogo de Endereços)
    
Os seguintes componentes não serão testados por padrão:
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialInConferencing
    
- ExumConnectivity (Unificação de Mensagens do Exchange)
    
- JoinLauncher
    
- MCXP2PIM (herdado dispositivo móvel mensagens instantâneas)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (chamadas de gateway PSTN, especificadas como um teste estendido)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Adicionando e removendo transações sintéticas

Depois que um nó do inspetor é configurado, é possível usar o cmdlet  Set-CsWatcherNodeConfiguration para adicionar ou remover transações sintéticas do nó. Por exemplo, para adicionar o teste PersistentChatMessage ao nó do inspetor, use o método Add e um comando semelhante a este:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

É possível adicionar vários testes separando os nomes de teste com vírgulas. Por exemplo:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Um erro ocorrerá se um ou mais desses testes (por exemplo, DataConference) já estiverem ativados no nó do inspetor. Nesse caso, você receberá uma mensagem de erro semelhante a esta:
  
Set-CsWatcherNodeConfiguration : Há uma sequência principal duplicada 'DataConference' para 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' ou restrição de identidade única.
  
Quando esse erro ocorre, nenhuma alteração será aplicada. O comando deve ser executado novamente com o teste duplicado removido.
  
Para remover uma transação sintética do nó do inspetor, use o método Remove. Por exemplo, esse comando remove o teste ABWQ do nó do inspetor:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

É possível usar o método Replace para substituir todos os testes ativados no momento por um ou mais testes novos. Por exemplo, se desejar que apenas um nó do inspetor execute o teste IM, você pode configurar isso usando este comando:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Quando você executa o comando anterior, todas as transações sintéticas no nó do inspetor especificado serão desativadas exceto para IM.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Exibindo e testando a configuração do nó do inspetor

Se quiser exibir os testes que foram atribuídos ao nó do inspetor, use um comando semelhante a este:
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

O comando anterior retornará informações semelhantes a essa, dependendo das transações sintéticas atribuídas ao nó:
  
Registro IM GroupIM P2PAV AvConference presença PersistentChatMessage DataConference
> [!TIP]
> Para exibir as transações sintéticas em ordem alfabética, use este comando: 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Para verificar se um nó do inspetor foi criado, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server:
  
```
Get-CsWatcherNodeConfiguration
```

Você receberá informações semelhantes a estas:
  
Identidade: atl-cs-001. <br/>
TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}<br/>
ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}<br/>
TargetFqdn: atl-cs-001.<br/>
Número da porta: 5061<br/>

Para verificar que o nó do inspetor foi configurado corretamente, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server:
  
```
Test-CsWatcherNodeConfiguration
```

Este comando testará o nó do inspetor em sua implantação e confirmará se as seguintes ações foram concluídas:
  
- A função registrador necessária está instalada.
    
- A chave de registro necessária é criada (concluído quando executou o cmdlet Set-CsWatcherNodeConfiguration).
    
- Seus servidores estão executando a versão correta do Skype para Business Server.
    
- Suas portas estão configuradas corretamente.
    
- Os usuários de teste atribuídos têm as credenciais necessárias.
    
## <a name="managing-watcher-nodes"></a>Gerenciar nós do inspetor
<a name="testuser"> </a>

Além de modificar as transações sintéticas que são executadas em um nó do inspetor, você também podem usar o cmdlet **Set-CsWatcherNodeConfiguration** para realizar duas outras tarefas importantes: habilitar e desabilitar o nó do inspetor e configurá-lo para usar URLs da Web internas ou externas durante a execução de testes.
  
Por padrão, os nós do inspetor são projetados para executar periodicamente todas as transações sintéticas habilitadas. Às vezes, no entanto, você pode querer suspender essas transações. Por exemplo, se o nó do inspetor estiver temporariamente desconectado da rede, não há motivo para executar as transações sintéticas. Sem conectividade de rede, essas transações falharão. Para desabilitar o nó do inspetor temporariamente, execute um comando semelhante a este no Shell de Gerenciamento do Skype for Business Server:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Esse comando desabilitará a execução das transações sintéticas no nó do inspetor atl-watcher- 001.litwareinc.com. Para retomar a execução das transações sintéticas, defina a propriedade Enabled novamente como True ($True):
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> A propriedade Enabled pode ser usada para habilitar e desabilitar os nós do inspetor. Se você desejar excluir permanentemente um nó do inspetor, use o cmdlet **Remove-CsWatcherNodeConfiguration** :
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Esse comando remove todas as configurações de nó do inspetor do computador especificado, o que impede que o computador execute transações sintéticas automaticamente. No entanto, o comando não desinstala os arquivos de agente do System Center ou o Skype para arquivos de sistema do servidor de negócios.
  
Por padrão, os nós do inspetor usam as URLs da Web externas de uma organização durante a realização de seus testes. No entanto, também é possível configurá-los para usar as URLs da Web internas da organização. Isso permite que os administradores verifiquem o acesso a URLs para os usuários localizados dentro da rede de perímetro. Para configurar um nó do inspetor para usar as URLs internas em vez das externas, defina a propriedade UseInternalWebUrls como True ($True):
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

A redefinição dessa propriedade para o valor padrão False ($False) fará com que o inspetor mais uma vez use as URLs externas:
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Instruções Especiais de Configuração para Transações Sintéticas
<a name="special_synthetictrans"> </a>

A maioria das transações sintéticas pode ser executada em um nó do inspetor como está. Na maioria dos casos, assim que uma transação sintética é adicionada às configurações do nó do inspetor, o nó do inspetor pode começar usando essa transação sintética durante suas fases de teste. No entanto, existem algumas transações sintéticas que exigem instruções especiais de configuração, conforme discutido nas seções a seguir.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transação Sintética de Conferência de Dados

Se o computador de nó do inspetor estiver localizado fora da sua rede de perímetro, você provavelmente não será capaz de executar a transação sintética de conferência de dados, a menos que primeiro desabilite as configurações de proxy do navegador do Windows Internet Explorer® para a conta Serviço de Rede completando as seguintes etapas:
  
1. No computador de nó do inspetor, clique em **Iniciar**, em **Todos os Programas**, em **Acessórios**, clique com o botão direito do mouse em **Prompt de Comando**, e clique em **Executar como administrador**.
    
2. Na janela do console, digite o seguinte comando e pressione ENTER. 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Você verá a seguinte mensagem exibida na janela de comando:
  
BITSAdmin é deprecada e nada garante que estará disponível em versões futuras do Windows. Ferramentas de Administração para o serviço BITS agora são fornecidas pelos cmdlets BITS PowerShell.
  
As configurações de proxy da Internet para conta Serviço de Rede estão definidas como NO_PROXY. 
  
(conexão = padrão)
  
Esta mensagem indica que você desabilitou as configurações de proxy do Internet Explorer para a conta Serviço de Rede.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transações sintéticas de Unificação de Mensagens do Exchange

A transação sintética de Unificação de Mensagens do Exchange verifica se usuários de teste podem se conectar a contas de correio de voz hospedadas no Exchange.
  
Os usuários de teste precisarão ser pré-configurados com contas de correio de voz. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transação Sintética de Chat Persistente

Para usar a transação sintética do chat persistente, você deve primeiro criar um canal e conceder aos usuários de teste permissões para usá-lo.
  
Você pode usar a transação sintética de chat persistente para configurar esse canal: 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Você deve executar esta tarefa de configuração de dentro da empresa:
  
- Se ela for realizada de uma máquina que não é um servidor, o usuário que executar o cmdlet deverá ser um membro da função CsPersistentChatAdministrators do RBAC (Controle de Acesso Baseado em Função).
    
- Se ela for realizada a partir do próprio servidor, o usuário que executar o cmdlet deverá ser um membro do grupo RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transações sintéticas de chamada ponto a ponto PSTN

A transação sintética de Test-CSPstnPeerToPeerCall verifica a capacidade de realizar e receber chamadas através de uma PSTN (rede telefônica pública comutada).
  
Para executar essa transação sintética, você deve configurar:
  
- Dois usuários de teste habilitados em UC (um chamador e um receptor).
    
- Números DID (Discagem Interna Direta) para cada conta de usuário.
    
- Rotas de voz e políticas de VoIP que permitem que chamadas para o número do receptor cheguem ao gateway PSTN.
    
- Um gateway PSTN que aceita chamadas e mídia que encaminharão as chamadas de volta ao pool primário de um receptor, com base no número discado.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transações Sintéticas do Repositório Unificado de Contatos

A transação sintética do repositório unificado de contatos verifica a capacidade do Skype para Business Server recuperar contatos em nome de um usuário do Exchange.
  
Para usar essa transação sintética, as seguintes condições devem ser atendidas:
  
- A autenticação de servidor para servidor do Lyss-Exchange deve ser configurada.
    
- Os usuários de teste devem ter uma caixa de entrada válida do Exchange.
    
Depois que essas condições forem atendidas, você pode executar o seguinte cmdlet do Windows PowerShell para migrar as listas de contatos dos usuários de teste para o Exchange:
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Pode levar algum tempo para que as listas de contato do usuário de teste migrem para o Exchange. Para monitorar o andamento da migração, a mesma linha de comando pode ser executada sem o - sinalizador de instalação:
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Esta linha de comando será bem-sucedida após a conclusão da migração.
  
### <a name="xmpp-synthetic-transaction"></a>Transação Sintética XMPP

A transação sintética de IM do protocolo XMPP (Extensible Messaging and Presence Protocol) exige que o recurso XMPP seja configurado com um ou mais domínios federados.
  
Para habilitar a transação sintética XMPP, um parâmetro XmppTestReceiverMailAddress deve ser fornecido com uma conta de usuário em um domínio XMPP roteável. Por exemplo:
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

Neste exemplo, um Skype para regra Business Server precisará existir para encaminhar mensagens de litwareinc.com para um gateway XMPP.

> [!NOTE]
> Gateways de XMPP e proxies estão disponíveis no Skype para Business Server 2015, mas não são mais suportados no Skype para Business Server 2019. Consulte a [federação XMPP migrando](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações. 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transação sintética do Servidor de Interoperabilidade de Vídeo (VIS)

A transação sintética do VIS (Servidor de Interoperabilidade de Vídeo) exige que você baixe e instale os arquivos de apoio da transação sintética ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)). 
  
Para instalar VISSTSupportPackage.msi, certifique-se de que as dependências (em Requisitos de Sistema) para o msi já se encontram instaladas. Executar VISSTSupportPackage.msi para realizar uma instalação simples. O arquivo. msi instala todos os arquivos no seguinte caminho: "%ProgramFiles%\VIS pacote de suporte de transação sintética".
  
Para obter mais detalhes sobre como executar a transação sintética de VIS consulte a documentação para o cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Alterar a Frequência de Execução para Transações Sintéticas
<a name="special_synthetictrans"> </a>

Por padrão, as transações sintéticas serão executadas com usuários configurados a cada 15 minutos. As transações sintéticas são executados em sequência dentro de um conjunto de usuários para evitar que duas transações sintéticas entrem em conflito. Um intervalo mais longo é necessária para permitir que todas as transações sintéticas sejam concluídas a tempo.
  
Se você desejar executar transações sintéticas com mais frequência, o número de transações sintéticas executadas com um determinado conjunto de usuários deve ser diminuída a fim de que os testes possam ser concluídos em um intervalo de tempo desejado com algum buffer para eventuais atrasos na rede. Se você desejar executar mais transações sintéticas, crie mais conjuntos de usuário para executar transações sintéticas adicionais.
  
Para alterar a frequência de execução das transações sintéticas, siga estas etapas:
  
1. Abrir o System Center Operations Manager. Clique na seção Criação. Clique em regras de seção (abaixo de coautoria).
    
2. Na seção regras, encontre a regra com o nome "Main sintética transação Runner desempenho conjunto regra".
    
3. A regra, clique com botão direito e selecione substituições, selecione a regra de substituição e selecione "para todos os objetos da classe: Inspetor de Pool".
    
4. Na janela de substituir propriedades, selecione o nome do parâmetro "Frequência" e defina o valor de substituição para aquela desejada.
    
5. Na mesma janela, selecione o pacote de gerenciamento ao qual essa substituição precisa ser aplicada.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Usando Registro Avançado em Log para Transações Sintéticas
<a name="special_synthetictrans"> </a>

As transações sintéticas são extremamente úteis para ajudar a identificar problemas com o sistema. Por exemplo, o cmdlet Test-CsRegistration pode alertar os administradores para o fato de que usuários estavam enfrentando dificuldades de registro com o Skype for Business Server. No entanto, detalhes adicionais podem ser necessários para determinar a causa real de uma falha.
  
Por esse motivo, as transações sintéticas oferecem registro avançado em log. Com o registro avançado em log, para cada atividade assumida por uma transação sintética, as seguintes informações são registradas:
  
- A hora em que a atividade foi iniciada.
    
- A hora em que a atividade foi concluída.
    
- A ação que foi executada (por exemplo, criar, participar ou sair de uma conferência; fazer logon no Skype for Business Server; enviar uma mensagem instantânea).
    
- Informativo, detalhado, aviso ou mensagens de erro geradas quando a atividade foi executada.
    
- Mensagens de registro de SIP.
    
- Registros de exceção ou códigos de diagnóstico gerados quando a atividade foi executada.
    
- O resultado líquido da execução da atividade.
    
Essas informações são geradas automaticamente sempre que uma transação sintética for executada, mas não são exibidas automaticamente ou salvas em um arquivo de log. Se você estiver executando manualmente uma transação sintética, você pode usar o parâmetro OutLoggerVariable para especificar uma variável do Windows PowerShell no qual as informações serão armazenadas. A partir daqui, você tem a opção de usar um dos dois métodos a seguir para salvar e/ou visualizar mensagens de erro em log avançado no formato XML ou HTML. 
  
Para recuperar as informações sobre a solução, especifique o parâmetro OutLoggerVariable, seguido por um nome da variável que você escolher:
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Não preceda o nome da variável com o caractere $. Use um nome de variável como RegistrationTest (não $RegistrationTest). 
  
Quando executar este comando, você verá um resultado semelhante ao seguinte:
  
Fqdn de destino: atl-cs-001 resultado: latência de falha: 00:00:00 mensagem de erro: esta máquina não tem todos os certificados atribuídos. Diagnóstico: você pode acessar informações muito mais detalhadas para essa falha que apenas a mensagem de erro mostrada aqui.

Para acessar essas informações em formato HTML, use um comando semelhante a este para salvar as informações armazenadas na variável RegistrationTest em um arquivo HTML:
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Como alternativa, é possível usar o método ToXML() para salvar os dados em um arquivo XML:
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Você pode exibir esses arquivos usando o Windows Internet Explorer, o Microsoft Visual Studio ou qualquer outro aplicativo capaz de abrir arquivos HTML/XML.
  
Transações sintéticas executadas a partir de dentro do System Center Operations Manager irá gerar automaticamente esses arquivos de log para falhas. Esses logs não serão gerados se a execução falhar antes que o Skype for Business Server PowerShell seja capaz de carregar e executar a transação sintética. 
  
> [!IMPORTANT]
> Por padrão, o Skype para Business Server salva os arquivos de log para uma pasta que não seja compartilhada. Para tornar esses logs prontamente acessíveis, é preciso compartilhar essa pasta. Por exemplo: \\atl-watcher-001.litwareinc.com\WatcherNode. 
