---
title: Gerenciar configuração da borda de acesso para sua organização
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de implantar um ou mais servidores de borda, você deverá habilitar os tipos de acesso do provedor ou domínio externo, acesso de usuário remoto e acesso de usuário anônimo para conferências por meio dos servidores de borda que serão suportados pela sua organização.
ms.openlocfilehash: 8428815a0f3d89124d1b5e681b79924171916f6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896914"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gerenciar configuração da borda de acesso para sua organização

Depois de implantar um ou mais servidores de borda, você deverá habilitar os tipos de acesso do provedor ou domínio externo, acesso de usuário remoto e acesso de usuário anônimo para conferências por meio dos servidores de borda que serão suportados pela sua organização.

Essas opções incluem os seguintes tipos de acesso que podem ser configurados através da página de **Configuração de borda de acesso** :

  - **Habilita a federação e conectividade de IM pública**   habilite isso se você deseja oferecer suporte ao acesso de usuário para domínios de parceiros federados. Essa configuração se aplica ao SIP federação configuradas para global, site ou escopos do usuário na página **Política de acesso externo** . Para aplicar as configurações de federação, você deve configurar o suporte de Federação em ambas as páginas.
    
    Existem duas opções que estão definições opcionais, como parceiros federados são descobertos e se o arquivamento de avisos de isenção (notificação para contatos federados que se comunica com que sua implantação tem arquivamento habilitado e que as comunicações detalhes serão arquivadas) serão enviadas aos contatos:
    
      - **Habilitar a descoberta de domínio de parceiro**   esta opção permite a descoberta automática de domínios que você pode federar. Skype para Business Server usa os registros de sistema de nome de domínio (DNS) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando o tráfego de entrada de parceiros federados descobertos automaticamente e limitando ou bloqueando esse tráfego com base em relação de confiança nível, a quantidade de tráfego e as configurações do administrador. Se você não selecionar essa opção, o acesso de usuário federado é habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Se ou não você seleciona essa opção, você pode especificar esse indivíduo domínios ser bloqueada ou permitida, incluindo restringir o acesso aos servidores específicos que executem o serviço de borda de acesso no domínio federado. Para obter detalhes, consulte [Configure suporte a domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Isenção de responsabilidade de arquivamento de envio para parceiros federados**   selecionar essa opção habilita o envio de uma mensagem de aviso de isenção de arquivamento para parceiros federados que avise-los a se os detalhes de comunicações são registradas. Se você arquivar comunicações externas com domínios de parceiro federado, você deve habilitar a notificação de isenção de responsabilidade de arquivamento avisar aos parceiros que seus detalhes de mensagens e comunicações estão sendo arquivadas pela sua implantação. Para obter detalhes sobre arquivamento, consulte [Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Habilitar o acesso de usuário remoto**   habilite essa opção se quiser que os usuários em sua organização que estão fora do firewall, como funcionários remotos e usuários que estiver viajando, possam se conectar ao Skype para Business Server. Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto](enable-or-disable-remote-user-access.md).

  - **Permitir que usuários anônimos acessem conferências**   habilite essa opção se quiser que os usuários internos convidem usuários anônimos externos para conferências que eles organizam. A habilitação dessa configuração só permite que usuários anônimos para conferências.

> [!NOTE]  
> Além de habilitar o acesso de usuário externo, suporte, você também configurar políticas para controlar o uso de acesso de usuário remoto em sua organização antes de qualquer tipo de acesso de usuário externo está disponível para usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas de acesso de usuário externo, consulte [Gerenciar a política de acesso externo para sua organização](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Exibindo informações de configuração de borda de acesso usando cmdlets do Windows PowerShell**

  - Informações de configuração de borda de acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration** . Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 
    
    Para exibir informações sobre todas as suas definições de configuração de borda de acesso, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
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

