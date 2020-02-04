---
title: Configurando os usuários do nó do Inspetor e configurações de configuração
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
ms.openlocfilehash: a3713844d5d2364459a28c5919bb1d32d421d706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Configurando os usuários de teste de nó do Inspetor e configurações de configuração no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-29_

Depois de configurar o computador que atuará como um nó do inspetor, você deve:

1.  Crie as contas de teste a serem usadas por estes nós do Inspetor. Se estiver usando o método de autenticação Negociar, você também deve usar o cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) para permitir o uso dessas contas de teste no nó do inspetor.

2.  Atualizar as definições de configuração do nó do inspetor.

Esta seção aborda:

  - Configurar contas de usuário de teste

  - Configurando um nó de Inspetor básico com as transações sintéticas padrão

  - Configurando testes estendidos

  - Adicionando e removendo transações sintéticas

  - Exibindo e testando a configuração do nó do inspetor

<div>

## <a name="configuring-test-user-accounts"></a>Configurar contas de usuário de teste

Os usuários de teste não precisam representar pessoas reais, mas devem ser contas válidas dos serviços de domínio Active Directory; Além disso, essas contas devem ser habilitadas para o Lync Server 2013, devem ter endereços SIP válidos e devem ser habilitadas para o Enterprise Voice (para usar a transação sintética test-CsPstnPeerToPeerCall). Se você usa o método de autenticação TrustedServer, tudo o que precisa fazer é verificar se essas contas existem e se foram configuradas como especificado aqui. É necessário atribuir pelo menos três usuários de teste a cada pool que deseja testar.

Se você estiver usando o método de autenticação Negotiate, também deverá usar o cmdlet **set-CsTestUserCredential** e o Shell de gerenciamento do Lync Server para permitir que essas contas de teste funcionem com as transações sintéticas. Você pode fazer isso executando um comando semelhante ao seguinte. (Esses comandos pressupõem que as três contas de usuário do Active Directory já foram criadas e que essas contas foram habilitadas para o Lync Server 2013.):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Observe que você deve incluir não somente o endereço SIP, mas também o nome de usuário e a senha. Se você não incluir a senha Set-CsTestUserCredential, o programa solicitará que você insira essas informações. O nome de usuário pode ser especificado usando o formato\\de nome de usuário do nome de domínio mostrado acima ou usando o nome Name@domain usuário do formato; por exemplo:

    -UserName "watcher3@litwareinc.com"

Para verificar se as credenciais do usuário de teste foram criadas, execute esses comandos no Shell de gerenciamento do Lync Server:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Informações semelhantes a isso devem ser retornadas para cada usuário:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurando um nó de Inspetor básico com as transações sintéticas padrão

Após a criação dos usuários de teste, você pode criar um nó de Inspetor usando um comando semelhante a este:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Esse comando cria um novo nó do inspetor que usa as configurações padrão e executa o conjunto padrão de transações sintéticas. O novo nó do inspetor também usa os usuários de teste watcher1@litwareinc.com, watcher2@litwareinc.com, e watcher3@litwareinc.com. Se o nó do Inspetor estiver usando a autenticação do TrustedServer, as três contas de teste poderão ser todas as contas de usuário válidas habilitadas para o Active Directory e o Lync Server. Se o nó do Inspetor estiver usando o método de autenticação Negotiate, você também deve habilitar essas contas de usuário para o nó de Inspetor usando o cmdlet **set-CsTestUserCredential** .

</div>

<div>

## <a name="configuring-extended-tests"></a>Configurando testes estendidos

Se você quiser habilitar a rede telefônica pública comutada (PSTN Test), que verifica a conectividade com a rede telefônica comutada pública, será necessário fazer algumas configurações adicionais ao configurar o nó do Inspetor. Primeiro, você precisa associar seus usuários de teste com o tipo de teste PSTN. Para fazer isso, execute um comando semelhante a isso dentro do Shell de gerenciamento do Lync Server:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Observe que os resultados desse comando devem ser armazenados em uma variável. Neste exemplo, isso é uma variável chamada $pstnTest.

Nesse ponto, você pode usar o cmdlet **New-CsWatcherNodeConfiguration** para associar o tipo de teste (armazenado na variável $pstnTest) a um pool do Lync Server 2013. Por exemplo, o comando a seguir cria uma nova configuração de nó de inspetor para o pool atl-cs-001.litwareinc.com, adicionando os três usuários de teste que foram criados anteriormente e adicionando também o tipo de teste PSTN:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Observe que o comando anterior falhará se você não tiver instalado os arquivos principais do Lync Server e o banco de dados do RTCLocal no computador do nó inspetor.

