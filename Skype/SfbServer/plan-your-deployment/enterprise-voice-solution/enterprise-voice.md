---
title: Planejar o Enterprise Voice no Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Enterprise Voice planejamento Noções básicas do Skype Business Server, incluindo sites, regiões, links de rede entre sites e estimar o tráfego de uso de voz.
ms.openlocfilehash: 3c5cad1b37b4f3bfe3fe73cad1d185b0116a68a0
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885334"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Planejar o Enterprise Voice no Skype for Business Server
 
Enterprise Voice planejamento Noções básicas do Skype Business Server, incluindo sites, regiões, links de rede entre sites e estimar o tráfego de uso de voz.
  
O processo de implantação do Enterprise Voice depende da sua topologia existente, infraestrutura e a funcionalidade do Enterprise Voice que você deseja suportar. Os procedimentos necessários dependem dos recursos que você escolher, mas há outras considerações de planejamento a fazer em um nível elevado.
  
Em geral, considere o tipo e o número de sites que você deseja implantar e suas localizações geográficas, o volume de chamadas em cada site, os tipos de links de rede que se conectam a sites, se você deseja fornecer redundância e failover para a funcionalidade de voz para cada um site, e se você deseja usar o equipamento de PBX existente. Há determinadas considerações, como alta disponibilidade, que você deve considerar ao planejar Skype para Business Server como um todo. Essas considerações são abordadas em tópicos ao longo desta seção, conforme necessário.
  
## <a name="sites-and-regions"></a>Locais e regiões

Primeiro, identifique os sites em sua topologia do qual você implantará o Enterprise Voice e as regiões de rede ao qual desses sites pertencem. Especificamente, considere como será fornecida a conectividade PSTN (rede telefônica pública comutada) a cada site. Para motivos de gerenciamento e logística, as regiões às quais esses sites pertencem podem ser um fator decisivo. Decida onde gateways serão implantados localmente, onde serão implantados aparelhos de filial persistente (SBAs) e onde você pode configurar troncos SIP (localmente ou no site central) para um provedor de serviço de telefonia da Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Links de rede entre locais

Você também precisa considerar o uso de largura de banda que você espera que nos links de rede entre o site central e seus sites de filial. Se você tiver ou planeja implantar, links de WAN resilientes entre sites, é recomendável que você implante um gateway em cada site de filial para fornecer a terminação de local DID (discagem direta) para usuários a US desses sites. Se você tiver links WAN resilientes, mas a largura de banda em um link WAN provavelmente for restrita, configure o controle de admissão de chamada para esse link. Se você não tiver vínculos de WAN resilientes, menos de 1.000 usuários no seu site de filial do host e não têm Skype treinado local para administradores do Business Server disponíveis, que recomendamos que você implante um aparelho de filial persistente no site da filial. Se você hospedar entre 1000 e 5000 usuários no seu site de filial, não têm uma conexão WAN resiliente e tendo treinado Skype para administradores do Business Server disponíveis, que recomendamos que você implante um servidor de filial persistente com um gateway pequeno, no site da filial. Considere também a habilitação de bypass de mídia em links restritos se você tiver um gateway par que suporte bypass de mídia.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimando uso e tráfego de voz

O Microsoft Lync Server 2013, ferramenta de planejamento usa a métrica a seguir para estimar o tráfego de usuário em cada local e o número de portas necessárias para dar suporte a esse tráfego.
  
> No caso de **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta.
    
> No caso de **Tráfego médio** (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta.
    
> No caso de **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta.
    
Por sua vez, o número de portas determina o número de servidores de mediação e gateways que serão necessários. Os gateways PSTN (rede) telefônica comutada pública que a maioria das organizações considera para implantação variam em tamanho de 2 portas a 960 portas. (Há gateways até maiores, mas esses são usados principalmente pelos provedores de serviços de telefonia).
  
Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Componentes, recursos e opções do Enterprise Voice

Consulte as seções a seguir para obter mais informações sobre como planejar a implantação do Enterprise Voice.
  
- [Componentes necessários para o Enterprise Voice no Skype para Business Server](components-required-for-enterprise-voice.md)
    
- [Planejar a conectividade PSTN em Skype para Business Server](pstn-connectivity-0.md)
    
- [Configurações de rede para os recursos avançados do Enterprise Voice no Skype para Business Server](network-settings-for-advanced-features.md)
    
- [Planejar o controle de admissão de chamada no Skype for Business Server](call-admission-control.md)
    
- [Planejamento de serviços de emergência no Skype para Business Server](emergency-services.md)
    
- [Planejar o bypass de mídia no Skype para negócios](media-bypass.md)
    
- [Plano para linhas telefônicas privadas com Skype para negócios](private-telephone-lines.md)
    
- [Plano para roteamento baseado em local no Skype para negócios](location-based-routing.md)
    
- [Planejar recursos de gerenciamento de chamada do Skype para negócios](call-management-features.md)
    
- [Planejamento de resiliência do Enterprise Voice em Skype para Business Server](enterprise-voice-resiliency.md)
    

