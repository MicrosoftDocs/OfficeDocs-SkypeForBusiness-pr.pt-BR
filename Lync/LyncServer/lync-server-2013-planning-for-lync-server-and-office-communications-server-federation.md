---
title: Planejamento para Federação do Lync Server e Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 838664dbbc34182d1c1eb5ec48f523480a891379
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Planejamento para Federação do Lync Server 2013 e Office Communications Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-13_

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

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo de certificado-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Resumo de DNS-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

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

