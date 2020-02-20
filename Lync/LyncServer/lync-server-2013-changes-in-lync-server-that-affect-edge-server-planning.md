---
title: 'Lync Server 2013: alterações no Lync Server que afetam o planejamento do servidor de borda'
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
ms.openlocfilehash: be2944125e5338dcc9b90b54f19fac003ec07287
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Alterações no Lync Server 2013 que afetam o planejamento do servidor de borda

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

O Lync Server 2013 introduz novos recursos que estendem os recursos e os métodos de comunicação para seus usuários. Além disso, o Lync Server 2013 introduz alterações nos serviços existentes para integrar e estender melhor os serviços que estão disponíveis para sua organização. Veja a seguir um resumo das alterações que podem afetar o planejamento e a implantação dos serviços do servidor de borda do Lync Server 2013.

<div>

## <a name="support-for-ipv6-addressing"></a>Suporte para endereçamento IPv6

O Lync Server 2013 oferece suporte ao endereçamento IPv6 para todos os serviços do servidor de borda. Se você tiver fornecido endereços IPv6 para as interfaces por meio da configuração no Windows Server, poderá usar endereços IPv6 na configuração do servidor de borda através da configuração de endereço IP no construtor de topologias. Além disso, o XMPP (Extensible Messaging and Presence Protocol) suporta IPv6. Nenhuma configuração adicional é necessária. Se o IPv6 estiver configurado na topologia, XMPP usará IPv6 (onde for necessário).

Um requisito adicionado para dar suporte ao IPv6 no Lync Server 2013 é criar registros de sistema de nomes de domínio para registros que devem ser descobertos e resolvidos para um endereço IPv6. O DNS IPv6 usa registros de host que são definidos como **aaaa** e chamados "quad-a". Outros tipos de registro são consistentes com seus correspondentes IPv4.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Suporte para implantação do protocolo XMPP (Extensible Messaging and Presence Protocol)

O servidor de borda introduz um proxy XMPP totalmente integrado (implantado nos servidores de borda) e um gateway do XMPP (implantado em seus servidores front-end). Você pode implantar a Federação do XMPP como um componente opcional. Ao adicionar e configurar o Gateway XMPP e o proxy do XMPP, você pode habilitar os usuários do Microsoft Lync 2013 para adicionar contatos de parceiros baseados em XMPP para mensagens instantâneas (IM) e presença.

<div>


> [!NOTE]  
> Atualmente, os serviços do XMPP no servidor de borda fornecem IM e presença entre os clientes do Lync Server e os contatos baseados em XMPP. Além disso, o XMPP está hospedado em apenas um site.



</div>

<div>


> [!IMPORTANT]  
> O recurso XMPP do Lync Server 2013 é testado e suportado pela Microsoft para Federação de mensagens instantâneas com o Google Talk. Para qualquer outro sistema XMPP, entre em contato com o fornecedor terceirizado para verificar se eles suportam a Federação com o Lync Server 2013 e para qualquer recomendação de implantação ou solução de problemas.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Suporte para autenticação de áudio/vídeo e servidor para certificados de autenticação de servidor

Um certificado é usado para gerar tokens emitidos para clientes e outros consumidores do serviço de autenticação A/V e para autenticação de servidor para servidor. O certificado de autenticação de áudio/vídeo é do tipo *AudioVideoAuthentication* e o certificado de autenticação de servidor para servidor é do tipo *OAuthTokenIssuer*.

Para autenticação de áudio/vídeo, os tokens são usados para autenticar solicitações de alocação de porta e os tokens são armazenados em cache por até 8 horas – o tempo de vida padrão do token. Em operação normal, este é um método muito confiável para criar e distribuir o material de autenticação para os clientes A/V. No entanto, os certificados têm uma vida útil finita e expiram em uma data e hora predefinidas (com base na data de criação e nas políticas impostas na autoridade de certificação que criou o certificado, normalmente 2 anos para esse tipo de certificado). Quando o certificado expira, todos os tokens criados pelo certificado expirado e armazenados em cache por consumidores não são válidos. Qualquer tentativa de usar um token criado com um certificado expirado resultaria em uma falha nas alocações de retransmissão de mídia e nas sessões de áudio/vídeo atuais. O cliente precisaria adquirir um novo token criado por um certificado válido para retomar a funcionalidade normal de áudio e vídeo.

