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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Leia este tópico para saber como planejar os sites PSTN do Cloud Connector Edition para garantir o roteamento de chamadas eficiente e econômica.
ms.openlocfilehash: 7afc5ac09e80edf6b1502e9d169aee77b3bd69b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287031"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Plano para sites PSTN do Cloud Connector Edition
 
Leia este tópico para saber como planejar os sites PSTN do Cloud Connector Edition para garantir o roteamento de chamadas eficiente e econômica.
  
Este tópico descreve o que você precisa saber sobre o Cloud Connector Edition e o roteamento de chamadas para que você possa planejar os sites PSTN do conector de nuvem. Um site PSTN é uma combinação de aparelhos de conector de nuvem, implantada no mesmo local e com gateways PSTN comuns conectados a eles. Este tópico se concentra em como configurar a topologia do site do conector de nuvem para garantir que seus sites do conector de nuvem possam manipular o roteamento de entrada e saída para todos os usuários atribuídos a um site da maneira mais eficiente e eficiente possível. Para obter mais informações sobre o Cloud Connector e os benefícios dos sites PSTN, lembre-se de ler [plano para o Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sites PSTN do Cloud Connector e roteamento de chamadas

Os sites PSTN do conector de nuvem são uma construção de topologia criada para impedir tarifas de longa distância e entre países desnecessárias e para garantir que as chamadas de emergência de saída sejam roteadas para o tronco apropriado. Para garantir o encaminhamento econômico e eficiente de chamadas, incluindo chamadas para serviços de emergência, você deve planejar cuidadosamente seus sites PSTN e como os usuários são atribuídos a cada site. 
  
Como parte do seu planejamento para o conector de nuvem, é essencial que você converse com suas operadoras sobre onde estão localizados seus escritórios e usuários e onde os troncos PSTN são encerrados na transportadora. Você precisa trabalhar com suas operadoras para determinar como as chamadas de emergência podem ser roteadas e, em seguida, usar essas informações para definir sites PSTN do conector de nuvem e atribuir usuários aos sites apropriados. Por exemplo, você precisa garantir que os troncos que terminam em um data center no qual o local de PSTN é ampliado sejam configurados para lidar com o roteamento de entrada e de saída de todos os números atribuídos aos usuários nesse site. 
  
Cada dispositivo de conector de nuvem pode ser conectado a vários gateways IP, PBXs de IP ou controladores de borda de sessão (SBCs). Como os gateways e PBXs estão conectados a troncos de telecomunicações (troncos PRI ou SIP), os aparelhos de conector de nuvem são conectados logicamente a troncos PSTN para chamadas de entrada e saída. Com o conector de nuvem e a conectividade PSTN local, você obtém o tronco e os números de telefone associados da sua operadora local. Se a sua empresa é de grande porte, talvez vocês usem mais de uma operadora, especialmente se a empresa estiver em mais de uma cidade, um estado ou um país. Como a operadora é proprietária do número de telefone, ela é responsável pela administração das chamadas de emergência.
  
O Skype for Business online trata igualmente todos os aparelhos de conector de nuvem em um site, e roteia chamadas de saída de forma rotativa para dispositivos de conector de nuvem no mesmo site. Cada conector de nuvem em um site tem conexão cruzada com o mesmo conjunto de troncos PSTN (completamente malhada). Como cada usuário está associado a um site PSTN do conector de nuvem, todas as chamadas de saída desse usuário (normal ou de emergência) serão atribuídas a um dos dispositivos de conector de nuvem no site PSTN ao qual o usuário está associado. 
  
O conector de nuvem faz roteamento de chamadas estáticas para seus gateways IP conectados, PBXs IP, SBCs ou troncos PSTN diretos. O Cloud Connector ainda não é capaz de roteamento dinâmico para um tronco baseado no destino (para roteamento de menor custo) ou com base na origem (chamada de emergência estática ou dinâmica). As chamadas recebidas não são um problema, pois a chamada só pode ser proveniente de um tronco associado ao número. As chamadas de saída, no entanto, podem ir para qualquer dispositivo de conector de nuvem em um site (e, por extensão, os troncos PSTN conectados a esse aparelho de conector de nuvem), o que pode causar chamadas de longa distância indesejáveis. Além disso, as chamadas de emergência não passarão se o site PSTN do conector de nuvem estiver ampliado em datacenters com diferentes códigos de área ou operadoras.
  
## <a name="an-example"></a>Um exemplo

O exemplo a seguir mostra como agrupar troncos em sites PSTN e como atribuir usuários aos sites. Para a empresa Contoso, considere o seguinte:
  
- Existem quatro usuários:  
    
  - Usuário A em Redmond WA (EUA)
    
  - Usuário B em Bellevue WA (EUA)
    
  - Usuário C em Centralia WA (EUA)
    
  - Usuário D em Portland ou (EUA)
    
- O Carrier A fornece números de telefone e troncos em:
    
  - Redmond (código de área 425)
    
  - Bellevue (código de área 425)
    
  - Centralia (código de área 360)
    
- A operadora B fornece números de telefone e troncos em:
    
  -  Portland (código de área 503)
    
Como o usuário A em Redmond (Data Center A) e o usuário B no Palmares (centro de dados B) estão Suburbs próximos uns dos outros e no mesmo código de área (425), A operadora A deve ser capaz de fazer uma chamada de emergência do usuário A em Redmond no tronco no Palmares. 
  
Consequentemente, os usuários A e B e os troncos do conector de nuvem para Palmares e Redmond podem estar no mesmo site PSTN do conector de nuvem, conforme mostrado no diagrama a seguir. As chamadas de emergência dos usuários de um escritório podem ser encaminhadas para os troncos do outro. No entanto, você deve verificar com sua operadora que isso funcionará.
  
![Como configurar sites PSTN](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considere também os seguintes exemplos:
  
- O usuário C em Centralia, cujo número é fornecido pela operadora A, está a duas horas de distância e usa um código de área diferente (360) dos outros usuários da operadora A que usam o código de área 425 de Bellevue e Redmond.  
    
    Portanto, mesmo se uma chamada for proveniente da concessionária A, é possível que o software de roteamento de chamadas da operadora no código de área Centralia 360 pode rejeitar uma chamada de emergência de entrada originada do usuário B no código de área Palmares 425. Nesse caso, é fundamental que a operadora confirme que o conector de nuvem e seus troncos associados nos sites PSTN Centralia podem manipular chamadas entre distâncias e códigos de área.
    
- O usuário D em Portland usa um número e tronco fornecidos pela transportadora B, portanto, é muito improvável que a operadora B faça uma chamada de emergência a partir de um número de telefone pertencente à transportadora. Portanto, o usuário D e o aparelho de conector de nuvem e os troncos associados em Portland devem estar localizados em um site PSTN diferente.
    

