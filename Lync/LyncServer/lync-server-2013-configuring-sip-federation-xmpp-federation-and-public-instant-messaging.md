---
title: Configurando federação SIP, federação XMPP e sistema de mensagens instântaneas público
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45abe0b4c32cf236912ad1a0e39f842653817e59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Configurando federação SIP, federação XMPP e sistema de mensagens instântaneas público no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

Federação, conectividade de mensagens instantâneas públicas e protocolo de presença e mensagens extensíveis (XMPP) definem uma classe diferente de usuários externos – usuários federados. Os usuários de uma implantação do Lync Server federado ou implantação do XMPP têm acesso a um conjunto limitado de serviços e são autenticados pela implantação externa. Os usuários remotos são membros da implantação do Lync Server e têm acesso a todos os serviços oferecidos pela sua implantação.

<div>


> [!NOTE]
> Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.



</div>

A conectividade de mensagens instantâneas públicas é um tipo especial de Federação que permite que um cliente do Lync Server acesse parceiros de mensagens instantâneas públicas configurados usando o Lync 2013. Os atuais parceiros de conectividade de mensagens instantâneas públicas são:

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Instant\!

Uma configuração pública de conectividade de mensagens instantâneas permite que os usuários do Lync acessem usuários de conectividade de mensagens instantâneas públicas:

  - Mensagens instantâneas e presença

  - Visibilidade de contatos públicos de conectividade de mensagens instantâneas no cliente do Lync

  - Pessoa a quem você conversa mensagens instantâneas com contatos

  - Chamadas de áudio e vídeo com usuários do Windows Live

A Federação do Lync Server define um contrato entre a implantação do Lync Server e outras implantações do Office Communications Server 2007 R2 ou Lync Server. Uma configuração federada do Lync Server permite que os usuários do Lync acessem usuários federados da seguinte forma:

  - Mensagens instantâneas e presença

  - Criação de contatos federados no cliente do Lync

A Federação XMPP define uma implantação externa baseada no protocolo de mensagens extensíveis e presença. Uma configuração do XMPP permite que os usuários do Lync acessem usuários de domínio do XMPP permitidos da seguinte forma:

  - Mensagem instantânea e presença – pessoa para pessoa apenas

  - Criação de contatos federados do XMPP no cliente do Lync

<div>


> [!IMPORTANT]
> O recurso XMPP do Lync Server 2013 é testado pela Microsoft e ela oferece suporte para federação de mensagens instantâneas com o Google Talk. Para quaisquer outros sistemas XMPP, entre em contato com o fornecedor do mesmo para verificar se eles suportam federação com o Lync Server 2013, e para quaisquer recomendações de implantação ou solução de problemas.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Federação externa do servidor de borda, conectividade de mensagens instantâneas públicas e processo de implantação de usuários do XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Permissões</th>
<th>Documentação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Determinar as opções para adicionar à implantação de borda existente</p></td>
<td><p>Execute o construtor de topologias para editar as configurações do servidor de borda e crie e publique a topologia. A topologia de borda existente replicará as alterações do repositório de gerenciamento central para o servidor de borda.</p></td>
<td><p>Grupo Administradores de domínio e grupo RTCUniversalServerAdmins</p>



> [!NOTE]
> Você pode editar uma topologia usando uma conta que seja membro do grupo usuários local, mas publicar uma topologia requer uma conta que seja membro do grupo Administradores do domínio e do grupo RTCUniversalServerAdmins

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Criando uma topologia de borda e de diretor no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Preparar-se para a instalação</p></td>
<td><ol>
<li><p>Certifique-se de que os pré-requisitos do sistema sejam atendidos.</p></li>
<li><p>Configurar registros DNS internos e externos para dar suporte à conectividade de mensagens instantâneas, ao agrupamento do Lync e à Federação do XMPP</p></li>
<li><p>Configurar portas e protocolos no firewall para dar suporte aos tipos de Federação que você está implantando</p></li>
<li><p>Obter e instalar certificados públicos. O tempo necessário para obter certificados depende de qual a autoridade de certificação (CA) emite o certificado. Esta etapa é opcional neste ponto da implantação. Se você não executar esta etapa neste ponto, deverá fazê-lo durante a configuração do servidor de borda. O serviço do servidor de borda não pode ser iniciado até que os certificados sejam obtidos</p></li>
</ol></td>
<td><p>Conforme apropriado para a sua organização, como essas funções geralmente são divididas entre vários grupos de trabalho</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planejando o SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configurar servidores de borda para cenários de Federação</p></td>
<td><ol>
<li><p>Transportar o arquivo de configuração de topologia exportado para cada servidor de borda ou permitir que a replicação seja concluída</p></li>
<li><p>Executar novamente o assistente de implantação para instalar componentes de suporte para Federação</p></li>
<li><p>Configurar os servidores de borda</p></li>
<li><p>Solicitar e instalar certificados para cada servidor de borda</p></li>
<li><p>Reiniciar os serviços do servidor de borda</p></li>
</ol></td>
<td><p>Grupo Administradores</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configuração de federação do Lync no Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configurar conectividade de mensagens instantâneas públicas no Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurando federação de XMPP no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar o suporte para acesso de usuário externo.</p></td>
<td><ol>
<li><p>Usar o painel de controle do Lync Server acesso externo do usuário</p></li>
<li><p>Configurar a política de acesso externo para permitir comunicações com usuários federados ou usuários públicos</p></li>
<li><p>Configurar domínios federados SIP para permitir ou bloquear domínios</p></li>
<li><p>Habilitar provedores federados SIP para provedores de conectividade de mensagens instantâneas públicas</p></li>
<li><p>Configurar parceiros federados do XMPP por domínio XMPP</p></li>
</ol></td>
<td><p>Grupo RTCUniversalServerAdmins ou conta de usuário atribuída à função CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurando suporte para acesso de usuário externo no Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurar criptografia de mídia para fornecedores públicos no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificar a configuração do servidor de borda</p></td>
<td><p>Verificar a conectividade do servidor e a replicação de dados de configuração de servidores internos</p></td>
<td><p>Para a verificação da replicação, do grupo RTCUniversalServerAdmins ou da conta de usuário que é atribuída ao CSAdministrator de verificação de roleFor da conectividade do usuário, um usuário para cada tipo de usuário federado</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Verificando a implantação de borda no Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Exemplo de configuração de XMPP no Lync Server 2013 – federação XMPP com Google Talk</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

