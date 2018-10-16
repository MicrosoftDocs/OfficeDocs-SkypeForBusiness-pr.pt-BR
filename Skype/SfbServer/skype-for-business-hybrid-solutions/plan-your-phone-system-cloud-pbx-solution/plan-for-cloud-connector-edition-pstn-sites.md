---
title: Plano para sites PSTN do Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Leia este tópico para saber como planejar os sites de nuvem conector Edition PSTN para garantir o roteamento de chamada de eficiência e economia.
ms.openlocfilehash: fa224bd4fa3dc1d0be5db8104e414f9a78d01b30
ms.sourcegitcommit: 58934985891818fa505ae742b1e750edccadd870
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2018
ms.locfileid: "25576516"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Plano para sites PSTN do Cloud Connector Edition
 
Leia este tópico para saber como planejar os sites de nuvem conector Edition PSTN para garantir o roteamento de chamada de eficiência e economia.
  
Este tópico descreve o que você precisa saber sobre a edição do conector de nuvem e roteamento para que você possa planejar seus sites de nuvem conector PSTN de chamada. Um site PSTN é uma combinação de aparelhos de conector de nuvem, implantado no mesmo local e com os gateways PSTN comuns conectados a eles. Este tópico aborda como configurar sua topologia de site do conector de nuvem para garantir que seus sites do conector de nuvem podem tratar do roteamento de entrada e saída para todos os usuários atribuídos a um site da maioria dos custos claros e objetivos maneira possível. Para obter mais informações sobre o conector de nuvem e os benefícios de sites PSTN, não deixe de ler [Planejar Skype para o conector de nuvem Business Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sites PSTN do Cloud Connector e roteamento de chamadas

Sites de PSTN do conector de nuvem são uma construção de topologia criada para evitar interurbano desnecessário e tarifas entre países e para garantir que as chamadas de emergência saídas são roteadas para o tronco apropriado. Para assegurar um roteamento de chamadas econômico e eficiente, incluindo chamadas para serviços de emergência, é preciso planejar seus sites PSTN e a atribuição dos usuários a cada site. 
  
Como parte do planejamento do Cloud Connector, é extremamente importante que você se comunique com as operadoras sobre a localização de seus escritórios e usuários, e onde terminam os troncos PSTN da operadora. Você precisa trabalhar com seus operadoras para determinar como chamadas de emergência podem ser roteadas e use essas informações para definir os sites de nuvem conector PSTN e atribuir usuários para os sites apropriados. Por exemplo, você precisa garantir que os troncos que terminam em um data center no qual o site PSTN é ampliado sejam configurados para lidar com o roteamento de entrada e de saída de todos os números atribuídos aos usuários nesse site. 
  
Cada dispositivo do conector de nuvem pode ser conectado ao vários Gateways IP, IP PBXs ou controladores de borda de sessão (SBCs). Porque os Gateways e PBXs estão conectados ao troncos de telecomunicações (PRI ou SIP troncos), aparelhos de conector de nuvem logicamente conectados a troncos PSTN para chamadas de entrada e saídas. Com o Cloud Connector e a conectividade PSTN local, você obtém o tronco e os números de telefone associados da sua operadora local. Se a sua empresa é de grande porte, talvez vocês usem mais de uma operadora, especialmente se a empresa estiver em mais de uma cidade, um estado ou um país. Como a operadora é proprietária do número de telefone, ela é responsável pela administração das chamadas de emergência.
  
Skype para Business Online trata todos os aparelhos de conector de nuvem em um site igualmente e encaminharão as chamadas de saída em uma base de rotação para aparelhos de conector de nuvem no mesmo site. Cada Cloud Connector em um site é conectado de maneira cruzada ao mesmo conjunto de troncos PSTN (totalmente entrelaçado). Como cada usuário é associado a um site de PSTN do conector de nuvem, qualquer chamada de saída do usuário (normal ou de emergência) será atribuída a um dos appliances nuvem conector no site do PSTN que o usuário está associado. 
  
Conector de nuvem faz o roteamento de chamadas estática para seu anexado Gateways de IP, o IP-PBXs, o SBCs ou a troncos diretos de PSTN. Conector de nuvem não ainda foi capaz de roteamento dinâmico a um tronco com base no destino (para roteamento de menor custo) ou com base na origem (estática ou dinâmica as chamadas de emergência). Chamadas de entrada não são um problema, desde que a chamada só possa vir de um tronco associado com o número. Chamadas de saída, no entanto, podem ir para qualquer aparelho de conector de nuvem em um site (e por extensão troncos PSTN anexados a esse aparelho de conector de nuvem) que podem causar indesejadas chamadas de longa distância. Além disso, as chamadas de emergência não modificará se o site de nuvem conector PSTN é alongado em datacenters com diferentes códigos de área ou operadoras.
  
## <a name="an-example"></a>Um exemplo

O exemplo a seguir mostra como agrupar troncos aos sites PSTN e como atribuir usuários à lista de sites. Para a empresa Contoso, considere o seguinte:
  
- Existem quatro usuários:   
    
  - Usuário A em Redmond WA (EUA)
    
  - Usuário B em Bellevue WA (EUA)
    
  - Usuário C em Centralia WA (EUA)
    
  - Usuário D em Portland OR (EUA)
    
- Operadora A fornecer números de telefone e troncos em:
    
  - Redmond (código de área 425)
    
  - Bellevue (código de área 425)
    
  - Centralia (código de área 360)
    
- B de operadora fornece números de telefone e troncos em:
    
  -  Portland (código de área 503)
    
Como usuário B em Bellevue (B do Centro de dados) e usuário em Redmond (A Data Center) são no bairros próximas umas às outras e no mesmo código de área (425), operadora uma poderá levar a uma chamada de emergência do usuário A em Redmond no tronco em Bellevue. 
  
Consequentemente, os usuários A e B e os troncos de conector de nuvem para Bellevue e Redmond, provavelmente podem ser no mesmo site nuvem conector PSTN conforme mostrado no diagrama a seguir. As chamadas de emergência dos usuários de um escritório podem ser encaminhadas para os troncos do outro. No entanto, você deve, verificar com a sua operadora que isso funcione.
  
![Como configurar sites PSTN](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considere também os seguintes exemplos:
  
- O usuário C em Centralia, cujo número é fornecido pela operadora A, está a duas horas de distância e usa um código de área diferente (360) dos outros usuários da operadora A que usam o código de área 425 de Bellevue e Redmond.  
    
    Portanto, mesmo se uma chamada é proveniente de uma operadora de telefonia, é possível que a chamada da operadora software de roteamento no código de área Centralia 360 pode rejeitar uma emergência entrada chamar provenientes do usuário B Bellevue código de área 425. Nesse caso é essencial que a operadora confirme que o conector de nuvem e seus troncos associados nos sites Centralia PSTN podem lidar com chamadas em distâncias e códigos de área.
    
- Usuário D em Portland usa um número e tronco fornecido pela operadora B, portanto, é altamente improvável que B operadora entrarão em uma chamada de emergência de um número de telefone que pertence ao operadora A. Para que o usuário D e o aparelho de conector de nuvem e troncos associados em Portland precisará estar localizado em um site diferente do PSTN.
    

