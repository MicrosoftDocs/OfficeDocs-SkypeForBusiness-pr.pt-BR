---
title: 'Lync Server 2013: gerenciar a configuração de borda de acesso para sua organização'
description: 'Lync Server 2013: gerenciar a configuração de borda de acesso para sua organização.'
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
ms.openlocfilehash: 2161385f9c03f025bcf6f5e599b7e0276f6d592c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550637"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Gerenciar a configuração de borda de acesso para sua organização no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Esta é uma documentação preliminar e está sujeita a alterações. Tópicos em branco são incluídos como espaços reservados.

Após a implantação de um ou mais servidores de borda, você deve habilitar os tipos de domínio externo ou acesso de provedor, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos servidores de borda que terão suporte para sua organização.

Essas opções incluem os seguintes tipos de acesso que podem ser configurados por meio da página **Configuração de Borda de Acesso**:

  - **Habilitar Federação e conectividade**     de im pública Habilite isso se você quiser dar suporte ao acesso de usuários a domínios de parceiros federados. Essa configuração se aplica à federação SIP e à federação XMPP configuradas para escopos global, site ou usuário na página **Política de Acesso Externo**. Para aplicar as configurações de federação, é necessário configurar o suporte à federação em ambas as páginas.
    
    Há duas configurações opcionais para o modo como os parceiros federados são descobertos, e se os avisos de isenção de arquivamento (notificação a contatos federados com os quais você se comunica de que sua implantação tem o arquivamento habilitado e de que os detalhes das comunicações serão arquivados) serão enviados aos contatos
    
      - **Habilitar descoberta**     de domínio de parceiro Selecionar essa opção permite a descoberta automática de domínios com os quais você pode federar. O Lync Server 2013 usa registros de sistema de nomes de domínio (DNS) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliar automaticamente o tráfego de entrada de parceiros federados descobertos e limitar ou bloquear esse tráfego com base no nível de confiança, na quantidade de tráfego e nas configurações de administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado. Para obter detalhes, consulte [Configurar suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Enviar isenção de responsabilidade de arquivamento para parceiros federados**     Selecionar essa opção permite o envio de uma mensagem de isenção de responsabilidade de arquivamento para parceiros federados que os aconselham que os detalhes de comunicação sejam registrados. Se você arquivar comunicações externas com domínios de parceiro federados, deverá habilitar a notificação de aviso de isenção de responsabilidade de arquivamento a fim de avisar os parceiros de que suas mensagens e comunicações estão sendo arquivadas por sua implantação. Para obter detalhes sobre arquivamento, consulte [definindo seus requisitos para arquivamento no Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Habilitar o acesso**     de usuário remoto Habilite essa opção se quiser que os usuários em sua organização que estejam fora do firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Lync Server. Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Permitir que usuários anônimos acessem conferências**     Habilite essa opção se quiser que os usuários internos convidem usuários anônimos externos para conferências que eles organizam. A habilitação dessa configuração permite apenas usuários anônimos para conferências. Para configurar a experiência de conferência e as opções que definirão como e o que os usuários podem fazer com conferências e para a inclusão de usuários anônimos, confira detalhes em [criar ou modificar a experiência do usuário de conferência para uma](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) referência de política de site ou de usuários e [conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> Além de permitir o suporte ao acesso de usuário externo, você também configura políticas para controlar o uso do acesso de usuário remoto em sua organização antes de qualquer tipo de acesso de usuário externo ficar disponível para os usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gerenciar política de acesso externo no Lync Server 2013</A>.



</div>

**Exibindo informações de configuração de borda de acesso usando cmdlets do Windows PowerShell**

  - As informações de configuração de borda de acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Para exibir informações sobre todas as suas definições de configuração de borda de acesso, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsAccessEdgeConfiguration
    
    Isto retorna informações semelhantes à seguinte:
    
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

  - [Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados no Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Habilitar ou desabilitar o acesso de usuário anônimo no Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Atribuir políticas de conferência para dar suporte a usuários anônimos no Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

