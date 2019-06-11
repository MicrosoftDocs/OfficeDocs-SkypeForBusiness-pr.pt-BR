---
title: Executar compatibilidade com versões anteriores para Servidor de Chat Persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b512d18449c881efd856674477a727cec137b64c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Executar compatibilidade com versões anteriores para Servidor de Chat Persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

O ponto de extremidade do Lync Server 2013, do servidor de chat persistente fornece uma maneira de criar uma URL simples que aponta para um pool de servidor de chat persistente. Isso é útil para clientes herdados (servidor de chat de grupo do Microsoft Office Communications Server 2007 R2 ou Lync Server 2010, chat em grupo) porque os usuários podem inserir uma URL simples na configuração manual ao tentar apontar o cliente herdado para um computador que esteja executando o Lync 2013, Chat persistente. Este ponto de extremidade não é usado pelo chat persistente e só é necessário para clientes herdados. Isso é útil para o período provisório em que as salas podem ser migradas, mas os clientes do Lync 2013 não foram implantados em toda a organização. Os usuários que estiverem executando o chat em grupo (cliente) do Lync 2010 ainda poderão se conectar ao servidor back-end persistente do servidor de chat.

Você não precisa criar vários pontos de extremidade do servidor de chat persistente; Você só precisa de um para cada pool de servidores de chat persistente. Os administradores podem criar vários pontos de extremidade (um por pool), mas os clientes herdados podem ser configurados para se conectar a apenas um pool de cada vez. No cenário habitual ou convencional, a implantação herdada é somente um pool. Uma nova implantação geralmente migra esse pool para um novo Lync Server 2013 e pode adicionar alguns novos pools de servidores de chat persistentes adicionais.

Este cenário principal geralmente segue este padrão:

  - Você administra os usuários com um Lync Server 2010, um pool de chat em grupo e seus clientes de chat em grupo do Lync 2010 se conectam a esse pool usando um usuário bem conhecido (\<SIP: OCSChat\>@ nome_do_domínioname. com ou uma semelhante). Os usuários são serviços de domínio do Active Directory habilitados para SIP e o serviço de pesquisa registra-se com eles para receber solicitações de entrada.

  - Em seguida, você instala um servidor de chat persistente do Lync Server 2013 e um pool de servidores de chat persistente.

  - Durante um período em que os usuários geralmente estão offline (por exemplo, um fim de semana):
    
      - Desative o Lync Server 2010, chat em grupo.
    
      - Migrar dados do Lync Server 2010, do pool de chat em grupo para o pool do servidor de chat persistente do Lync Server 2013.
    
      - Exclua o usuário conhecido dos serviços de domínio Active Directory.
    
      - Crie um novo *ponto de extremidade herdado* com o mesmo URI de SIP que o usuário conhecido excluído anteriormente.
    
      - Inicie os servidores de chat persistentes do Lync Server 2013.

  - Os usuários fazem logon novamente usando o seu cliente de grupo do Lync 2010 e se conectam aos dados sem precisar alterar nenhuma configuração.

  - Posteriormente, você poderá encerrar o Lync Server 2010, o chat em grupo. Em seguida, você pode implantar o Lync Server 2013, o servidor de chat persistente e instalar novos pools do servidor de chat persistente do Lync Server 2013.

Para obter detalhes sobre a migração do Lync Server 2010, o chat em grupo para o Lync Server 2013, o servidor de chat persistente, consulte [migração do Lync server 2010, chat em grupo ou Office Communications Server 2007 R2 Grupo chat para o Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Para executar a compatibilidade com versões anteriores (para criar um ponto de extremidade de servidor de chat persistente que aponta para um pool de servidores de chat persistente, que pode ser usado por clientes do pool de chat do grupo herdado):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Em seguida, configure os clientes de chat persistentes para usar esse endereço SIP como objeto de contato. O endereço SIP é criado com o cmdlet **New-CsPersistentChatEndpoint** para um pool específico do servidor de chat persistente.

Para adicionar o ponto de extremidade do servidor de chat persistente usando a interface de linha de comando do Windows PowerShell, considere o exemplo a seguir. Nesse caso, você está configurando o objeto de contato para ser chamado "persistentchat" na topologia "contoso.com", em que o nome de domínio totalmente qualificado (FQDN) do pool é "pcpool.contoso.com":

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>Confira também


[Migração do Lync Server 2010, Chat em Grupo ou Office Communications Server 2007 R2 Group Chat para Lync Server 2013, Servidor de Chat Persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