A autenticação de servidor para servidor é gerenciada por um certificado global solicitado e aplicado a todos os servidores na implantação. O certificado é responsável por autenticar servidores no Lync Server 2013, bem como autenticação no Exchange 2013 e no Microsoft SharePoint Server 2013. Para obter mais informações sobre como funciona a autenticação de servidor para servidor, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Uma diferença muito importante entre o processo de autenticação de áudio/vídeo e o processo de autenticação de servidor para servidor é o tempo de vida da autenticação ou tokens. Para autenticação de áudio/vídeo, a autenticação expira após oito horas. A autenticação de servidor para servidor tem um tempo de vida de 24 horas. Você deve planejar adequadamente para cada um dos tipos de certificado.

Novo no Lync Server 2013 é a capacidade de transferir um certificado de autenticação de áudio/vídeo e servidor para o certificado de autenticação de servidor para o servidor com antecedência da expiração do certificado atual. O novo certificado é usado para gerar novos tokens ou novas solicitações de autenticação. Mas mantém o certificado antigo para verificar as sessões e autenticações atuais.. O que isso faz é evitar efetivamente praticamente todas as falhas devido a expirações de token e certificado. Para obter detalhes sobre esse recurso e como configurá-lo, consulte [preparando o AV e certificados OAuth no Lync Server 2013 using-rolo in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Dependência reduzida na afinidade baseada em cookies

Nas versões anteriores do Lync Server e Office Communications Server, a afinidade baseada em cookies foi usada pelos serviços Web para garantir que o estado de sessão do cliente e dos serviços Web tenha sido mantido. Os serviços Web do Lync Server 2013 usam um mecanismo de afinidade interno que elimina a maioria dos requisitos para afinidade com base em cookies.

<div>


> [!WARNING]  
> O cliente móvel do Microsoft Lync 2010 ainda deve usar a afinidade com base em cookies e exigirá a configuração da afinidade com base em cookies até que você tenha migrado todos os clientes para o futuro cliente móvel Microsoft Lync (data da versão ainda não determinada).



</div>

Para obter detalhes sobre a afinidade baseada em cookies no Lync Server 2013, consulte os [componentes necessários para acesso de usuário externo no Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).

</div>

<div>

## <a name="autodiscover-enhancements"></a>Aprimoramentos de descoberta automática

O recurso de descoberta automática no Lync Server 2013 permite que os clientes localizem recursos adicionais que são disponibilizados para comunicação. A descoberta automática foi introduzida pela primeira vez na atualização cumulativa do Lync Server 2010: novembro de 2011 para mobilidade e Microsoft Lync 2010 Mobile. O recurso de descoberta automática (também conhecido pelos nomes de registro DNS LyncDiscover e LyncDiscoverInternal) permite que os clientes localizem e usem serviços de mobilidade (para clientes móveis do Microsoft Lync 2010), o Microsoft Lync Web App e o Web Scheduler do Lync, bem como comunicação com o Microsoft Exchange Server e o SharePoint Server. A descoberta automática é instalada como parte normal da configuração e implantação de sua infraestrutura e dos servidores do Lync Server 2013. O assistente de implantação do construtor de topologia e do Lync Server eliminam a maioria das tarefas de configuração que foram necessárias na atualização cumulativa do Lync Server 2010: novembro de 2011.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Serviços para clientes móveis

Apresentado na atualização cumulativa do Lync Server 2010: de novembro de 2011, serviços de mobilidade no Lync Server 2013 habilitar telefones móveis executando Lync Mobile e dispositivos tablets usando dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia compatíveis para executar atividades como enviar e receber mensagens instantâneas, exibir contatos e ver a presença. Além disso, os dispositivos móveis são compatíveis com alguns recursos do Enterprise Voice, como clique para ingressar em uma conferência, ligar via trabalho, alcance de um único número, caixa postal e notificação de chamada perdida.

<div>


> [!NOTE]  
> Os serviços de mobilidade usam o proxy reverso e os serviços publicados que são implantados em seus servidores front-end. Nenhuma alteração é necessária para os servidores de borda. Minimamente você precisa de SIP/TCP/5061from de saída do servidor que executa o serviço de borda de acesso do Lync Server.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>A função diretor é opcional

A função do servidor Diretor na topologia do Lync Server 2013 não foi alterada. Ele ainda hospeda serviços Web, autentica solicitações de usuário recebidas e direciona usuários externos para o pool inicial. Ao alterar o diretor de uma função recomendada para uma função opcional, a Microsoft não pretende diminuir o valor do diretor. A intenção é reduzir a contagem de servidores e outros requisitos de hardware (por exemplo, balanceadores de carga de hardware para o diretor) sem comprometer recursos e funcionalidades. Como os servidores de front-end podem fazer o mesmo trabalho que o diretor sem impacto nos serviços fornecidos, você pode implantar diretores se você escolher. Você pode excluir com segurança o diretor com confiança de que os servidores front-end fornecerão os mesmos serviços no lugar de um diretor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

