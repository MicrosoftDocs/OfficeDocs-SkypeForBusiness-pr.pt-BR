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
ms.openlocfilehash: f5373984e3a4349d73974d9f3b6c243999fbb165
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Configurando os usuários de teste do nó do Inspetor e definições de configuração no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-29_

Depois de configurar o computador que atuará como um nó do inspetor, você deve:

1.  Criar as contas de teste que serão usadas por esses nós de inspetor. Se estiver usando o método de autenticação Negociar, você também deve usar o cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) para permitir o uso dessas contas de teste no nó do inspetor.

2.  Atualizar as definições de configuração do nó do inspetor.

Esta seção cobre:

  - Configurando contas de usuário de teste

  - Configurando uma Nó do inspetor básico com as Transações sintéticas padrão

  - Configurando Testes estendidos

  - Adicionando e removendo Transações sintéticas

  - Exibindo e testando a configuração do nó inspetor

<div>

## <a name="configuring-test-user-accounts"></a>Configurando contas de usuário de teste

Os usuários de teste não precisam representar pessoas reais, mas devem ser contas válidas dos serviços de domínio do Active Directory; Além disso, essas contas devem ser habilitadas para o Lync Server 2013, elas devem ter endereços SIP válidos e devem ser habilitadas para o Enterprise Voice (para usar a transação sintética test-CsPstnPeerToPeerCall). Se você usar o método de autenticação TrustedServer, então será necessário certificar-se de que essas contas existem e foram configuradas como especificado aqui. É necessário atribuir pelo menos três usuários de teste a cada pool que deseja testar.

Se você estiver usando o método de autenticação Negotiate, você também deve usar o cmdlet **set-CsTestUserCredential** e o Shell de gerenciamento do Lync Server para permitir que essas contas de teste funcionem com as transações sintéticas. Isso pode ser feito executando um comando semelhante a este. (Estes comandos presumem que as três contas de usuário do Active Directory já tenham sido criadas e que essas contas tenham sido habilitadas para o Lync Server 2013.):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Observe que é necessário incluir não apenas o endereço SIP, mas também o nome e a senha do usuário. Se não incluir a senha, Set-CsTestUserCredential solicitará que você insira essas informações. O nome de usuário pode ser especificado usando o formato\\nome de usuário do nome de domínio mostrado acima ou usando o nome de usuário do formato name@domain; por exemplo:

    -UserName "watcher3@litwareinc.com"

Para verificar se as credenciais do usuário de teste foram criadas, execute estes comandos de dentro do Shell de gerenciamento do Lync Server:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Informações semelhantes a estas devem ser retornadas para cada usuário:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurando uma Nó do inspetor básico com as Transações sintéticas padrão

Depois que os usuários de teste são criados, você pode criar um nó do inspetor usando um comando semelhante a este:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Esse comando cria um novo nó do inspetor que usa as configurações padrão e executa o conjunto padrão de transações sintéticas. O novo nó do inspetor também usa watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com dos usuários de teste. Se o nó do Inspetor estiver usando a autenticação do TrustedServer, as três contas de teste poderão ser todas as contas de usuário válidas habilitadas para o Active Directory e o Lync Server. Se o nó do inspetor está usando o método de autenticação Negociar, você também deve ativar essas contas do usuário para o nó do inspetor usando o cmdlet **Set-CsTestUserCredential**.

</div>

<div>

## <a name="configuring-extended-tests"></a>Configurando testes estendidos

Se você desejar ativar a rede telefônica pública comutada (teste da PSTN), que verifica a conectividade com a rede telefônica comutada, será necessário efetuar configurações adicionais ao configurar o nó do inspetor. Primeiro, é necessário associar seus usuários de teste ao tipo de teste da PSTN. Para fazer isso, execute um comando semelhante a este no Shell de gerenciamento do Lync Server:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Observe que os resultados desse comando devem ser armazenados em uma variável. Neste exemplo, é uma variável chamada de $pstnTest.

