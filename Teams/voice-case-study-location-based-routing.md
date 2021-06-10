---
title: Teams de caso contoso de voz
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams de caso de voz para corporação multi-nacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785938"
---
# <a name="contoso-case-study-location-based-routing"></a>Estudo de caso contoso: Location-Based routing

Location-Based routing (LBR) é um recurso que restringe o desvio de chamada com base na política e na localização física do usuário no momento da colocação ou recebimento de uma chamada.  

## <a name="overview"></a>Visão Geral

A Contoso tem dois escritórios em um país onde é ilegal ignorar o provedor PSTN (Rede Telefônica Pública Comutado) para diminuir os custos de chamadas de longa distância. O escritório principal tem uma conexão com a Internet usada pelo escritório principal e pelo segundo escritório. Cada escritório tem seu próprio Controlador de Borda de Sessão (SBC) conectado a uma operadora PSTN.  
 
Neste país, a Contoso tinha a LBR configurada para sua implantação Skype for Business de terceiros. Para determinar como configurar a LBR para Teams, a Contoso leu [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md). A Contoso determinou que Teams e Skype for Business seguem os mesmos cenários em que uma chamada pode ser feita, quando ela pode ser recebida, quando uma chamada PSTN pode ser transferida para um usuário Teams e quando você pode transferir outro usuário Teams para a chamada PSTN.  

Para Skype for Business, a LBR foi configurada com o Tronco SIP do Controlador de Borda de Sessão (SBC) conectando-se à operadora PSTN. Para esse SBC, a Contoso analisou a lista de [SBCs](direct-routing-border-controllers.md) certificados e determinou que o SBC implantado está certificado para Roteamento Direto, mas não está certificado para Bypass de Mídia. Para dar suporte à LBR, o Roteamento Direto precisa ser configurado para o SBC local, é necessário que haja uma saída de Internet local e o SBC precisa ser configurado para Bypass de Mídia. Com base nessa informação, a Contoso decidiu o seguinte:

- Para atrasar a habilitação de Teams LBR até que o SBC existente seja certificado para Bypass de Mídia.   

- A Contoso decidiu usar o SBC do site principal para a Rota Direta Office 365.  O SBC do site principal será o SBC de proxy para o site remoto.  

- A Contoso usou um consultor de terceiros com base na Índia para ajudar na certificação da configuração lbr com a empresa de telefonia no país.  

- Para dar suporte a usuários que trabalham de fora do escritório para fazer chamadas PSTN, a empresa emitiu um telefone celular para seus funcionários. 

Os diagramas a seguir mostram as implantações antes e depois de um país com regulamentos de telefonia que exigem Location-Based Roteamento:

**Implantação original**

![Diagrama mostrando antes do estado](media/voice-case-study-5.png)

**Implantação com Roteamento Direto**

![Diagrama mostrando antes do estado](media/voice-case-study-6.png)


## <a name="configuration"></a>Configuração: 

Para configurar os componentes de rede Teams, a Contoso seguiu as instruções em Gerenciar sua topologia de rede [para recursos de voz na nuvem.](manage-your-network-topology.md) A Contoso concluiu as etapas a seguir para configurar Location-Based Routing: 

- Definir regiões de rede - Uma região de rede foi definida. 

- Definir sites de rede - Dois sites de rede foram definidos. Um site para cada local do escritório na região.

- Definir sub-redes de rede - Cada andar dentro de um local do escritório tem sua própria sub-rede para a rede com fio e sem fio. Essa configuração resultou em 20 sub-redes para a Contoso. 

- Definir endereços IP confiáveis - Os endereços IP externos voltados para o SBC foram adicionados ao endereço IP confiável.  

