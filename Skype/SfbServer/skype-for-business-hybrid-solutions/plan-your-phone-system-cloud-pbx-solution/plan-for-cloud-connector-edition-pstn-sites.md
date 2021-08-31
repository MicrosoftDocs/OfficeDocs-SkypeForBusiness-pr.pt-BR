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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Leia este tópico para saber como planejar seus sites PSTN do Cloud Connector Edition para garantir o roteamento de chamadas eficiente e econômico.
ms.openlocfilehash: 50b30a5071dd14cc0016419d85406b7c50d85387
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729230"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Plano para sites PSTN do Cloud Connector Edition

> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)
 
Leia este tópico para saber como planejar seus sites PSTN do Cloud Connector Edition para garantir o roteamento de chamadas eficiente e econômico.
  
Este tópico descreve o que você precisa saber sobre o Cloud Connector Edition e o roteamento de chamadas para que você possa planejar seus sites PSTN do Cloud Connector. Um site PSTN é uma combinação de dispositivos do Cloud Connector, implantados no mesmo local e com gateways PSTN comuns conectados a eles. Este tópico se concentra em como configurar sua topologia de site do Cloud Connector para garantir que seus sites do Cloud Connector possam lidar com o roteamento de entrada e de saída para todos os usuários atribuídos a um site da maneira mais eficiente e eficaz possível. Para obter mais informações sobre o Cloud Connector e os benefícios dos sites PSTN, leia [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sites PSTN do Cloud Connector e roteamento de chamadas

Os sites PSTN do Cloud Connector são uma construção de topologia criada para evitar tarifas de longa distância e entre países desnecessárias e garantir que as chamadas de emergência de saída sejam roteados para o tronco apropriado. Para garantir o roteamento econômico e eficiente de chamadas, incluindo chamadas para serviços de emergência, você deve planejar cuidadosamente seus sites PSTN e como os usuários são atribuídos a cada site. 
  
Como parte do seu planejamento para o Cloud Connector, é essencial que você fale com suas operadoras sobre onde seus escritórios e usuários estão localizados e onde os troncos PSTN terminam da operadora. Você precisa trabalhar com suas operadoras para determinar como as chamadas de emergência podem ser roteados e, em seguida, usar essas informações para definir sites PSTN do Cloud Connector e atribuir usuários aos sites apropriados. Por exemplo, você deve garantir que os troncos que terminam em um datacenter onde o site PSTN está estendido estão configurados para lidar com o roteamento de entrada e saída para todos os números atribuídos aos usuários nesse site. 
  
Cada dispositivo do Cloud Connector pode ser conectado a vários Gateways IP, PBXs IP ou Controladores de Borda de Sessão (SBCs). Como os Gateways e PBXs estão conectados a troncos telco (troncos PRI ou SIP), os dispositivos do Cloud Connector são logicamente conectados a troncos PSTN para chamadas de entrada e saída. Com o Cloud Connector e a conectividade PSTN local, você obtém o tronco e os números de telefone associados de sua operadora local. Se sua empresa for uma grande empresa, você poderá ter mais de uma operadora, especialmente se sua empresa abranger mais de uma cidade, estado ou país. Como sua operadora é proprietária do número de telefone, a operadora é responsável por lidar com chamadas de emergência.
  
Skype for Business Online trata todos os dispositivos do Cloud Connector em um site igualmente e roteia chamadas de saída em rotação para dispositivos do Cloud Connector no mesmo site. Cada Cloud Connector em um site é conectado ao mesmo conjunto de troncos PSTN (totalmente meshed). Como cada usuário está associado a um site PSTN do Cloud Connector, qualquer chamada de saída desse usuário (normal ou emergência) será atribuída a um dos dispositivos do Cloud Connector no site PSTN ao qual o usuário está associado. 
  
O Cloud Connector faz o roteamento de chamadas estáticas para seus Gateways IP anexados, IP-PBXs, SBCs ou troncos PSTN diretos. O Cloud Connector ainda não é capaz de roteamento dinâmico para um tronco com base no destino (para roteamento de menor custo) ou com base na origem (chamada de emergência estática ou dinâmica). As chamadas de entrada não são um problema, pois a chamada só pode vir de um tronco associado ao número. As chamadas de saída, no entanto, podem ir para qualquer dispositivo do Cloud Connector em um site (e, por extensão, os troncos PSTN anexados a esse dispositivo do Cloud Connector) que podem causar chamadas de longa distância indesejadas. Além disso, as chamadas de emergência não passarão se o site PSTN do Cloud Connector for estendido entre datacenters com diferentes códigos de área ou operadoras.
  
## <a name="an-example"></a>Um exemplo

O exemplo a seguir mostra como agrupar troncos em sites PSTN e como atribuir usuários aos sites. Para a empresa Contoso, suponha o seguinte:
  
- Há quatro usuários: 
    
  - Usuário A em Redmond WA (EUA)
    
  - Usuário B em Bellevue WA (EUA)
    
  - Usuário C em Centralia WA (EUA)
    
  - Usuário D em Portland OR (EUA)
    
- A Operadora A fornece números de telefone e troncos em:
    
  - Redmond (código de área 425)
    
  - Bellevue (código de área 425)
    
  - Centralia (código de área 360)
    
- A Operadora B fornece números de telefone e troncos em:
    
  -  Portland (código de área 503)
    
Como o usuário A em Redmond (Data Center A) e o usuário B em Bellevue (Data Center B) estão em bairros próximos um do outro e no mesmo código de área (425), a Operadora A deve ser capaz de fazer uma Chamada de Emergência do usuário A em Redmond no tronco em Bellevue. 
  
Consequentemente, os usuários A e B e os troncos do Cloud Connector para Bellevue e Redmond provavelmente estarão no mesmo site PSTN do Cloud Connector, conforme mostrado no diagrama a seguir. Chamadas de emergência de usuários em um escritório podem ser roteados para troncos no outro. Você deve, no entanto, verificar com sua operadora que isso funcionará.
  
![Como configurar sites PSTN.](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considere os exemplos a seguir também:
  
- O usuário C na Centralia, cujo número é fornecido pela Operadora A, está a duas horas de distância e em um código de área diferente (360), de outros usuários da Operadora A no código de área Bellevue e Redmond 425. 
    
    Portanto, mesmo que uma chamada seja proveniente da Operadora A, é possível que o software de roteamento de chamadas da operadora no código de área centralia 360 possa rejeitar uma chamada de emergência de entrada originada do usuário B no código de área bellevue 425. Nesse caso, é fundamental que a operadora confirme se o Cloud Connector e seus troncos associados nos sites PSTN da Centralia podem manipular chamadas entre distâncias e códigos de área.
    
- O usuário D em Portland usa um número e um tronco fornecidos pela Operadora B, portanto, é altamente improvável que a Operadora B atenderá a uma chamada de emergência de um número de telefone pertencente à Operadora A. Portanto, o usuário D e o dispositivo Cloud Connector e troncos associados em Portland terão que estar localizados em um site PSTN diferente.
