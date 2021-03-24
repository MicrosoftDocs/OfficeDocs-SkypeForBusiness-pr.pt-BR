---
title: Implantar vários sites no Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Saiba mais sobre como implantar vários sites PSTN no Cloud Connector Edition.
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098397"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Implantar vários sites no Cloud Connector

> [!Important] 
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

Saiba mais sobre como implantar vários sites PSTN no Cloud Connector Edition.
  
Esta seção descreve como implantar vários sites PSTN (Rede Telefônica Pública Comutado). Os sites são implantados um por vez usando as mesmas etapas da implantação de um único site. Este tópico descreve as considerações e as diferenças entre sites em uma implantação de vários sites. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Vários sites PSTN (Rede Telefônica Pública Comutado)

A seguir, mostra um exemplo de configuração para implantar o Skype for Business Cloud Connector Edition para diferentes sites PSTN. Certifique-se de que as configurações estão corretas antes de iniciar uma implantação.
  
PSTN Site 1
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

PSTN Site 2
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

Para cada site PSTN que você deseja adicionar, siga as etapas em [Implantar um único site no Cloud Connector](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> A pasta compartilhada para preparar alta disponibilidade (HA) é por site PSTN. A pasta compartilhada **deve** ser diferente entre sites PSTN. Não use a mesma pasta compartilhada para vários sites.> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Site único com alta disponibilidade (HA) em comparação com implantações de vários sites
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

A tabela a seguir lista as diferenças entre um único site com suporte a HA e uma implantação de vários sites.
  
|**Categoria**|**Item**|**Site único com HA**|**Multi-Site**|
|:-----|:-----|:-----|:-----|
|Configurar  <br/> |Nome do Host do Dispositivo <br/> |**Diferente** entre dispositivos <br/> |**Diferente** entre sites PSTN <br/> |
|Configurar  <br/> |Pasta compartilhada  <br/> |Requer a **mesma** pasta compartilhada entre dispositivos <br/> |Requer uma **pasta** compartilhada diferente entre dispositivos <br/> |
|Configurar  <br/> |VirtualMachineDomain  <br/> |Requer o **mesmo** domínio entre dispositivos <br/> |Requer o **mesmo** domínio em sites PSTN <br/> |
|Configurar  <br/> |SIPDomains  <br/> |Nomes de domínio e ordem devem ser os **mesmos em** todos os dispositivos <br/> |Nomes de domínio e ordem devem ser os **mesmos em** sites PSTN <br/> |
|Configurar  <br/> |Nome do site  <br/> |**Mesmo** Nome do Site entre dispositivos <br/> |**Diferente** Nome do Site em sites PSTN <br/> |
|Configurar  <br/> |Nomes de servidor  <br/> |**Diferente** entre dispositivos <br/> |**Diferente** entre sites PSTN <br/> |
|Configurar  <br/> |FQDNs de pool interno  <br/> |**O mesmo** em todos os dispositivos <br/> |**O mesmo** em sites PSTN <br/> |
|Configurar  <br/> |IPs internos  <br/> |**Diferente** entre dispositivos <br/> |**Diferente** entre sites PSTN <br/> |
|Configurar  <br/> |FQDN externo  <br/> |**O mesmo** em todos os dispositivos <br/> |**Diferente** entre sites PSTN <br/> |
|Configurar  <br/> |IPs externos  <br/> |**Diferente** entre dispositivos <br/> |**Diferente** entre sites PSTN <br/> |
|Configurar  <br/> |Configurações de GW PSTN  <br/> |**O mesmo** em todos os dispositivos <br/> |**Diferente** entre sites PSTN <br/> |
|Configurar  <br/> |Registro DNS  <br/> |Adicionar registros com os **mesmos** FQDNs de Acesso Externo e **endereços** IP diferentes <br/> |Adicionar registros  com FQDNs de Acesso Externo diferentes e **endereços** IP diferentes <br/> |
|Configurar  <br/> |Locatário híbrido  <br/> |Definir HybridPSTNSite  <br/> Definir PeerDestination para fallback  <br/> |Definir HybridPSTNSite  <br/> Definir PeerDestination para fallback  <br/> |
|Configurar  <br/> |Gateway  <br/> |Mapeamento MS GW **M:N** neste site <br/> |Os gateways PSTN em cada site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site  <br/> |
|Configurar  <br/> |User  <br/> |Definir UserPSTNSettings  <br/> |Definir UserPSTNSettings  <br/> |
