---
title: Planejando a Federação do Lync Server e do Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c683092b61d278d380ad68cef86795d496498fbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Planejando a Federação do Lync Server 2013 e do Office Communications Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-13_

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

  - Habilite a Federação no construtor de topologias. Para obter detalhes, consulte o tópico de implantação Configurando a [Federação do SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Determine suas necessidades para descoberta de domínio federado:
    
      - <span></span>  
        Para a configuração manual da Federação, você deve ter o nome de domínio totalmente qualificado (FQDN) do servidor de borda do parceiro e do nome do domínio, ou nome do domínio online, que é inserido no painel de controle do Lync Server, **agrupamento e acesso externo**, **SIP Domínios federados**. Crie uma **nova** política ou **edite** uma política existente para permitir ou bloquear domínios por FQDN.
        
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
        > Se você estiver oferecendo suporte para clientes móveis do Microsoft Lync no Windows Phone ou no iPhone do Apple, no iPad ou em outros dispositivos Apple e estiver usando o serviço de notificação por Push ou o serviço de notificação por push, você deve planejar o sipfederationtls. _ TCP. &lt;Registros SRV&gt; do domínio SIP para cada domínio SIP para os quais você tem clientes móveis do Lync. Android e Nokia Symbian Lync Mobile não use a notificação por push e não está sujeito a esse requisito.

        
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

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo do certificado-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Resumo da porta-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Resumo de DNS-SIP, Federação de XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

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

