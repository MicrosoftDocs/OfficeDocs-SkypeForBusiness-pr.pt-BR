---
title: Planejamento para SIP, Federação XMPP e mensagens instantâneas públicas
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
ms.openlocfilehash: c1e31e9fd0de6135dd1fd3f552d0d692f1bf7543
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Planejamento para SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-28_

Os servidores de borda podem ser configurados para permitir que os usuários internos e externos acessem contatos em organizações ou serviços de parceiros. As federações, pois esses contratos de parceiros são conhecidos, podem fornecer qualquer um ou todos os seguintes itens para os contatos em sua organização na Federação de parceiros ou contatos na Federação de parceiro para o seu:

  - Sistema de mensagens instantâneas e presença

  - Colaboração e conferência, por exemplo – Webconferência

  - Audioconferência, conferência de vídeo ou ambos

Em alguns casos, a comunicação, por exemplo, mensagens instantâneas (IM) e presença entre o Microsoft Lync Server 2013 e um contato XMPP (Extensible Messaging and Presence Protocol), é ponto-a-ponto apenas que suporta apenas você e o contato no federado parceira. Em outros casos, como um Lync Server, Lync Server 2010 para a Federação do Lync Server 2013, vários participantes podem ser convidados para entrar na conversa.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Federação do Lync Server e Office Communications Server

Federação entre o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server suporta comunicação ponto a ponto e vários participantes. As conversas ponto a ponto podem ser posicionadas para conversas de várias partes, permitindo reuniões locais. Reuniões - Conferência da Web ou conferências áudio/visual - podem ser programadas para incluir contatos dentro da sua organização, assim como contatos em parceiros que você federar.

A Federação apareceu primeiro no Microsoft Office Live Communications Server 2005 e suportava um tipo de Federação, Federação direta. A Federação direta exigia que você saiba o domínio SIP (Session Initiation Protocol) do parceiro de Federação e o FQDN (nome de domínio totalmente qualificado) do servidor de borda do parceiro. O Live Communications Server 2005 com SP1 apresentou tipos de Federação adicionais, todos os quais os registros SRV do sistema de nomes de domínio (DNS) necessários serão publicados pelo parceiro federado para localizar seu servidor de borda. A terminologia para esta versão foi:

  - *Abrir Federação aprimorada*: aceitar qualquer nome de domínio SIP e usar SRV DNS para localizar o servidor de borda de parceiro

  - *Federação avançada*: Configure o nome de domínio SIP do parceiro como um parceiro de Federação para sua organização e use DNS SRV para localizar o servidor de borda de parceiro

  - *Federação direta*: Configure o nome de domínio SIP do parceiro e o FQDN para o servidor de borda do parceiro

  - *Lista de permissões de servidor*: aceitar qualquer domínio, usar SRV DNS para localizar o servidor de borda de um provedor de hospedagem ou um provedor de conectividade de mensagens instantâneas (IM) público

O Microsoft Office Communications Server 2007 introduziu a nomenclatura atualizada para tipos de Federação para definir melhor o que cada tipo de Federação realmente realizou:

  - A Federação Avançada Aberta se tornou *Domínio de Parceiro Descoberto*

  - A Federação Avançada se tornou *Domínio de Parceiro Permitido*

  - A Federação Direta se tornou *Servidor de Parceiro Permitido*

  - A Lista de Permissão do Servidor se tornou *Provedor de Hospedagem* e *Provedor IM Público*

O Microsoft Lync Server 2010 introduziu uma definição mais estreita de provedor de Hospedagem de acordo com o Microsoft Lync Online 2010 e com o Microsoft Office 365 e também o fez sujeito à mesma lista permitida definida pelo tipo de Federação de domínio de parceiro permitido.

