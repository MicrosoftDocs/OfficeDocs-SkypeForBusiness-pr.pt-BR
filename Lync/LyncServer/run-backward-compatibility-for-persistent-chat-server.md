---
title: Executar compatibilidade com versões anteriores para servidor de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad689dace5e302cad8d41dff77dd575637b99ae6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Executar compatibilidade com versões anteriores para servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

O ponto de extremidade do Lync Server 2013, do servidor de chat persistente oferece uma maneira de criar uma URL simples que aponta para um pool de servidor de chat persistente. Isso é útil para clientes herdados (Microsoft Office Communications Server 2007 R2 Group Chat Server ou Lync Server 2010, chat de grupo) porque os usuários podem inserir uma URL simples na configuração manual ao tentar apontar o cliente herdado para um computador que executa o Lync 2013, Chat persistente. Este ponto de extremidade não é usado pelo chat persistente e é necessário somente para clientes herdados. Isso é útil para o período provisório onde as salas podem ser migradas, mas os clientes do Lync 2013 não foram implantados em toda a organização. Os usuários que executam o Lync 2010 Group Chat (cliente) ainda podem se conectar ao servidor back-end do servidor de chat persistente.

Você não precisa criar vários pontos de extremidade do servidor de chat persistente; Você só precisa de um para cada pool do servidor de chat persistente. Os administradores podem criar vários pontos de extremidade (um por pool), mas os clientes herdados podem estar configurados para conectar-se somente a um pool por vez. No cenário habitual ou importante, a implantação herdade é somente um pool. Uma nova implantação geralmente migra esse pool para um novo Lync Server 2013 e pode adicionar alguns novos pools de servidores de chat persistentes adicionais.

Esse cenário indispensável, geralmente, segue esse padrão:

  - Você administra usuários com um Lync Server 2010, pool de chat de grupo e seus clientes de chat de grupo do Lync 2010 se conectam a esse pool usando alguns usuários conhecidos (SIP padrão\<: OCSChat@ DomainName\>. com ou semelhante a um). Os usuários são serviços de domínio do Active Directory habilitados para SIP e o serviço de pesquisa registra com eles para receber solicitações de entrada.

  - Em seguida, você instala um servidor de chat persistente do Lync Server 2013 e um pool de servidor de chat persistente.

  - Durante um período no qual os usuários, geralmente, estão offline (por exemplo, um fim de semana):
    
      - Desative o Lync Server 2010, chat de grupo.
    
      - Migre dados do Lync Server 2010, pool de chat de grupo para o pool do servidor de chat persistente do Lync Server 2013.
    
      - Exclua o usuário conhecido dos serviços de domínio do Active Directory.
    
      - Crie um novo *ponto de extremidade herdado* com o mesmo URI do SIP do usuário conhecido excluído anteriormente.
    
      - Inicie os servidores de chat persistente do Lync Server 2013.

  - Os usuários fazem logon novamente usando seu chat de grupo do Lync 2010 (cliente) e se conectam aos seus dados sem precisar alterar nenhuma configuração.

  - Mais tarde, você pode encerrar o Lync Server 2010, o chat de grupo. Subsequentemente, você pode implantar o Lync Server 2013, o servidor de chat persistente e instalar novos pools do servidor de chat persistente do Lync Server 2013.

Para obter detalhes sobre como migrar do Lync Server 2010, o chat de grupo para o Lync Server 2013, servidor de chat persistente, consulte [migração do Lync server 2010, chat de grupo ou Office Communications Server 2007 R2 Group Chat to Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Para executar a compatibilidade com versões anteriores (para criar um ponto de extremidade de servidor de chat persistente que aponta para um pool de servidor de chat persistente, que pode ser usado por clientes do pool de chat de grupo herdado):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Em seguida, configure os clientes de chat persistente para usar esse endereço SIP como objeto de contato. O endereço SIP é criado com o cmdlet **New-CsPersistentChatEndpoint** para um pool de servidor de chat persistente específico.

Para adicionar o ponto de extremidade do servidor de chat persistente usando a interface de linha de comando do Windows PowerShell, considere o exemplo a seguir. Neste caso, você está configurando o  objeto de contato para ser chamado de "persistentchat" na topologia "contoso.com", no qual o nome de domínio totalmente qualificado (FQDN) do pool é "pcpool.contoso.com":

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

