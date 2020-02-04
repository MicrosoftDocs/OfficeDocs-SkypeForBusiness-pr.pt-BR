---
title: Planejando o SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 994a1395363c28976c8bbfe325edae99e97cdc48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Planejando o SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-28_

Os servidores de borda podem ser configurados para permitir que seus usuários internos e externos tenham acesso a contatos em organizações ou serviços de parceiros. As federações, pois esses contratos de parceiros são conhecidos, podem fornecer qualquer um dos itens a seguir ou todos eles para os contatos da sua organização na Federação de parceiros ou contatos na Federação de parceiros para o seu:

  - Mensagens instantâneas e presença

  - Colaboração e conferência, por exemplo: conferência via Web

  - Conferência de áudio, videoconferência ou ambos

Em alguns casos, a comunicação, por exemplo, mensagens instantâneas (IM) e presença entre um Microsoft Lync Server 2013 e um contato XMPP (Extensible Messaging and Presence Protocol), é somente ponto-a-ponto-dando suporte somente você e o contato no federado sócio. Em outros casos, como um Lync Server, Lync Server 2010 para Lync Server 2013 Federation, vários participantes podem ser convidados para ingressar na conversa.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Federação do Lync Server e do Office Communications Server

Federação entre o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server oferece suporte a comunicações ponto a ponto e de vários participantes. As conversas ponto a ponto podem ser escalonadas para conversas com vários participantes, permitindo reuniões ad hoc. Reuniões: Webconferência ou conferências de áudio/visuais – podem ser programadas para incluir contatos dentro da sua organização e contatos em parceiros com os quais você se federa.

A Federação apareceu primeiro no Microsoft Office Live Communications Server 2005 e com suporte um tipo de Federação, Federação direta. A Federação direta exigia que você saiba o domínio SIP (Session Initiation Protocol) do parceiro de Federação e o nome de domínio totalmente qualificado (FQDN) do servidor de borda do parceiro. O Live Communications Server 2005 com SP1 introduziu tipos de Federação adicionais, todos os registros SRV do sistema de nome de domínio (DNS) necessários a serem publicados pelo parceiro federado para localizar o servidor de borda. A terminologia do lançamento era:

  - *Abrir a Federação aprimorada*: aceitar qualquer nome de domínio SIP e usar o SRV DNS para localizar o servidor de borda de parceiro

  - *Federação aprimorada*: configurar o nome de domínio SIP do parceiro como um parceiro de Federação para a sua organização e usar o SRV DNS para localizar o servidor de borda de parceiro

  - *Federação direta*: configurar o nome de domínio SIP do parceiro e o FQDN para o servidor de borda do parceiro

  - *Lista de permissões do servidor*: aceitar qualquer domínio, usar o SRV DNS para localizar o servidor de borda de um provedor de hospedagem ou um provedor de conectividade de mensagens instantâneas (IM) público

O Microsoft Office Communications Server 2007 introduziu o nome atualizado dos tipos de Federação para definir melhor o que cada tipo de Federação realmente realizou:

  - A Federação aprimorada aberta se tornou conhecida como *domínio de parceiro descoberto*

  - A Federação aprimorada se tornou conhecida como *domínio de parceiro permitido*

  - A Federação direta se tornou conhecida como *servidor parceiro permitido*

  - A lista de permissões do servidor se tornou conhecida como *provedor de hospedagem* e provedor de mensagens de chat *públicas*

O Microsoft Lync Server 2010 introduziu uma definição mais estreita do provedor de Hospedagem de acordo com o Microsoft Lync Online 2010 e o Microsoft Office 365 e também o fez sujeito à mesma lista permitida definida pelo tipo de Federação do domínio parceiro permitido.

