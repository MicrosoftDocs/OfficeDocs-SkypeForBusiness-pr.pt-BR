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
description: Saiba como implantar vários sites PSTN no Cloud Connector Edition.
ms.openlocfilehash: 98890bb3ffe53497c5e915acba5c073c4316f3b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799691"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Implantar vários sites no Cloud Connector
 
Saiba como implantar vários sites PSTN no Cloud Connector Edition.
  
Esta seção descreve como implantar vários sites PSTN (Rede Telefônica Pública Comutada). Os sites são implantados um de cada vez, usando o procedimento de implantação de um único site. Este tópico apresenta considerações e as diferenças entre os sites em uma implantação de vários sites.  
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Vários sites PSTN

Veja a seguir um exemplo de configuração para implantar o Skype for Business Cloud Connector Edition para sites PSTN diferentes. Antes de iniciar a implantação, verifique se a configuração está definida corretamente.
  
Site PSTN 1
  
```
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

Site PSTN 2
  
```
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

Para cada site PSTN que você deseja adicionar, siga as etapas em [implantar um único site no conector de nuvem](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> A pasta compartilhada para a preparação de alta disponibilidade refere-se a cada site PSTN. As pastas compartilhadas dos sites PSTN **devem** ser diferentes. Não use a mesma pasta compartilhada para vários sites. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Site único com alta disponibilidade comparado a implantações de vários sites
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

A tabela a seguir lista as diferenças entre a implantação de um único site com suporte para alta disponibilidade e a implantação de vários sites.
  
|**Categoria**|**Item**|**Único site com alta disponibilidade**|**Vários sites**|
|:-----|:-----|:-----|:-----|
|Configuração  <br/> |Nome do host do aplicativo <br/> |**Diferentes** nos vários dispositivos <br/> |**Diferente** nos vários sites PSTN <br/> |
|Instalação  <br/> |Pasta compartilhada  <br/> |Requer a **mesma** pasta compartilhada em todos os aparelhos <br/> |Requer uma pasta compartilhada **diferente** nos vários dispositivos <br/> |
|Configuração  <br/> |VirtualMachineDomain  <br/> |Requer o **mesmo** domínio nos vários dispositivos <br/> |Requer o **mesmo** domínio nos vários sites PSTN <br/> |
|Configuração  <br/> |SIPDomains  <br/> |Os nomes de domínio e a ordem devem ser **iguais** em todos os aparelhos <br/> |Os nomes de domínio e a ordem devem ser **iguais** em sites PSTN <br/> |
|Configuração  <br/> |Nome do site  <br/> |Nome do Site **igual** nos vários dispositivos <br/> |Nome do Site **diferente** nos vários sites PSTN <br/> |
|Configuração  <br/> |Nomes de servidor  <br/> |**Diferentes** nos vários dispositivos <br/> |**Diferente** nos vários sites PSTN <br/> |
|Configuração  <br/> |FQDNs de pool interno  <br/> |**Iguais** nos vários dispositivos <br/> |**Igual** nos vários sites PSTN <br/> |
|Configuração  <br/> |IPs internos  <br/> |**Diferentes** nos vários dispositivos <br/> |**Diferente** nos vários sites PSTN <br/> |
|Configuração  <br/> |FQDN externo  <br/> |**Iguais** nos vários dispositivos <br/> |**Diferente** nos vários sites PSTN <br/> |
|Configuração  <br/> |IPs externos  <br/> |**Diferentes** nos vários dispositivos <br/> |**Diferente** nos vários sites PSTN <br/> |
|Configuração  <br/> |Configurações de Gateway PSTN  <br/> |**Iguais** nos vários dispositivos <br/> |**Diferente** nos vários sites PSTN <br/> |
|Configuração  <br/> |Registro DNS  <br/> |Adicionar registros com os **mesmos** FQDNs externos de acesso externo e endereços IP **diferentes** <br/> |Adicionar registros com FQDNs de Acesso Externo **diferentes** e endereços IP **diferentes** <br/> |
|Instalação  <br/> |Locatário híbrido  <br/> |Definir HybridPstnSite  <br/> Definir PeerDestination para fallback  <br/> |Definir HybridPstnSite  <br/> Definir PeerDestination para fallback  <br/> |
|Instalação  <br/> |Gateway  <br/> |Mapeamento de **M:N** do MS GW neste site <br/> |Os gateways PSTN em cada site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site  <br/> |
|Instalação  <br/> |Usuário  <br/> |Definir UserPSTNSettings  <br/> |Definir UserPSTNSettings  <br/> |
   

