---
title: Gerenciar Configuração de Borda de Acesso para sua organização
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso de provedor ou domínio externo, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos Servidores de Borda que serão suportados para sua organização.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817331"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gerenciar Configuração de Borda de Acesso para sua organização

Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso de provedor ou domínio externo, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos Servidores de Borda que serão suportados para sua organização.

Essas opções incluem os seguintes tipos de acesso que podem ser configurados por meio da página **Configuração de Borda de Acesso**:

  - **Habilitar federação e conectividade pública de IM**   Habilita isso se quiser dar suporte ao acesso de usuário a domínios de parceiros federados. Esta configuração se aplica à federação SIP configurada para escopos globais, de site ou de usuário na **página Política de Acesso** Externo. Para aplicar as configurações de federação, é necessário configurar o suporte à federação em ambas as páginas.
    
    Existem duas opções que são configurações opcionais de como os parceiros federados são descobertos e se os avisos de isenção de responsabilidade de arquivamento (notificação a contatos federados que você comunica com que sua implantação está habilitada e que os detalhes das comunicações serão arquivados) serão enviados aos contatos:
    
      - **Habilitar a descoberta de domínio do parceiro**   Selecionar essa opção permite a descoberta automática de domínios com os qual você pode federar. O Skype for Business Server usa registros DNS (Sistema de Nomes de Domínio) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, quantidade de tráfego e configurações de administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado. Para obter detalhes, [consulte Configurar o suporte para domínios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)
    
      - **Enviar aviso de isenção de responsabilidade de arquivamento a parceiros federados**   Selecionar essa opção permite o envio de uma mensagem de aviso de isenção de responsabilidade de arquivamento para parceiros federados que os avisa de que os detalhes das comunicações são registrados. Se você arquivar comunicações externas com domínios de parceiro federados, deverá habilitar a notificação de aviso de isenção de responsabilidade de arquivamento a fim de avisar os parceiros de que suas mensagens e comunicações estão sendo arquivadas por sua implantação. Para obter detalhes sobre arquivamento, consulte Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento [para um parceiro federado.](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - **Habilitar acesso de usuário remoto**   Habilita essa opção se quiser que os usuários em sua organização que estão fora do firewall, como telecomutadores e usuários que estejam viajando, sejam capazes de se conectar ao Skype for Business Server. Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto.](enable-or-disable-remote-user-access.md)

  - **Permitir que usuários anônimos acessem conferências**   Habilita essa opção se quiser que os usuários internos convidem usuários anônimos externos para conferências organizadas por eles. A habilitação dessa configuração permite apenas usuários anônimos para conferências.

> [!NOTE]  
> Além de permitir o suporte ao acesso de usuário externo, você também configura políticas para controlar o uso do acesso de usuário remoto em sua organização antes de qualquer tipo de acesso de usuário externo ficar disponível para os usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte Gerenciar política de acesso [externo para sua organização.](../external-access-policies/manage-external-access-policy-for-your-organization.md)

**Exibindo informações de configuração de Borda de Acesso usando cmdlets do Windows PowerShell**

  - As informações de configuração da Borda de Acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration.** Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 
    
    Para exibir informações sobre todas as suas definições de configuração de Borda de Acesso, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
     `Get-CsAccessEdgeConfiguration`
    
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

