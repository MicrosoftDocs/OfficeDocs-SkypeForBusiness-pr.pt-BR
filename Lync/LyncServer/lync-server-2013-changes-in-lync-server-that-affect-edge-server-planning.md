---
title: 'Lync Server 2013: Alterações no Lync Server que afetam o planejamento do Servidor de Borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73eda15acbce7eb4b47a0a52602776e8fc830b0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Alterações no Lync Server 2013 que afetam o planejamento do Servidor de Borda

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

O Lync Server 2013 introduz novos recursos que ampliam os recursos e métodos de comunicação para seus usuários. Além disso, o Lync Server 2013 introduz alterações em serviços existentes para integrar melhor e estender os serviços que estão disponíveis para sua organização. Veja a seguir um resumo das alterações que podem afetar o planejamento e a implantação de serviços do servidor de borda do Lync Server 2013.

<div>

## <a name="support-for-ipv6-addressing"></a>Suporte para endereçamento IPv6

O Lync Server 2013 dá suporte ao endereçamento IPv6 para todos os serviços de servidor de borda. Se você tiver fornecido endereços IPv6 para as interfaces por meio da configuração no Windows Server, poderá usar endereços IPv6 na configuração do servidor de borda por meio da configuração do endereço IP no construtor de topologias. Além disso, o protocolo de presença e mensagens extensível (XMPP) é compatível com IPv6. Nenhuma configuração adicional é necessária. Se o IPv6 estiver configurado na topologia, o XMPP usará IPv6 (quando necessário).

Um requisito adicional para dar suporte ao IPv6 no Lync Server 2013 é criar registros de sistema de nome de domínio para registros que devem ser descobertos e resolvidos para um endereço IPv6. O DNS IPv6 usa registros de host que são definidos como **aaaa** e chamados "quad-a". Outros tipos de registro são consistentes com seus correspondentes IPv4.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Suporte para implantação de protocolo de presença e mensagens extensíveis (XMPP)

O servidor de borda introduz um proxy XMPP totalmente integrado (implantado nos servidores de borda) e um Gateway XMPP (implantado em seus servidores front-end). Você pode implantar a Federação do XMPP como um componente opcional. Ao adicionar e configurar o XMPP proxy e o gateway do XMPP, você pode habilitar seus usuários do Microsoft Lync 2013 para adicionar contatos de parceiros baseados no XMPP para mensagens instantâneas (IM) e presença.

<div>


> [!NOTE]  
> Atualmente, os serviços do XMPP no servidor de borda só fornecem mensagens instantâneas e presença entre os clientes do Lync Server e os contatos baseados no XMPP. Além disso, o XMPP é hospedado em apenas um site.



</div>

<div>


> [!IMPORTANT]  
> O recurso XMPP do Lync Server 2013 é testado pela Microsoft e ela oferece suporte para federação de mensagens instantâneas com o Google Talk. Para quaisquer outros sistemas XMPP, entre em contato com o fornecedor do mesmo para verificar se eles suportam federação com o Lync Server 2013, e para quaisquer recomendações de implantação ou solução de problemas.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Suporte para a interrupção da autenticação de áudio/vídeo e do servidor para certificados de autenticação do servidor

Um certificado é usado para gerar tokens que são emitidos para clientes e outros consumidores do serviço de autenticação A/V e para autenticação do servidor para o servidor. O certificado de autenticação de áudio/vídeo é do tipo *AudioVideoAuthentication* e o certificado de autenticação do servidor para o servidor é do tipo *OAuthTokenIssuer*.

Para autenticação de áudio/vídeo, os tokens são usados para autenticar solicitações de alocação de porta e os tokens são armazenados em cache por até 8 horas – o tempo de vida padrão do token. Em operação normal, esse é um método muito confiável para criar e distribuir material de autenticação para os consumidores a/V. No entanto, os certificados têm uma vida útil finita e expiram em uma data e hora predefinidas (com base na data de criação e nas políticas impostas na autoridade de certificação que criou o certificado, geralmente há 2 anos para esse tipo de certificado). Quando o certificado expira, todos os tokens criados pelo certificado expirado e armazenados em cache por consumidores se tornam inválidos. Qualquer tentativa de usar um token criado com um certificado expirado resultará em falha nas atribuições de retransmissão de mídia e nas sessões de áudio/vídeo atuais. O cliente precisaria adquirir um novo token criado por um certificado válido para retomar a funcionalidade normal de áudio e vídeo.