Neste ponto, você pode usar o cmdlet **New-CsWatcherNodeConfiguration** para associar o tipo de teste (armazenado na variável $pstnTest) a um pool do Lync Server 2013. Por exemplo, o seguinte comando cria uma nova configuração de nó do inspetor para o pool atl-cs-001.litwareinc.com, adicionando os três usuários de teste que foram criados anteriormente e também adicionando o tipo de teste de PSTN:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Observe que o comando anterior falhará se você não tiver instalado os arquivos principais do Lync Server e o banco de dados RTCLocal no computador do nó do observador.

Para testar várias políticas de voz, é necessário criar um teste estendido para cada política usando o cmdlet **New-CsExtendedTest**. Os usuários atribuídos ao teste devem ser configurados com as políticas de voz desejadas. Os testes estendidos são passados para o cmdlet **New-CsWatcherNodeConfiguration** usando um comando semelhante a este:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Se New-CsWatcherNodeConfiguration é chamado sem usar o parâmetro Testes, isso significa que somente as transações sintéticas Padrão (e a transação sintética estendida especificada) serão ativadas no novo nó do inspetor. Isso significa que o nó do inspetor testará os seguintes componentes:

  - Registro

  - Mensagens instantâneas

  - GroupIM

  - P2PAV (sessões de áudio/vídeo ponto a ponto)

  - AvConference (áudio/conferência)

  - Presença

  - ABS (serviço do Catálogo de Endereços)

  - ABWQ (serviço Web do Catálogo de Endereços)

  - PSTN (chamadas de gateway PSTN, especificadas como um teste estendido. Por padrão, a PSTN está desativada. O teste está ativado somente nesse caso, pois o comando ativou a PSTN usando o parâmetro ExtendedTests).

Isso também significa que os seguintes componentes não serão testados por padrão:

  - AVEdgeConnectivity

  - MCXP2PIM (mensagens instantâneas de dispositivo móvel)

  - ExumConnectivity (Unificação de Mensagens do Exchange)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Adicionando e removendo Transações sintéticas

Depois que um nó do inspetor é configurado, é possível usar o cmdlet **Set-CsWatcherNodeConfiguration** para adicionar ou remover transações sintéticas do nó. Por exemplo, para adicionar o teste PersistentChatMessage ao nó do inspetor, use o método Adicionar e um comando semelhante a este:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

É possível adicionar vários testes separando os nomes de teste com vírgulas. Por exemplo:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Observe que um erro ocorrerá se um ou mais desses testes (por exemplo, DataConference) já estiverem ativados no nó do inspetor. Nesse caso, você receberá uma mensagem de erro semelhante a esta:

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Quando esse erro ocorre, nenhuma alteração será aplicada. O comando deve ser executado novamente com o teste duplicado removido.

Para remover uma transação sintética do nó do inspetor, use o método Remover em vez de Adicionar. Por exemplo, esse comando remove o teste ABWQ do nó do inspetor:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

É possível usar o método Substituir para substituir todos os testes ativados no momento por um ou mais testes novos. Por exemplo, se desejar que apenas um nó do inspetor execute o teste IM, você pode configurar isso usando este comando:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Quando você executa o comando anterior, todas as transações sintéticas no nó do inspetor especificado serão desativadas exceto para IM.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Exibindo e testando a configuração do nó inspetor

Se quiser exibir os testes que foram atribuídos ao nó do inspetor, use um comando semelhante a este:

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

O comando anterior retornará informações semelhantes a essa, dependendo das transações sintéticas atribuídas ao nó:

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
> Para exibir as transações sintéticas em ordem alfabética, use este comando:<BR>Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object



</div>

Para verificar se um nó do inspetor foi criado, digite o seguinte comando no Shell de gerenciamento do Lync Server:

    Get-CsWatcherNodeConfiguration

Você receberá informações semelhantes a estas:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Para verificar se o nó do inspetor foi configurado corretamente, digite o seguinte comando no Shell de gerenciamento do Lync Server:

    Test-CsWatcherNodeConfiguration

O comando anterior testará o nó do inspetor em sua implantação e informará se:

  - A função Registrador necessária foi instalada.

  - A chave de registro necessária foi criada por você ao executar Set-CsWatcherNodeConfiguration.

  - Seus servidores estão executando a versão correta do Lync Server.

  - Suas portas foram configuradas corretamente.

  - Seus usuários de teste atribuídos têm as credenciais necessárias.

</div>

</div>

<span> </span>

</div>

</div>

</div>

