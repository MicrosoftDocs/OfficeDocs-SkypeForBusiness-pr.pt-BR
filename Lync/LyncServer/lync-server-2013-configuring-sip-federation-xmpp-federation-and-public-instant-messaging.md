---
title: Configurando Federação SIP, Federação XMPP e mensagens instantâneas públicas
description: Configurando Federação SIP, Federação XMPP e mensagens instantâneas públicas.
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
ms.openlocfilehash: 7b83c29da75c99e7a338bfd7732aec8ec49cbf47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556957"
---
# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Configurando Federação SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

Federação, conectividade de mensagem instantânea pública e protocolo XMPP (Extensible Messaging and Presence Protocol) definem uma classe diferente de usuários externos – os usuários federados. Os usuários de uma implantação federada do Lync Server ou do XMPP têm acesso a um conjunto limitado de serviços e são autenticados pela implantação externa. Os usuários remotos são membros da sua implantação do Lync Server e têm acesso a todos os serviços oferecidos pela sua implantação.

<div>


> [!NOTE]
> Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.



</div>

A conectividade de mensagens instantâneas públicas é um tipo especial de Federação que permite que um cliente do Lync Server acesse parceiros de mensagens instantâneas públicas configurados usando o Lync 2013. Os parceiros atuais de conectividade de mensagem instantânea pública são:

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Instant\!

Uma configuração de conectividade de mensagem instantânea pública permite que os usuários do Lync acessem usuários de conectividade de mensagem instantânea pública através de:

  - IM e presença

  - Visibilidade de contatos de  conectividade de mensagem instantânea pública no cliente Lync

  - Conversas entre duas pessoas com os contatos

  - Chamadas de áudio e vídeo com usuários do Windows Live

A federação do Lync Server define um acordo entre sua implantação do Lync Server e outras implantações do Office Communications Server 2007 R2 ou Lync Server. Uma configuração federada do Lync Server permite acesso dos usuários do Lync aos usuários federados através de:

  - IM e presença

  - Criação de contatos federados no cliente Lync

A federação XMPP define uma implantação externa baseada no protocolo XMPP (eXtensible Messaging and Presence Protocol). Uma configuração de XMPP permite o acesso dos usuários do Lync aos usuários de domínio XMPP através de:

  - IM e presença - apenas entre duas pessoas

  - Criação de contatos federados XMPP no cliente Lync

<div>


> [!IMPORTANT]
> O recurso XMPP do Lync Server 2013 é testado e suportado pela Microsoft para Federação de mensagens instantâneas com o Google Talk. Para qualquer outro sistema XMPP, entre em contato com o fornecedor terceirizado para verificar se eles suportam a Federação com o Lync Server 2013 e para qualquer recomendação de implantação ou solução de problemas.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Federação externa de servidor de borda, conectividade de mensagem instantânea pública e processo de implantação de usuários XMPP


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
<td><p>Determina as opções para adicionar à implantação de borda existente</p></td>
<td><p>Execute o construtor de topologias para editar as configurações do servidor de borda e crie e publique a topologia. A topologia de borda existente replicará as alterações do repositório de gerenciamento central para o servidor de borda.</p></td>
<td><p>Grupo de administradores de domínio e grupo RTCUniversalServerAdmins</p>



> [!NOTE]
> Você pode editar uma topologia usando uma conta que é membro do grupo de usuários locais, mas publicar uma topologia exige uma conta que seja membro de um grupo de administradores de domínio e do grupo RTCUniversalServerAdmins

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Criando uma topologia de borda e de diretor no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Preparar para instalação</p></td>
<td><ol>
<li><p>Garanta que os pré-requisitos do sistema sejam atendidos.</p></li>
<li><p>Configure registros DNS internos e externos para suportar conectividade de mensagens instantâneas públicas, federação Lync e federação XMPP</p></li>
<li><p>Configure portas e protocolos no firewall para suportar os tipos de federação que você está implantando</p></li>
<li><p>Obtenha e instale certificados públicos. O tempo necessário para obter certificados depende de qual autoridade de certificação (CA) emite o certificado. Esta etapa é opcional neste ponto da implantação. Se você não executar essa etapa nesse momento, será necessário fazê-lo durante a configuração do Servidor de Borda. O serviço de Servidor de Borda não pode ser iniciado até que o certificado seja obtido</p></li>
</ol></td>
<td><p>Conforme for apropriado para sua organização, pois essas funções são geralmente divididas entre vários grupos de trabalho</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planejamento para SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configure os Servidores de Borda para cenários de federação</p></td>
<td><ol>
<li><p>Transporte o arquivo de configuração de topologia exportado para cada Servidor de Borda ou permita que a replicação seja concluída</p></li>
<li><p>Execute novamente o Assistente de Implantação para instalar componentes de suporte para federação</p></li>
<li><p>Configura os Servidores de Borda</p></li>
<li><p>Solicite e instale certificados para cada Servidor de Borda</p></li>
<li><p>Reinicie os serviços dos Servidores de Borda

</p></li>
</ol></td>
<td><p>Grupo de administradores</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Configurando a Federação do Lync no Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configurando a conectividade de mensagens instantâneas públicas no Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurando a Federação XMPP no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar suporte para acesso de usuário externo.</p></td>
<td><ol>
<li><p>Usar o acesso de usuário externo do painel de controle do Lync Server</p></li>
<li><p>Configure a Política de Acesso Externo para permitir comunicação com usuários federados ou usuários públicos</p></li>
<li><p>Configure domínios federados SIP para permitir ou bloquear domínios</p></li>
<li><p>Habilite provedores federados SIP para provedores de conectividade de mensagens instantâneas</p></li>
<li><p>Configure os parceiros federados XMPP por domínio XMPP</p></li>
</ol></td>
<td><p>Grupo RTCUniversalServerAdmins ou conta de usuário atribuído à função CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurando suporte para acesso de usuário externo no Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurar a criptografia de mídia para provedores públicos no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verifique sua configuração do Servidor de Borda</p></td>
<td><p>Verifique a conectividade de servidor e replicação de dados de configuração de servidores internos</p></td>
<td><p>Para verificar a replicação, o grupo RTCUniversalServerAdmins ou conta do usuário que é atribuído à função CSAdministrator. Para verificação da conectividade do usuário, um usuário para cada tipo de usuário federado</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Verificando a implantação de borda no Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Exemplo de configuração de XMPP no Lync Server 2013 – Federação do XMPP com Google Talk</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