A autenticação do servidor para o servidor é gerenciada por um certificado global que é solicitado e aplicado a todos os servidores na implantação. O certificado é responsável pela autenticação de servidores no Lync Server 2013, bem como pela autenticação do Exchange 2013 e do Microsoft SharePoint Server 2013. Para obter mais informações sobre como funciona a autenticação do servidor com o servidor, consulte [Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Uma diferença muito importante entre o processo de autenticação de áudio/vídeo e o processo de autenticação do servidor no servidor é o tempo de vida da autenticação ou dos tokens. Para a autenticação de áudio/vídeo, a autenticação expira após oito horas. A autenticação de servidor para servidor tem uma vida útil de 24 horas. Você deve planejar adequadamente para cada um dos tipos de certificado.

Novo para o Lync Server 2013 é a capacidade de transferir um certificado de autenticação de áudio/vídeo e um certificado de autenticação de servidor para servidor com antecedência da expiração do certificado atual. O novo certificado é usado para gerar novos tokens ou novas solicitações de autenticação. mas retém o certificado antigo para verificar as sessões e autenticações atuais.. O que isso faz é evitar efetivamente praticamente todas as falhas devido a expirações de token e certificado. Para obter detalhes sobre esse recurso e como configurá-lo, consulte [preparando certificados do AV e do OAuth no Lync Server 2013 using-roll Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Dependência reduzida na afinidade baseada em cookies

Em versões anteriores do Lync Server e do Office Communications Server, a afinidade baseada em cookies era usada pelos serviços Web para garantir que o estado da sessão do cliente e dos serviços Web tenha sido mantido. Os serviços Web do Lync Server 2013 usam um mecanismo de afinidade interno que elimina a maioria dos requisitos para afinidade baseada em cookies.

<div>


> [!WARNING]  
> O cliente móvel do Microsoft Lync 2010 ainda deve usar afinidade baseada em cookies e exigirá a configuração da afinidade baseada em cookies até que você migre todos os clientes para o próximo cliente móvel do Microsoft Lync (data do lançamento ainda não determinado).



</div>

Para obter detalhes sobre a afinidade baseada em cookies no Lync Server 2013, consulte [componentes necessários para o acesso de usuários externos no Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).

</div>

<div>

## <a name="autodiscover-enhancements"></a>Aprimoramentos de descoberta automática

O recurso descoberta automática no Lync Server 2013 permite que os clientes localizem recursos adicionais que são disponibilizados para comunicação. A descoberta automática foi introduzida pela primeira vez na atualização cumulativa do Lync Server 2010: novembro de 2011 para Mobility e Microsoft Lync 2010 Mobile. O recurso de descoberta automática (também conhecido pelos nomes de registros de DNS LyncDiscover e LyncDiscoverInternal) permite que os clientes localizem e usem serviços de mobilidade (para clientes móveis do Microsoft Lync 2010), o Microsoft Lync Web App e o Lync Web Scheduler, bem como comunicações com o Microsoft Exchange Server e o SharePoint Server. A descoberta automática é instalada como parte normal da configuração e implantação de sua infraestrutura e dos servidores do Lync Server 2013. O construtor de topologias e o assistente de implantação do Lync Server eliminam a maioria das tarefas de configuração necessárias na atualização cumulativa do Lync Server 2010:2011 de novembro.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Serviços para clientes móveis

Apresentado na atualização cumulativa do Lync Server 2010: serviços de mobilidade de novembro de 2011 no Lync Server 2013 habilitar telefones celulares que executam dispositivos móveis do Lync e tablets com dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia para executar atividades como enviar e receber mensagens instantâneas, ver contatos e ver a presença. Além disso, os dispositivos móveis dão suporte a alguns recursos de voz empresarial, como o clique para ingressar em uma conferência, fazer chamadas por meio de trabalho, de alcance de número único, caixa postal e notificação de chamada perdida.

<div>


> [!NOTE]  
> Os serviços de mobilidade usam o proxy reverso e os serviços publicados que são implantados em seus servidores front-end. Nenhuma alteração é necessária para servidores Edge. Minimamente, você precisa do SIP/TCP/5061from o servidor que executa o serviço de borda de acesso ao Lync Server.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>A função diretor é opcional

A função do servidor Diretor na topologia do Lync Server 2013 não mudou. Ele ainda hospeda serviços Web, autentica solicitações do usuário recebidas e direciona os usuários externos para o pool inicial. Ao alterar o diretor de uma função recomendada para uma função opcional, a Microsoft não pretende diminuir o valor do diretor. A intenção é reduzir a contagem do servidor e outros requisitos de hardware (por exemplo, balanceadores de carga de hardware para o diretor) sem comprometer recursos e funcionalidades. Como os servidores de front-end podem fazer o mesmo trabalho que o diretor sem impacto nos serviços fornecidos, você pode implantar diretores se optar por fazê-lo. Você pode excluir com segurança o diretor com certeza de que os servidores de front-end fornecerão os mesmos serviços no lugar de um diretor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

