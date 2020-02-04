---
title: 'Lync Server 2013: Gerenciar configuração da borda de acesso para sua organização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4739599f92b9189a208e1bb320a53b82d66a3a9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Gerenciar configuração da borda de acesso para sua organização no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Esta documentação é preliminar e está sujeita a alterações. Os tópicos em branco são incluídos como espaços reservados.

Após implantar um ou mais servidores Edge, você deve habilitar os tipos de acesso de domínio externo ou de provedor, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos servidores de borda que terão suporte para sua organização.

Essas opções incluem os seguintes tipos de acesso que podem ser configurados por meio da página de **configuração de borda de acesso** :

  - **Habilite a Federação e a conectividade**   de mensagens de chat pública habilite isso se você quiser dar suporte ao acesso de usuários a domínios de parceiros federados. Essa configuração se aplica a agrupamentos SIP e a Federação XMPP configuradas para escopos global, de site ou de usuário na página **política de acesso externo** . Para que as configurações de Federação sejam aplicadas, você deve configurar o suporte de Federação em ambas as páginas.
    
    Há duas opções que são configurações opcionais sobre como os parceiros federados são descobertos e se o arquivamento de avisos de isenção de responsabilidade (notificação para contatos federados nos quais você se comunica com a sua implantação tem o arquivamento habilitado e se as comunicações os detalhes serão arquivados) serão enviados aos contatos
    
      - **Habilitar descoberta**   de domínio de parceiro selecionar essa opção permite a descoberta automática de domínios com os quais você pode federar. O Lync Server 2013 usa registros de sistema de nomes de domínio (DNS) para tentar descobrir domínios que não estão listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança. quantidade de tráfego e configurações do administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para os usuários nos domínios que você incluir na lista de domínios permitidos. Independentemente de você selecionar essa opção, você pode especificar que domínios individuais sejam bloqueados ou permitidos, incluindo a restrição de acesso a servidores específicos que executam o serviço de borda de acesso no domínio federado. Para obter detalhes, consulte [Configurar o suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Enviar isenção de isenção de responsabilidade para parceiros**   federados selecionar essa opção permite o envio de uma mensagem de isenção de isenção de responsabilidade para parceiros federados que os aconselha que os detalhes de comunicação sejam gravados. Se você arquivar comunicações externas com domínios de parceiros federados, habilite a notificação de isenção de isenção de responsabilidade para avisar os parceiros de que suas mensagens e os detalhes de comunicação estão sendo arquivados pela sua implantação. Para obter detalhes sobre o arquivamento, consulte [definindo seus requisitos para arquivamento no Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Habilitar o acesso**   de usuário remoto Habilite esta opção se você quiser que os usuários de sua organização que estão fora do seu firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Lync Server. Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Habilitar usuários anônimos para acessar conferências**   habilite essa opção se você quiser que os usuários internos convidem usuários anônimos externos para conferências que elas organizam. Habilitar essa configuração só permite usuários anônimos para conferências. Para configurar a experiência de conferência e as opções que definirão como e o que os usuários podem fazer com conferências e para a inclusão de usuários anônimos, consulte detalhes em [criar ou modificar a experiência do usuário de conferência para uma](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) referência de política de site ou usuários e [conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> Além de habilitar o suporte a acesso externo do usuário, você também pode configurar políticas para controlar o uso do acesso de usuários remotos em sua organização antes de qualquer tipo de acesso de usuário externo estar disponível para os usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso externo a usuários, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gerenciar a política de acesso externo no Lync Server 2013</A>.



</div>

**Exibindo informações de configuração de borda de acesso usando cmdlets do Windows PowerShell**

  - As informações de configuração de borda de acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.
    
    Para ver informações sobre todas as suas configurações de borda de acesso, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsAccessEdgeConfiguration
    
    Isso retornará informações parecidas com:
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Habilitar ou desabilitar descoberta de parceiros de federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados no Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Habilitar ou desabilitar acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Habilitar ou desabilitar acesso de usuário anônimo no Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Atribuir políticas de conferência para suporte de usuários anônimos no Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

