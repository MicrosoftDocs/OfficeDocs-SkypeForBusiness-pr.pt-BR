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
> O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
 
Leia este tópico para saber como planejar seus sites PSTN do Cloud Connector Edition para garantir um roteamento de chamadas eficiente e econômico.
  
Este tópico descreve o que você precisa saber sobre o Cloud Connector Edition e o roteamento de chamadas para que você possa planejar seus sites PSTN do Cloud Connector. Um site PSTN é uma combinação de dispositivos do Cloud Connector, implantados no mesmo local e com gateways PSTN comuns conectados a eles. Este tópico se concentra em como configurar sua topologia de site do Cloud Connector para garantir que seus sites do Cloud Connector possam lidar com o roteamento de entrada e saída para todos os usuários atribuídos a um site da maneira mais econômica e eficaz possível. Para obter mais informações sobre o Cloud Connector e os benefícios dos sites PSTN, certifique-se de ler Planejar o [Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md) 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sites PSTN do Cloud Connector e roteamento de chamadas

Os sites PSTN do Cloud Connector são um constructo de topologia criado para evitar interurbano e inter-país desnecessários e para garantir que as chamadas de emergência de saída sejam roteados para o tronco apropriado. Para garantir o roteamento econômico e eficiente de chamadas, incluindo chamadas para serviços de emergência, você deve planejar cuidadosamente seus sites PSTN e como os usuários são atribuídos a cada site. 
  
Como parte do seu planejamento para o Cloud Connector, é essencial que você converse com suas operadoras sobre onde seus escritórios e usuários estão localizados e onde terminam os troncos PSTN da operadora. Você precisa trabalhar com suas operadoras para determinar como as chamadas de emergência podem ser encaminhada e, em seguida, usar essas informações para definir sites PSTN do Cloud Connector e atribuir usuários aos sites apropriados. Por exemplo, você deve garantir que os troncos que terminam em um datacenter onde o site PSTN está estendido estão configurados para lidar com o roteamento de entrada e saída de todos os números atribuídos aos usuários desse site. 
  
Cada dispositivo do Cloud Connector pode ser conectado a vários Gateways IP, PBXs IP ou SBCs (Controladores de Borda de Sessão). Como os Gateways e PBXs estão conectados a troncos telco (troncos PRI ou SIP), os dispositivos do Cloud Connector são logicamente conectados aos troncos PSTN para chamadas de entrada e saída. Com o Cloud Connector e a conectividade PSTN local, você obtém o tronco e os números de telefone associados da operadora local. Se sua empresa for uma grande empresa, você pode ter mais de uma operadora, especialmente se sua empresa abranger mais de uma cidade, estado ou país. Como a operadora é proprietária do número de telefone, ela é responsável pela manipulação de chamadas de emergência.
  
O Skype for Business Online trata igualmente todos os dispositivos do Cloud Connector em um site e roteia as chamadas de saída de forma rotativas para dispositivos do Cloud Connector no mesmo site. Cada Cloud Connector em um site é conectado ao mesmo conjunto de troncos PSTN (totalmente conectados). Como cada usuário está associado a um site PSTN do Cloud Connector, qualquer chamada de saída desse usuário (normal ou de emergência) será atribuída a um dos dispositivos do Cloud Connector no site PSTN ao qual o usuário está associado. 
  
O Cloud Connector faz o roteamento de chamadas estáticas para seus Gateways IP, IP-PBXs, SBCs ou troncos PSTN diretos. O Cloud Connector ainda não é capaz de roteamento dinâmico para um tronco com base no destino (para roteamento de menor custo) ou com base na origem (chamadas de emergência estáticas ou dinâmicas). Chamadas de entrada não são um problema, pois a chamada só pode vir de um tronco associado ao número. As chamadas de saída, no entanto, podem ir para qualquer dispositivo do Cloud Connector em um site (e por extensão os troncos PSTN conectados a esse dispositivo do Cloud Connector), o que pode causar chamadas de longa distância indesejadas. Além disso, as chamadas de emergência não passarão se o site PSTN do Cloud Connector for estendido entre datacenters com diferentes códigos de área ou operadoras.
  
## <a name="an-example"></a>Um exemplo

O exemplo a seguir mostra como agrupar troncos para sites PSTN e como atribuir usuários aos sites. Para a empresa Contoso, suponha o seguinte:
  
- Há quatro usuários: 
    
  - Usuário A em Redmond WA (EUA)
    
  - Usuário B em Bellevue WA (EUA)
    
  - Usuário C em Centralia WA (EUA)
    
  - Usuário D em Portland OR (EUA)
    
- A operadora A fornece números de telefone e troncos em:
    
  - Redmond (código de área 425)
    
  - Bellevue (código de área 425)
    
  - Centralia (código de área 360)
    
- A operadora B fornece números de telefone e troncos em:
    
  -  Portland (código de área 503)
    
Como o usuário A em Redmond (Data Center A) e o usuário B em Bellevue (Data Center B) estão em incódigos próximos uns dos outros e no mesmo código de área (425), a operadora A deve ser capaz de fazer uma chamada de emergência do usuário A em Redmond no tronco em Bellevue. 
  
Consequentemente, os usuários A e B e os troncos do Cloud Connector para Bellevue e Redmond provavelmente podem estar no mesmo site PSTN do Cloud Connector, conforme mostrado no diagrama a seguir. Chamadas de emergência de usuários em um escritório podem ser roteados para troncos no outro. No entanto, você deve verificar com sua operadora se isso funcionará.
  
![Como configurar sites PSTN](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considere os exemplos a seguir também:
  
- O usuário C em Centralia, cujo número é fornecido pela operadora A, está a duas horas de distância e, em um código de área diferente (360), de outros usuários da operadora A no código de área Bellevue e Redmond 425. 
    
    Portanto, mesmo que uma chamada seja proveniente da operadora A, é possível que o software de roteamento de chamadas da operadora no código de área 360 centralia rejeite uma chamada de emergência de entrada originada do usuário B em Bellevue código de área 425. Nesse caso, é fundamental que a operadora confirme se o Cloud Connector e seus troncos associados nos sites PSTN de Centralia podem lidar com chamadas entre distâncias e códigos de área.
    
- O usuário D em Portland usa um número e um tronco fornecidos pela operadora B, portanto, é altamente improvável que a operadora B adote uma chamada de emergência de um número de telefone pertencente à operadora A. Portanto, o usuário D e o dispositivo do Cloud Connector e os troncos associados em Portland terão que estar localizados em um site PSTN diferente.
    

