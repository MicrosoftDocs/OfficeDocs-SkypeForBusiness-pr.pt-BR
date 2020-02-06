---
title: Gerenciar configuração da borda de acesso para sua organização
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Após implantar um ou mais servidores Edge, você deve habilitar os tipos de acesso de domínio externo ou de provedor, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos servidores de borda que terão suporte para sua organização.
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818342"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gerenciar configuração da borda de acesso para sua organização

Após implantar um ou mais servidores Edge, você deve habilitar os tipos de acesso de domínio externo ou de provedor, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos servidores de borda que terão suporte para sua organização.

Essas opções incluem os seguintes tipos de acesso que podem ser configurados por meio da página de **configuração de borda de acesso** :

  - **Habilite a Federação e a conectividade**   de mensagens de chat pública habilite isso se você quiser dar suporte ao acesso de usuários a domínios de parceiros federados. Essa configuração se aplica à Federação SIP configurada para escopos global, de site ou de usuário na página **política de acesso externo** . Para que as configurações de Federação sejam aplicadas, você deve configurar o suporte de Federação em ambas as páginas.
    
    Há duas opções que são configurações opcionais sobre como os parceiros federados são descobertos e se o arquivamento de avisos de isenção de responsabilidade (notificação para contatos federados nos quais você se comunica com a sua implantação tem o arquivamento habilitado e se as comunicações os detalhes serão arquivados) serão enviados aos contatos:
    
      - **Habilitar descoberta**   de domínio de parceiro selecionar essa opção permite a descoberta automática de domínios com os quais você pode federar. O Skype for Business Server usa registros de sistema de nome de domínio (DNS) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base na confiança nível, quantidade de tráfego e configurações do administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para os usuários nos domínios que você incluir na lista de domínios permitidos. Independentemente de você selecionar essa opção, você pode especificar que domínios individuais sejam bloqueados ou permitidos, incluindo a restrição de acesso a servidores específicos que executam o serviço de borda de acesso no domínio federado. Para obter detalhes, consulte [Configurar o suporte para domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Enviar isenção de isenção de responsabilidade para parceiros**   federados selecionar essa opção permite o envio de uma mensagem de isenção de isenção de responsabilidade para parceiros federados que os aconselha que os detalhes de comunicação sejam gravados. Se você arquivar comunicações externas com domínios de parceiros federados, habilite a notificação de isenção de isenção de responsabilidade para avisar os parceiros de que suas mensagens e os detalhes de comunicação estão sendo arquivados pela sua implantação. Para obter detalhes sobre o arquivamento, consulte [habilitar ou desabilitar o envio de uma isenção de arquivamento para parceiro federado](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Habilitar o acesso**   de usuário remoto Habilite esta opção se você quiser que os usuários de sua organização que estão fora do seu firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Skype for Business Server. Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuários remotos](enable-or-disable-remote-user-access.md).

  - **Habilitar usuários anônimos para acessar conferências**   habilite essa opção se você quiser que os usuários internos convidem usuários anônimos externos para conferências que elas organizam. Habilitar essa configuração só permite usuários anônimos para conferências.

> [!NOTE]  
> Além de habilitar o suporte a acesso externo do usuário, você também pode configurar políticas para controlar o uso do acesso de usuários remotos em sua organização antes de qualquer tipo de acesso de usuário externo estar disponível para os usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso externo a usuários, consulte [gerenciar a política de acesso externo para sua organização](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Exibindo informações de configuração de borda de acesso usando cmdlets do Windows PowerShell**

  - As informações de configuração de borda de acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration** . Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 
    
    Para ver informações sobre todas as suas configurações de borda de acesso, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
     `Get-CsAccessEdgeConfiguration`
    
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

