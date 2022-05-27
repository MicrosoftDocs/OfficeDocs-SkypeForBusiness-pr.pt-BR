---
title: Gerenciar Configuração de Borda de Acesso para sua organização
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso de domínio ou provedor externo, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos Servidores de Borda que terão suporte para sua organização.
ms.openlocfilehash: 228d3c2975d403422795244dafebc0138e385d89
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674593"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gerenciar Configuração de Borda de Acesso para sua organização

Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso de domínio ou provedor externo, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos Servidores de Borda que terão suporte para sua organização.

Essas opções incluem os seguintes tipos de acesso que podem ser configurados por meio da página **Configuração de Borda de Acesso**:

  - **Habilitar a federação e a conectividade de mensagens instantâneas públicas**   Habilite isso se você quiser dar suporte ao acesso do usuário a domínios de parceiros federados. Essa configuração se aplica à federação SIP configurada para escopos globais, de site ou de usuário na **página Política de Acesso** Externo. Para aplicar as configurações de federação, é necessário configurar o suporte à federação em ambas as páginas.
    
    Existem duas opções que são configurações opcionais de como os parceiros federados são descobertos e se os avisos de isenção de responsabilidade de arquivamento (notificação a contatos federados que você se comunica com o qual sua implantação tem o arquivamento habilitado e se os detalhes das comunicações serão arquivados) serão enviados aos contatos:
    
      - **Habilitar a descoberta de domínio de parceiro**   Selecionar essa opção permite a descoberta automática de domínios com os qual você pode federar. Skype for Business Server usa registros DNS (Sistema de Nomes de Domínio) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, na quantidade de tráfego e nas configurações de administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado. Para obter detalhes, consulte [Configurar o suporte para domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Enviar aviso de isenção de responsabilidade de arquivamento a parceiros federados**   Selecionar essa opção permite o envio de uma mensagem de isenção de responsabilidade de arquivamento a parceiros federados que os aconselham a registrar detalhes de comunicações. Se você arquivar comunicações externas com domínios de parceiro federados, deverá habilitar a notificação de aviso de isenção de responsabilidade de arquivamento a fim de avisar os parceiros de que suas mensagens e comunicações estão sendo arquivadas por sua implantação. Para obter detalhes sobre arquivamento, consulte Habilitar ou desabilitar o envio de um aviso de [isenção de responsabilidade de Arquivamento para um parceiro federado](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Habilitar o acesso de usuário remoto**   Habilite essa opção se quiser que os usuários em sua organização que estão fora do firewall, como os operadores de telecomunicações e os usuários que estão viajando, possam se conectar ao Skype for Business Server. Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto](enable-or-disable-remote-user-access.md).

  - **Habilitar usuários anônimos para acessar conferências**   Habilite essa opção se quiser que os usuários internos convidem usuários anônimos externos para conferências que eles organizam. A habilitação dessa configuração permite apenas usuários anônimos para conferências.

> [!NOTE]  
> Além de permitir o suporte ao acesso de usuário externo, você também configura políticas para controlar o uso do acesso de usuário remoto em sua organização antes de qualquer tipo de acesso de usuário externo ficar disponível para os usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte [Gerenciar política de acesso externo para sua organização](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Exibindo informações de configuração do Access Edge usando Windows PowerShell cmdlets**

  - As informações de configuração do Access Edge podem ser exibidas usando Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration**. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 
    
    Para exibir informações sobre todas as suas definições de configuração do Access Edge, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
     `Get-CsAccessEdgeConfiguration`
    
    Isto retorna informações semelhantes à seguinte:
    
    Identidade: global<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers : False<br/>
    AllowOutsideUsers: True<br/>
    BeClearingHouse : False<br/>
    EnablePartnerDiscovery: False<br/>
    EnableArchivingDisclaimer: False<br/>
    EnableUserReplicator: True<br/>
    KeepCrlsUpToDateForPeers: True<br/>
    MarkSourceVerifiableOnOutgoingMessages: True<br/>
    OutgoingTlsCountForFederatedPartners : 4<br/>
    DiscoveredPartnerStandardRate : 20<br/>
    EnableDiscoveredPartnerContactsLimit: True<br/>
    MaxContactsPerDiscoveredPartner: 1000<br/>
    DiscoveredPartnerReportPeriodMinutes : 60<br/>
    MaxAcceptedCertificatesStored: 1000<br/>
    MaxRejectedCertificatesStored: 500<br/>
    CertificatesDeletedPercentage: 20<br/>
    RoutingMethod : UseDnsSrvRouting<br/>