Habilitar a Federação entre o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server usa os servidores de borda e proxies reverso para impor as regras e os domínios de parceiros permitidos que você definir. De uma perspectiva de planejamento, a Federação com outro Lync Server, o Office Communications Server exige o seguinte:

  - Habilite a Federação no construtor de topologias. Para obter detalhes, consulte o tópico de implantação [Configurando a Federação do SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Determine suas necessidades para descoberta de domínio federado:
    
      - <span></span>  
        Para a configuração manual da Federação, você deve ter o nome de domínio totalmente qualificado (FQDN) do servidor de borda do parceiro e do nome do domínio, ou nome do domínio online, que é inserido no painel de controle do Lync Server, **agrupamento e acesso externo**, **domínios federados do SIP**. Crie uma **nova** política ou **edite** uma política existente para permitir ou bloquear domínios por FQDN.
        
        <div>
        

        > [!WARNING]
        > A configuração manual do servidor de borda do parceiro de Federação está sujeita a falhas caso o parceiro altere o endereço IP do servidor de borda.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Para <STRONG>novos domínios federados SIP</STRONG>, você deve fornecer o <STRONG>nome de domínio (ou FQDN)</STRONG> para o Microsoft Lync Online, Microsoft Office 365. Para o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server, você também deve fornecer um <STRONG>serviço de borda de acesso (FQDN)</STRONG>

        
        </div>
    
      - <span></span>  
        Para a Federação de parceiro descoberto, em que os parceiros podem descobrir seu servidor de borda, você cria um registro SRV \_em seu DNS-sipfederationtls externo. \_TCP.contoso.com – que aponta para a porta 5061 e para o registro do host (A) de seu servidor de borda
        
        <div>
        

        > [!IMPORTANT]
        > Se você estiver oferecendo suporte para clientes móveis do Microsoft Lync no Windows Phone ou no iPhone do Apple, no iPad ou em outros dispositivos Apple e estiver usando o serviço de notificação por Push ou o serviço de notificação por push, você deve planejar _sipfederationtls. _tcp. &lt;Registros SRV&gt; do domínio SIP para cada domínio SIP para os quais você tem clientes móveis do Lync. Android e Nokia Symbian Lync Mobile não use a notificação por push e não está sujeito a esse requisito.

        
        </div>

  - Configurar políticas de acesso de usuários externos para dar suporte a domínios federados

  - Abra portas de firewall para o protocolo SIP, conferência da Web e áudio/visual para acomodar a Federação ou os contatos que você está habilitando. Para obter detalhes, consulte: [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

As informações a seguir ajudarão você a definir os requisitos de certificado, de porta/protocolo e DNS para federação com o Microsoft Lync Server 2013 e o Lync Server 2010.

O planejamento de certificados, firewall e requisitos de porta/protocolo e requisitos de DNS geralmente é um processo direto se você planejou ou implantou seus servidores de borda do Microsoft Lync Server 2013. Como a Federação é um recurso adicional que usa o servidor de borda existente, os requisitos de planejamento geralmente são atendidos pelo planejamento e implantação do servidor de borda. Você deve usar as tabelas a seguir para determinar se os seus requisitos são atendidos e fazer alterações de acordo com a porta/protocolo e DNS.

<div>


> [!IMPORTANT]
> Se você tiver um pool de servidores de borda e estiver conferindo-se com os parceiros do Lync Server 2013 ou Lync Server 2010, poderá usar o balanceamento de carga DNS ou os balanceadores de carga de hardware nos lados internos e externos dos servidores de borda. Se você estiver fazendo a Federação com o Office Communications Server 2007 ou o Office Communications Server 2007 R2, o balanceamento de carga de hardware fornecerá suporte de failover em caso de um servidor de borda. O Office Communications Server 2007 e o Office Communications Server 2007 R2 não têm reconhecimento de balanceamento de carga de DNS. Os servidores de borda de parceiro estabelecerão comunicação com o primeiro servidor de borda no pool que responde. Se esse servidor de borda falhar, a comunicação não executará automaticamente o failover.



</div>

Os requisitos do certificado geralmente são atendidos pelo planejamento de certificados para o servidor de borda escolhido ou plano do servidor de borda em pool.

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>Conectividade de mensagens instantâneas públicas

A conectividade de mensagens instantâneas públicas é uma classe de Federação e está configurada para permitir que os usuários internos e externos do Lync Server 2013 adicionem contatos de qualquer um dos seguintes:

  - Contatos do Messenger

  - Instant\! contatos

  - Contatos do America Online (AOL)

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de desligamento do serviço (a data exata ainda precisa ser decidida, mas não mais cedo que 2013).</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário e por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo! Spam. O recurso da Microsoft para fornecer esse serviço tem o apoio acordado do Yahoo!, o contrato subjacente para o qual não será renovado.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de mensagens instantâneas e de voz.</P></LI></UL>



</div>

Essa classe de Federação requer as seguintes considerações de planejamento:

  - Os usuários do Windows Live Messenger podem ter áudio/comunicação visual ponto a ponto com usuários do Lync Server 2013, além de mensagens instantâneas. Seus servidores de borda devem atender a requisitos específicos de portabilidade e protocolo. Para obter detalhes, consulte [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - O Yahoo mensagens instantâneas não tem requisitos exclusivos, além daqueles geralmente usados no planejamento e na implantação do servidor de borda típico que está fornecendo a Federação.

  - O America Online requer que o certificado do servidor de borda atribuído ao serviço de borda de acesso tenha um uso avançado de chave (EKU) do cliente.

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>Federação de protocolo de presença e mensagens extensíveis (XMPP)

As versões anteriores do Lync Server e do Office Communications Server forneciam um gateway de protocolo de presença e mensagens (XMPP) extensível que poderia ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP. No Microsoft Lync Server 2013, a funcionalidade XMPP pode ser implantada como um recurso. A funcionalidade XMPP é instalada em duas partes: um proxy do XMPP que é executado no servidor de borda e o gateway de XMPP que é executado nos servidores front-end.

A implantação e a configuração do XMPP são abordadas na [implantação de acesso ao usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) você planeja oferecer suporte a XMPP em sua organização definindo regras de porta e protocolo em seu firewall, configuração de certificados e adição de registros DNS. Os tópicos a seguir nesta seção resumem as informações que você precisará para planejar com êxito a Federação do XMPP para sua implantação.

<div>


> [!IMPORTANT]
> O recurso XMPP do Lync Server 2013 é testado pela Microsoft e ela oferece suporte para federação de mensagens instantâneas com o Google Talk. Para quaisquer outros sistemas XMPP, entre em contato com o fornecedor do mesmo para verificar se eles suportam federação com o Lync Server 2013, e para quaisquer recomendações de implantação ou solução de problemas.



</div>

<div>


> [!IMPORTANT]
> Não há suporte para a Federação do XMPP para usuários que são hospedados em aparelhos de ramificação sobreviventes. Isso se aplica a ambos ver informações de presença e troca de mensagens INSTANTÂNEAs.



</div>

</div>

<div id="sectionSection3" class="section">

Nos tópicos a seguir, contenham orientação para definir certificados, portas de firewall e entradas de DNS para os tipos de cenários de Federação com suporte.

  - <span></span>  
    [Resumo do certificado-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Resumo da porta-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Resumo de DNS-SIP, Federação de XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar políticas para controlar acesso de usuário federado no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Cenários de acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar firewall A/V externo e requisitos de porta para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Determinar requisitios de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gerenciar configuração da borda de acesso para sua organização no Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Gerenciar domínios SIP federados para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gerenciar fornecedores SIP federados para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

