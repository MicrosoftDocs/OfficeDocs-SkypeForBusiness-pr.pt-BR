---
title: 'Lync Server 2013: instruções de configuração especiais para transações sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c2f0f45aa2187f1b47f8dfa81b3ba121388f6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Instruções de configuração especiais para transações sintéticas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-11-16_

A maioria das transações sintéticas pode ser executada em um nó de Inspetor como está; ou seja, assim que a transação sintética tiver sido adicionada às configurações do nó do Inspetor, o nó do Inspetor poderá começar a usar a transação sintética durante o teste. No entanto, isso não é verdade para todas as transações sintéticas. As exceções – transações sintéticas que exigem instruções de configuração especiais – são discutidas nas seções a seguir.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Lidando com erros de tempo limite do servidor

Em alguns casos, você pode descobrir que suas transações sintéticas estão falhando com erros de tempo limite do servidor (código de erro 504). Esses erros costumam ocorrer devido a problemas de firewall. Quando uma transação sintética é executada, essa transação é executada no processo MonitoringHost. exe; por sua vez, o MonitoringHost. exe inicia uma instância do processo PowerShell. exe. Se o MonitoringHost. exe ou o PowerShell. exe estiverem bloqueados pelo seu firewall, a transação sintética falhará e gerará um erro do 504.

Para solucionar esse problema, você deve criar manualmente regras de firewall de entrada para MonitoringHost. exe e PowerShell. exe no computador local. Isso pode ser feito pelo firewall do Windows ou por um software de firewall local de terceiros, dependendo da configuração pré-existente do seu servidor.

Se você estiver empregando um dispositivo de firewall de rede entre a máquina de host de transação sintética e os servidores do Lync que está tentando monitorar, deve tratar o host como uma máquina cliente e usar o observador de todos os requisitos de porta do firewall de [portas e protocolos para servidores internos no Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Transações sintéticas de conferência de dados

Se o seu computador do nó do observador estiver localizado fora de sua rede de perímetro, provavelmente não será possível executar a transação sintética de data Conferencing, a menos que você primeiro desabilite as configurações de proxy do Internet Explorer para a conta de serviço de rede. Para desativar as configurações de proxy para esse serviço, conclua o seguinte procedimento:

1.  No computador do nó do Inspetor, clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e clique em **Executar como administrador**.

2.  Na janela do console, digite o seguinte comando e pressione ENTER:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

A seguinte mensagem aparecerá na janela de comando:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Essa mensagem significa que você desabilitou as configurações de proxy do Internet Explorer para a conta de serviço de rede.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Transações sintéticas da Unificação de mensagens do Exchange

A transação sintética de Unificação de Mensagens do Exchange verifica se usuários de teste podem se conectar a contas de correio de voz hospedadas no Exchange. Esses usuários de teste precisarão ser pré-configurados com contas de correio de voz antes de poderem usar os testes de UM do Exchange.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Transações sintéticas de chat persistente

Para usar a transação de chat sintética persistente, os administradores devem primeiro criar um canal e conceder permissões aos usuários de teste para usá-lo. O cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) pode ser usado para configurar corretamente esses usuários de teste:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Esta tarefa de configuração deve ser executada dentro da empresa:

  - Se executado de um computador que não seja do servidor, o usuário que executa o cmdlet deve ser um membro da função PersistentChatAdministrators para o controle de acesso baseado em função (RBAC).

  - Se executado do próprio servidor, o usuário que executa o cmdlet deve ser um membro do grupo RTCUniversalServerAdmins.

No comando anterior, o parâmetro setup foi incluído e definido como true ($True). Se você incluir o parâmetro setup, Test-CsPersistentChatMessage criará uma sala de chat persistente especial e preencherá essa sala com os usuários de teste. Isso ajuda a garantir que, na verdade, não há uma sala de chat disponível para fins de teste. Observe que o parâmetro setup só deve ser executado em um servidor front-end.

A sala de chat criada por Test-CsPersistentChatMessage pode ser excluída somente por um administrador.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Transações sintéticas de chamada ponto a ponto PSTN

A transação sintética [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) verifica a capacidade de colocar e receber chamadas por meio da rede telefônica pública comutada (PSTN).

Para executar essa transação sintética, os administradores devem configurar:

  - Dois usuários de teste (um chamador e um receptor) habilitados para o Enterprise Voice.

  - Números DID (Discagem Interna Direta) para cada conta de usuário.

  - Políticas de voz e rotas de voz que permitem que as chamadas para o número do destinatário atinjam o gateway PSTN.

  - Um gateway PSTN que aceita chamadas e mídia que roteia chamadas para o pool inicial de um receptor com base no número discado.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Transações sintéticas de repositório de contatos unificado

A transação sintética do repositório de contatos unificado verifica se o Lync Server 2013 é capaz de recuperar contatos em nome de um usuário do Microsoft Exchange Server 2013.

Para usar essa transação sintética, as seguintes condições devem ser atendidas:

  - [Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) deve ser configurado entre o lync Server 2013 e o Exchange 2013.

  - Os usuários de teste devem ter uma caixa de correio válida do Exchange 2013.

Depois que essas condições forem atendidas, os administradores poderão executar o seguinte comando para verificar se o usuário com o endereço SIP kenmyer@litwareinc.com pode recuperar seus contatos do repositório de contatos unificado:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Observe o uso do parâmetro setup usado no comando anterior. Se o parâmetro setup estiver incluído ao executar Test-CsUnifiedContactStore, os contatos do usuário especificado (neste caso, sip:kenmyer@litwareinc.com) serão movidos para o repositório de contatos unificado. (Naturalmente, se os contatos do usuário já estiverem no repositório de contatos unificado, eles não precisam ser movidos.) O parâmetro setup geralmente é usado apenas uma vez (a primeira vez que o CsUnifiedContactStore é executado) e só deve ser usado com usuários de teste; ou seja, com contas de usuário que nunca serão realmente conectadas ao Lync Server. Após o usuário do teste ter sido migrado para o repositório de contatos unificado, você pode verificar se os contatos do usuário podem ser recuperados chamando Test-CsUnifiedContactStore sem o parâmetro setup:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Transações sintéticas XMPP

A transação sintética de mensagem de chat XMPP (Extensible Messaging and Presence Protocol) requer que o recurso XMPP seja configurado com um ou mais domínios federados.

Para habilitar a transação sintética XMPP, um parâmetro XmppTestReceiverMailAddress deve ser fornecido com uma conta de usuário em um domínio de XMPP roteável. Por exemplo:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

Neste exemplo, será preciso existir uma regra do Lync Server 2013 para direcionar as mensagens para o litwareinc.com para um Gateway XMPP.

</div>

</div>

<span> </span>

</div>

</div>

</div>

