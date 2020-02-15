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
ms.openlocfilehash: a749e4349f6dae6ab7cae079af443734f9cfbc15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Instruções especiais de configuração para transações sintéticas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-11-16_

A maioria das transações sintéticas pode ser executada em um nó do inspetor no estado em que se encontram, ou seja, assim que uma transação sintética é adicionada às configurações do nó do inspetor, ele pode começar a usá-la durante as fases de teste. No entanto, isso não ocorre para todas as transações sintéticas. As exceções (transações que exigem instruções de configuração especiais) são abordadas nas seções a seguir.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Lidando com erros de tempo limite do servidor

Em alguns casos, você pode descobrir que suas transações sintéticas estão falhando com erros de tempo limite do servidor (código de erro 504). Esses erros costumam ocorrer devido a problemas de firewall. Quando uma transação sintética é executada, essa transação é executada no processo MonitoringHost. exe; por sua vez, MonitoringHost. exe inicia uma instância do processo PowerShell. exe. Se o MonitoringHost. exe ou o PowerShell. exe estiver bloqueado pelo firewall, a transação sintética falhará e gerará um erro 504.

Para resolver esse problema, você deve criar manualmente regras de firewall de entrada para MonitoringHost. exe e PowerShell. exe no computador local. Isso pode ser feito por meio do firewall do Windows ou de um software de firewall local de terceiros, dependendo da configuração preexistente do seu servidor.

Se você estiver usando um dispositivo de firewall de rede entre a máquina de host de transação sintética e os servidores Lync que você está tentando monitorar, você deve tratar o host como uma máquina cliente e o observador de todos os requisitos de porta de firewall de [portas e protocolos para servidores internos no Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Transações sintéticas de conferência de dados

Se o computador do nó do observador estiver localizado fora da rede de perímetro, provavelmente você não poderá executar a transação sintética de audioconferência, a menos que primeiro desabilite as configurações de proxy do Internet Explorer para a conta de serviço de rede. Para desabilitar as configurações de proxy para esse serviço, execute o procedimento a seguir:

1.  No computador do nó do observador, clique em **Iniciar**, em **Todos os programas**, em **Acessórios**, clique com o botão direito no **Prompt de comando** e clique em **Executar como administrador**.

2.  Na janela do console, digite o seguinte comando e pressione ENTER:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

A seguinte mensagem será exibida na janela de comando:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Essa mensagem significa que você desabilitou as configurações de proxy do Internet Explorer para a conta de serviço de rede.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Transações sintéticas de Unificação de Mensagens do Exchange

A transação sintética de Unificação de mensagens (UM) do Exchange verifica se os usuários de teste podem se conectar às contas de caixa postal hospedadas no Exchange. Esses usuários de teste precisarão ser pré-configurados com contas de caixa postal para poderem usar os testes de UM do Exchange.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Transações sintéticas de chat persistente

Para usar a transação sintética de chat persistente, os administradores devem primeiro criar um canal e conceder permissões aos usuários de teste para usá-lo. O cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) pode ser usado para configurar corretamente os usuários de teste:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Esta tarefa de configuração deve ser realizada de dentro da empresa:

  - Se ela for realizada de uma máquina que não é um servidor, o usuário que executar o cmdlet deverá ser um membro da função PersistentChatAdministrators do RBAC (Controle de Acesso Baseado em Função).

  - Se ela for realizada a partir do próprio servidor, o usuário que executar o cmdlet deverá ser um membro do grupo RTCUniversalServerAdmins.

No comando anterior, o parâmetro Setup foi incluído e definido como True ($True). Se você incluir o parâmetro setup, o Test-CsPersistentChatMessage criará uma sala de chat persistente especial e preencherá essa sala com os usuários de teste. Isso ajudará a garantir que haja uma sala de chat real disponível para fins de teste. Observe que o parâmetro Setup deve ser executado apenas de um servidor front-end.

A sala de chat criada por Test-CsPersistentChatMessage só pode ser excluída por um administrador.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Transações sintéticas de chamada ponto a ponto PSTN

A transação sintética [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) verifica a capacidade de colocar e receber chamadas através da rede telefônica pública comutada (PSTN).

Para executar essa transação sintética, os administradores devem configurar:

  - Dois usuários de teste (um chamador e um receptor) habilitados para o Enterprise Voice.

  - Números DID (Discagem Interna Direta) para cada conta de usuário.

  - Políticas e rotas de voz que permitem que chamadas para o número do receptor cheguem ao gateway PSTN.

  - Um gateway PSTN que aceita chamadas e mídia que encaminha os retornos de chamada para o pool primário de um receptor com base no número discado.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Transações sintéticas do repositório unificado de contatos

A transação sintética do repositório unificado de contatos verifica se o Lync Server 2013 pode recuperar contatos em nome de um usuário do Microsoft Exchange Server 2013.

Para usar essa transação sintética, as seguintes condições devem ser atendidas:

  - [Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) deve ser configurado entre o lync Server 2013 e o Exchange 2013.

  - Os usuários de teste devem ter uma caixa de correio do Exchange 2013 válida.

Depois que essas condições forem atendidas, os administradores poderão executar o seguinte comando para verificar se o usuário com o endereço SIP kenmyer@litwareinc.com pode recuperar seus contatos do repositório unificado de contatos:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Observe o uso do parâmetro setup usado no comando anterior. Se o parâmetro setup estiver incluído durante a execução de Test-CsUnifiedContactStore, os contatos do usuário especificado (neste caso, sip:kenmyer@litwareinc.com) serão movidos para o repositório unificado de contatos. (Obviamente, se os contatos do usuário já estiverem no repositório unificado de contatos, eles não precisarão ser movidos.) Normalmente, o parâmetro Setup é usado apenas uma vez (a primeira vez que Test-CsUnifiedContactStore é executado) e só deve ser usado com usuários de teste; ou seja, com contas de usuário que nunca serão realmente conectadas ao Lync Server. Após a migração do usuário de teste para o repositório unificado de contatos, você pode verificar se os contatos do usuário podem ser recuperados chamando Test-CsUnifiedContactStore sem o parâmetro setup:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Transações sintéticas XMPP

A transação sintética de IM do protocolo XMPP exige que o recurso XMPP seja configurado com um ou mais domínios federados.

Para habilitar a transação sintética XMPP, um parâmetro XmppTestReceiverMailAddress deve ser fornecido com uma conta de usuário em um domínio XMPP roteável. Por exemplo:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

Neste exemplo, uma regra do Lync Server 2013 precisará existir para rotear mensagens para o litwareinc.com para um Gateway XMPP.

</div>

</div>

<span> </span>

</div>

</div>

</div>

