---
title: Plano para sites PSTN do Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Leia este tópico para saber como planejar seus sites PSTN do Cloud Connector Edition para garantir um roteamento de chamadas eficiente e econômico.
ms.openlocfilehash: 3b4320e12a87c771e28fce445102327c7783a5d2
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358797"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Plano para sites PSTN do Cloud Connector Edition

> [!Important]
> O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online. Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Leia este tópico para saber como planejar seus sites PSTN do Cloud Connector Edition para garantir um roteamento de chamadas eficiente e econômico.
  
Este tópico descreve o que você precisa saber sobre o Cloud Connector Edition e o roteamento de chamadas para que você possa planejar seus sites PSTN do Cloud Connector. Um site PSTN é uma combinação de dispositivos do Cloud Connector, implantado no mesmo local e com gateways PSTN comuns conectados a eles. Este tópico se concentra em como configurar sua topologia de site do Cloud Connector para garantir que seus sites do Cloud Connector possam lidar com roteamento de entrada e saída para todos os usuários atribuídos a um site da maneira mais eficiente e eficaz possível. Para obter mais informações sobre o Cloud Connector e os benefícios dos sites PSTN, leia [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sites PSTN do Cloud Connector e roteamento de chamadas

Os sites PSTN do Cloud Connector são uma construção de topologia criada para evitar tarifas de longa distância e entre países desnecessárias e para garantir que as chamadas de emergência de saída sejam encaminhadas para o tronco apropriado. Para garantir um roteamento econômico e eficiente de chamadas, incluindo chamadas para serviços de emergência, você deve planejar cuidadosamente seus sites PSTN e como os usuários são atribuídos a cada site. 
  
Como parte do seu planejamento para o Cloud Connector, é essencial que você converse com suas operadoras sobre onde seus escritórios e usuários estão localizados e onde os troncos PSTN terminam da operadora. Você precisa trabalhar com suas operadoras para determinar como as chamadas de emergência podem ser encaminhadas e, em seguida, usar essas informações para definir sites PSTN do Cloud Connector e atribuir usuários aos sites apropriados. Por exemplo, você deve garantir que os troncos que terminam em um datacenter onde o site PSTN esteja alongado estejam configurados para lidar com o roteamento de entrada e saída para todos os números atribuídos aos usuários desse site. 
  
Cada dispositivo do Cloud Connector pode ser conectado a vários gateways IP, PBXs IP ou controladores de borda de sessão (SBCs). Como os gateways e PBXs estão conectados a troncos de telecomunicações (troncos PRI ou SIP), os dispositivos do Cloud Connector são conectados de forma lógica aos troncos PSTN para chamadas de entrada e de saída. Com o Cloud Connector e a conectividade PSTN local, você obtém o tronco e os números de telefone associados da sua operadora local. Se sua empresa é uma grande empresa, você pode ter mais de uma operadora, especialmente se sua empresa abrange mais de uma cidade, estado ou país. Como a operadora é proprietária do número de telefone, a operadora é responsável por lidar com as chamadas de emergência.
  
O Skype for Business online trata todos os dispositivos do Cloud Connector em um site igualmente, e roteará chamadas de saída de forma rotativa para dispositivos do Cloud Connector no mesmo site. Cada Cloud Connector em um site está conectado ao mesmo conjunto de troncos PSTN (totalmente entrelaçado). Como cada usuário é associado a um site PSTN do Cloud Connector, qualquer chamada de saída desse usuário (normal ou de emergência) será atribuída a um dos dispositivos do Cloud Connector no site PSTN com o qual o usuário está associado. 
  
O Cloud Connector faz roteamento de chamada estática para seus gateways IP conectados, IP-PBXs, SBCs ou troncos PSTN diretos. O Cloud Connector ainda não é capaz de roteamento dinâmico para um tronco com base no destino (para roteamento de menor custo) ou com base na origem (chamada de emergência estática ou dinâmica). As chamadas de entrada não são um problema, pois a chamada só pode ser proveniente de um tronco associado ao número. As chamadas de saída, no entanto, podem ir para qualquer dispositivo do Cloud Connector em um site (e por extensão os troncos PSTN anexados a esse dispositivo do Cloud Connector) que podem causar chamadas de longa distância indesejadas. Além disso, as chamadas de emergência não passarão se o site PSTN do Cloud Connector estiver esticado em datacenters com códigos de área ou operadoras diferentes.
  
## <a name="an-example"></a>Um exemplo

O exemplo a seguir mostra como agrupar troncos para sites PSTN e como atribuir usuários aos sites. Para a empresa contoso, considere o seguinte:
  
- Há quatro usuários: 
    
  - Usuário A em Redmond WA (EUA)
    
  - Usuário B no Bellevue WA (EUA)
    
  - Usuário C no Centralia WA (EUA)
    
  - Usuário D em Portland ou (EUA)
    
- A operadora A fornece números de telefone e troncos em:
    
  - Redmond (código de área 425)
    
  - Bellevue (código de área 425)
    
  - Centralia (código de área 360)
    
- A operadora B fornece números de telefone e troncos em:
    
  -  Portland (código de área 503)
    
Como o usuário A em Redmond (Data Center A) e o usuário B no Bellevue (Data Center B) estão no Suburbs ao lado uns dos outros e no mesmo código de área (425), A operadora A deve ser capaz de fazer uma chamada de emergência do usuário A em Redmond no tronco no Bellevue. 
  
Consequentemente, os usuários A e B, e os troncos do Cloud Connector para Bellevue e Redmond, provavelmente podem estar no mesmo site PSTN do Cloud Connector, conforme mostrado no diagrama a seguir. As chamadas de emergência de usuários em um escritório podem ser encaminhadas para troncos no outro. No entanto, você deve verificar com sua operadora que isso funcionará.
  
![Como configurar sites PSTN](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considere também os exemplos a seguir:
  
- O usuário C no Centralia, cujo número é fornecido pela concessionária A, é uma unidade de duas horas distante e, em um código de área diferente (360), de outra operadora de usuários no código de área Bellevue e Redmond 425. 
    
    Portanto, mesmo que uma chamada seja proveniente da concessionária A, é possível que o software de roteamento de chamadas da operadora no código de área do Centralia 360 possa rejeitar uma chamada de emergência de entrada originada do usuário B no código de área Bellevue 425. Nesse caso, é fundamental que a operadora confirme que o Cloud Connector e seus troncos associados nos sites PSTN do Centralia podem lidar com chamadas entre distâncias e códigos de área.
    
- O usuário D em Portland usa um número e tronco fornecidos pela transportadora B, portanto, é altamente improvável que a operadora B faça uma chamada de emergência a partir de um número de telefone pertencente à operadora A. Portanto, o usuário D e o dispositivo do Cloud Connector e os troncos associados em Portland precisarão estar localizados em um site PSTN diferente.
    