Habilitar a Federação entre o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server usa os servidores de borda e os proxies reverso para impor as regras e domínios de parceiros permitidos que você definir. De uma perspectiva de planejamento, a Federação com outro Lync Server, o Office Communications Server requer o seguinte:

  - Habilitar federação no Construtor de Topologia. Para obter detalhes, consulte o tópico de implantação [Configurando a Federação SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Determine seus requisitos para descoberta do domínio federado:
    
      - <span></span>  
        Para a configuração manual da Federação, você deve ter o FQDN (nome de domínio totalmente qualificado) do servidor de borda e do nome de domínio do parceiro, ou nome de domínio online, que é inserido no painel de controle do Lync Server, **Federação e acesso externo**, **domínios federados SIP**. Crie uma política **Novo** ou **Edite** uma política existente para permitir ou bloquear domínios pelo FQDN.
        
        <div>
        

        > [!WARNING]
        > A configuração manual do servidor de borda de um parceiro de Federação está sujeita a falhas caso o parceiro altere o endereço IP de seu servidor de borda.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Para <STRONG>novos domínios federados SIP</STRONG>, você deve fornecer o <STRONG>nome de domínio (ou FQDN)</STRONG> para o Microsoft Lync Online, Microsoft Office 365. Para o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server, você também deve fornecer um <STRONG>serviço de borda de acesso (FQDN)</STRONG>

        
        </div>
    
      - <span></span>  
        Para Federação de parceiro descoberta, onde os parceiros podem descobrir seu servidor de borda, você cria um registro SRV em seu \_DNS-sipfederationtls externo. \_TCP.contoso.com – que aponta para a porta 5061 e o registro de host (A) do servidor de borda
        
        <div>
        

        > [!IMPORTANT]
        > Se você estiver oferecendo suporte aos clientes do Microsoft Lync Mobile no Windows Phone ou no iPhone, iPad ou em outros dispositivos Apple e estiver usando o serviço de notificação por Push ou o serviço de notificação por push, você deve planejar _sipfederationtls. _tcp. &lt;Registros SRV&gt; de domínio SIP para cada domínio SIP que você tenha clientes móveis do Lync. Android e Nokia Symbian Lync Mobile não usam a notificação por push e não estão sujeitos a esse requisito.

        
        </div>

  - Configure políticas de acesso do usuário externo para suportar domínios federados

  - Abra portas de firewall para SIP, conferência da Web e áudio/visual para acomodar a federação ou contatos que estiver habilitando. Para obter detalhes, consulte: [determinar firewall A/V externo e requisitos de porta para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

As informações a seguir ajudarão você a definir os requisitos de certificado, de porta/protocolo e DNS para federação com o Microsoft Lync Server 2013 e o Lync Server 2010.

O planejamento de certificados, firewall e requisitos de porta/protocolo e DNS é geralmente um processo de avanço direto se você tiver planejado ou implantado seus servidores de borda do Microsoft Lync Server 2013. Como a Federação é um recurso adicional que usa o servidor de borda existente, os requisitos de planejamento geralmente são atendidos pelo planejamento e implantação do servidor de borda. Você deve usar as seguintes tabelas para determinar quais de seus requisitos são atendidos e faz mudanças na porta/protocolo e DNS da mesma forma.

<div>


> [!IMPORTANT]
> Se você tiver um pool de servidores de borda e estiver se Federando com parceiros do Lync Server 2013 ou do Lync Server 2010, poderá usar balanceamento de carga DNS ou balanceadores de carga de hardware nos lados internos e externos voltados para os servidores de borda. Se você estiver se Federando com o Office Communications Server 2007 ou o Office Communications Server 2007 R2, o balanceamento de carga de hardware fornecerá suporte de failover no caso de um servidor de borda. O Office Communications Server 2007 e o Office Communications Server 2007 R2 não têm reconhecimento de balanceamento de carga de DNS. Os servidores de borda de parceiro estabelecerão a comunicação com o primeiro servidor de borda no pool que responder. Se esse servidor de borda falhar, a comunicação não executará automaticamente o failover.



</div>

Os requisitos de certificado normalmente são atendidos pelo planejamento de certificados para o servidor de borda escolhido ou para o plano do servidor de borda em pool.

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>Conectividade de mensagens instantâneas públicas

A conectividade de mensagens instantâneas públicas é uma classe de Federação e é configurada para permitir que seus usuários internos e externos do Lync Server 2013 adicionem contatos de qualquer um dos seguintes:

  - Contatos do Messenger

  - Instant\! contacts

  - Contatos do America Online (AOL)

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de desligamento do serviço (a data exata ainda deve ser decidida, mas não antes de junho de 2013).</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário, por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual não será renovado.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de IM e voz.</P></LI></UL>



</div>

Essa classe de Federação requer as seguintes considerações de planejamento:

  - Os usuários do Windows Live Messenger podem ter a comunicação de áudio/vídeo ponto a ponto com os usuários do Lync Server 2013, além de mensagens instantâneas. Os servidores de borda devem atender a requisitos específicos de porta e protocolo. Para obter detalhes, consulte [determine external A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - O Yahoo mensagens instantâneas não tem requisitos exclusivos, além daqueles normalmente usados no planejamento e implantação do servidor de borda típico que está fornecendo Federação.

  - O America Online requer que o certificado do servidor de borda atribuído ao serviço de borda de acesso tenha um cliente de uso avançado de chave (EKU).

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>Federação do protocolo XMPP (Extensible Messaging and Presence Protocol)

Versões anteriores do Lync Server e Office Communications Server forneciam um Gateway XMPP (Extensible Messaging and Presence Protocol) que pode ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP. No Microsoft Lync Server 2013, a funcionalidade do XMPP pode ser implantada como um recurso. A funcionalidade do XMPP está instalada em duas partes: um proxy do XMPP que é executado no servidor de borda e o gateway do XMPP que é executado nos servidores front-end.

A implantação e a configuração do XMPP são abordadas na [implantação de acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) você planeja oferecer suporte a XMPP em sua organização definindo regras de porta e protocolo no firewall, configuração de certificados e adição de registros DNS. Os seguintes tópicos nesta seção resumem as informações que você precisará para planejar com êxito a Federação do XMPP para sua implantação.

<div>


> [!IMPORTANT]
> O recurso XMPP do Lync Server 2013 é testado e suportado pela Microsoft para Federação de mensagens instantâneas com o Google Talk. Para qualquer outro sistema XMPP, entre em contato com o fornecedor terceirizado para verificar se eles suportam a Federação com o Lync Server 2013 e para qualquer recomendação de implantação ou solução de problemas.



</div>

<div>


> [!IMPORTANT]
> A Federação XMPP não é suportada para usuários hospedados em aparelhos de filial persistente. Isso se aplica a informações de presença e troca de mensagens de IM.



</div>

</div>

<div id="sectionSection3" class="section">

Nos tópicos a seguir contêm orientações para definir certificados, portas de firewall e entradas de DNS para os tipos de cenários de Federação com suporte.

  - <span></span>  
    [Resumo de certificado-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Resumo de DNS-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gerenciar a configuração de borda de acesso para sua organização no Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Gerenciar domínios federados SIP para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gerenciar provedores federados SIP para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