Para testar várias políticas de voz, você precisa criar um teste estendido para cada política usando o cmdlet **New-CsExtendedTest** . Os usuários atribuídos a esse teste devem ser configurados com as políticas de voz desejadas. Os testes estendidos são passados para o cmdlet **New-CsWatcherNodeConfiguration** usando um comando semelhante ao seguinte:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Se New-CsWatcherNodeConfiguration for chamado sem usar o parâmetro tests, isso significa que somente as transações sintéticas padrão (e a transação sintética estendida especificada) serão habilitadas para o novo nó inspetor. Isso significa que o nó do Inspetor testará os seguintes componentes:

  - Registro

  - IM

  - GroupIM (mensagens instantâneas de grupo)

  - P2PAV (sessões de áudio/vídeo ponto a ponto)

  - AvConference (áudio/conferência)

  - Presença

  - ABS (serviço do Catálogo de Endereços)

  - ABWQ (serviço Web do Catálogo de Endereços)

  - PSTN (chamadas de gateway PSTN, especificadas como teste estendido. Por padrão, PSTN está desabilitado. O teste está habilitado nesse caso somente porque o comando habilitou PSTN usando o parâmetro ExtendedTests.)

Isso também significa que os seguintes componentes não serão testados por padrão:

  - AVEdgeConnectivity

  - MCXP2PIM (mensagens instantâneas do dispositivo móvel)

  - ExumConnectivity (Unificação de Mensagens do Exchange)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Adicionando e removendo transações sintéticas

Após a configuração de um nó de Inspetor, você pode usar o cmdlet **set-CsWatcherNodeConfiguration** para adicionar ou remover transações sintéticas do nó. Por exemplo, para adicionar o teste PersistentChatMessage ao nó do inspetor, use o método Add e um comando semelhante a este:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

É possível adicionar vários testes separando os nomes de teste com vírgulas. Por exemplo:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Observe que um erro ocorrerá se um ou mais desses testes (por exemplo, dataconferência) já tiver sido habilitado no nó inspetor. Nesse caso, você receberá uma mensagem de erro semelhante a esta:

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Quando esse erro ocorre, nenhuma alteração será aplicada. O comando deve ser executado novamente com o teste duplicado removido.

Para remover uma transação sintética de um nó de Inspetor, use o método Remove em vez do método Add. Por exemplo, esse comando remove o teste ABWQ do nó do inspetor:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Você também pode usar o método Replace para substituir todos os testes habilitados no momento por um ou mais testes novos. Por exemplo, se você quiser apenas um nó de inspetor para executar o teste de mensagem instantânea, poderá configurá-lo usando este comando:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Quando você executa o comando anterior, todas as transações sintéticas do nó de Inspetor especificado serão desabilitadas, exceto para mensagens instantâneas.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Exibindo e testando a configuração do nó do inspetor

Se quiser exibir os testes que foram atribuídos ao nó do inspetor, use um comando semelhante a este:

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

O comando anterior retornará informações parecidas com isso, dependendo das transações sintéticas que foram atribuídas ao nó:

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
> Para exibir as transações sintéticas em ordem alfabética, use este comando:<BR>Get-CsWatcherNodeConfiguration-identidade "atl-cs-001.litwareinc.com" | Select-Object – ExpandProperty Tests | Sort-Object



</div>

Para verificar se um nó de inspetor foi criado, digite o seguinte comando no Shell de gerenciamento do Lync Server:

    Get-CsWatcherNodeConfiguration

Você receberá informações semelhantes a esta:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Para verificar se o nó do inspetor foi configurado corretamente, digite o seguinte comando no Shell de gerenciamento do Lync Server:

    Test-CsWatcherNodeConfiguration

O comando anterior testará cada nó de Inspetor em sua implantação e informará a você as informações, como se:

  - A função registrador necessária foi instalada.

  - A chave do Registro necessária foi criada para você quando você executou Set-CsWatcherNodeConfiguration.

  - Seus servidores estão executando a versão correta do Lync Server.

  - Suas portas foram configuradas corretamente.

  - Seus usuários de teste atribuídos têm as credenciais necessárias.

</div>

</div>

<span> </span>

</div>

</div>

</div>

