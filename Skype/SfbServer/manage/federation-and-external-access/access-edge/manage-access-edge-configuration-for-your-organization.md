---
title: Gerenciar Configuração de Borda de Acesso para sua organização
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso de domínio externo ou provedor, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos Servidores de Borda que serão suportados para sua organização.
ms.openlocfilehash: ff152ea25bbea750815e0619ce521ede8d8d7203
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860088"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gerenciar Configuração de Borda de Acesso para sua organização

Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso de domínio externo ou provedor, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos Servidores de Borda que serão suportados para sua organização.

Essas opções incluem os seguintes tipos de acesso que podem ser configurados por meio da página **Configuração de Borda de Acesso**:

  - **Habilitar a conectividade de IM pública e federação**   Habilita isso se quiser dar suporte ao acesso do usuário a domínios de parceiros federados. Essa configuração se aplica à federação SIP configurada para escopos globais, de site ou de usuário na página **Política de Acesso** Externo. Para aplicar as configurações de federação, é necessário configurar o suporte à federação em ambas as páginas.
    
    Existem duas opções que são configurações opcionais de como os parceiros federados são descobertos e se os avisos de isenção de responsabilidade de arquivamento (notificação a contatos federados que você se comunica com que sua implantação está habilitada para arquivamento e que os detalhes das comunicações serão arquivados) serão enviados para contatos:
    
      - **Habilitar a descoberta de domínio do parceiro**   Selecionar essa opção permite a descoberta automática de domínios com os qual você pode federar. Skype for Business Server usa registros DNS (Sistema de Nomes de Domínio) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, na quantidade de tráfego e nas configurações do administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado. Para obter detalhes, [consulte Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Enviar aviso de isenção de responsabilidade de arquivamento para parceiros federados**   Selecionar essa opção permite o envio de uma mensagem de aviso de isenção de responsabilidade de arquivamento para parceiros federados que os aconselha a registrar detalhes de comunicações. Se você arquivar comunicações externas com domínios de parceiro federados, deverá habilitar a notificação de aviso de isenção de responsabilidade de arquivamento a fim de avisar os parceiros de que suas mensagens e comunicações estão sendo arquivadas por sua implantação. Para obter detalhes sobre arquivamento, consulte [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Habilitar o acesso de usuário remoto**   Habilita essa opção se você quiser que os usuários em sua organização que estejam fora do firewall, como os operadores de telecomunicações e os usuários que estão viajando, sejam capazes de se conectar ao Skype for Business Server. Para obter detalhes, consulte [Enable or disable remote user access](enable-or-disable-remote-user-access.md).

  - **Habilitar usuários anônimos para acessar conferências**   Habilita essa opção se quiser que os usuários internos convidem usuários anônimos externos para conferências que eles organizam. A habilitação dessa configuração permite apenas usuários anônimos para conferências.

> [!NOTE]  
> Além de permitir o suporte ao acesso de usuário externo, você também configura políticas para controlar o uso do acesso de usuário remoto em sua organização antes de qualquer tipo de acesso de usuário externo ficar disponível para os usuários. Para obter detalhes sobre a criação, configuração e aplicação de políticas para acesso de usuário externo, consulte Gerenciar política de acesso externo [para sua organização.](../external-access-policies/manage-external-access-policy-for-your-organization.md)

**Exibindo informações de configuração de Borda de Acesso usando Windows PowerShell cmdlets**

  - As informações de configuração de Borda de Acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration.** Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 
    
    Para exibir informações sobre todas as configurações de Borda de Acesso, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:
    
     `Get-CsAccessEdgeConfiguration`
    
    Isto retorna informações semelhantes à seguinte:
    
    Identidade : Global<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers : False<br/>
    AllowOutsideUsers : True<br/>
    BeClearingHouse : False<br/>
    EnablePartnerDiscovery : False<br/>
    EnableArchivingDisclaimer : False<br/>
    EnableUserReplicator : True<br/>
    KeepCrlsUpToDateForPeers : True<br/>
    MarkSourceVerifiableOnOutgoingMessages : True<br/>
    OutgoingTlsCountForFederatedPartners : 4<br/>
    DiscoveredPartnerStandardRate : 20<br/>
    EnableDiscoveredPartnerContactsLimit : True<br/>
    MaxContactsPerDiscoveredPartner : 1000<br/>
    DiscoveredPartnerReportPeriodMinutes : 60<br/>
    MaxAcceptedCertificatesStored : 1000<br/>
    MaxRejectedCertificatesStored : 500<br/>
    CertificatesDeletedPercentage : 20<br/>
    RoutingMethod : UseDnsSrvRouting<br/>

