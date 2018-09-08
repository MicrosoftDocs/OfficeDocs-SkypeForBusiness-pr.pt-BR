---
title: Tronco MN no Skype para Business Server
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
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: Skype para Business Server Enterprise Voice oferece suporte a tronco M:N entre o servidor de mediação e componentes, como o IP-PBX, controladores de borda de sessão e gateways PSTN.
ms.openlocfilehash: 548ba95d3cd3b8c21fcb5fb489f5c70e70a80ce2
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882169"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>Tronco M:N no Skype para Business Server
 
Skype para Business Server Enterprise Voice oferece suporte a tronco M:N entre o servidor de mediação e componentes, como o IP-PBX, controladores de borda de sessão e gateways PSTN.
  
Skype para Business Server oferece suporte a maior flexibilidade na definição de um tronco para fins de roteamento de chamada de versões anteriores. Um tronco é uma associação lógica entre um servidor de mediação e o número da porta de escuta com um gateway e um número de porta de escuta. Isso implica várias coisas: um servidor de mediação pode ter vários troncos para o mesmo gateway; um servidor de mediação pode ter vários troncos para gateways diferentes; Por outro lado, um gateway pode ter vários troncos para diferentes servidores de mediação.
  
Você deve ainda criar um tronco raiz sempre que você use o construtor de topologias para adde um gateway à topologia. O número de gateways que um determinado servidor de mediação pode lidar depende a capacidade de processamento do servidor durante o horário de pico ocupado. Se você implantar um servidor de mediação em um hardware que excede os requisitos mínimos de hardware para Skype para Business Server, conforme descrito em [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), em seguida, a estimativa de quantas chamadas ativas de não ignorar uma Servidor de mediação autônomo pode manipular é aproximadamente chamadas de 1000. Quando implantado na reunião de hardware essas especificações, o servidor de mediação é esperado para executar a transcodificação, mas ainda rotear as chamadas para vários gateways, mesmo se os gateways não suportam bypass de mídia.
  
Ao definir uma rota de chamada, você especificar os troncos associados a essa rota, mas você não especificar quais servidores de mediação estão associados essa rota. Em vez disso, use o construtor de topologias para associar troncos com servidores de mediação. Em outras palavras, roteamento determina qual tronco a ser usado para uma chamada e, subsequentemente, o servidor de mediação associado a esse tronco é enviado a sinalização para essa chamada.
  
O servidor de mediação pode ser implantado como um pool; Este pool pode ser colocado com um pool de Front-End ou ele pode ser implantado como um pool autônomo. Quando um servidor de mediação é colocado com um pool de Front-End, o tamanho do pool pode ter no máximo 12 (o limite do tamanho do pool de registrador). Juntos, esses novos recursos aumentam a confiabilidade e a flexibilidade de implantação dos servidores de mediação, mas eles exigem que os recursos associados nas seguintes entidades ponto:
  
- **Gateway PSTN.** Um Skype para gateway qualificado do Business Server deve implementar balanceamento de carga DNS, que permite que um gateway PSTN (rede) qualificado telefônica comutada pública agir como um balanceador de carga para um pool de servidores de mediação e, portanto, para chamadas de balanceamento de carga todo o pool .
    
- **Controlador de Borda da Sessão.** Para um tronco SIP, a entidade par é um SBC (Controlador de Borda da Sessão) no provedor de serviços de telefonia da Internet. Na direção do pool de servidores de mediação para o SBC, o SBC pode receber conexões de qualquer servidor de mediação no pool. Na direção do SBC para o pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Um método que permite isso é através do balanceamento de carga DNS, se ele tiver suporte do provedor de serviços e do SBC. Uma alternativa é dar os endereços IP de todos os servidores de mediação no pool de provedor de serviços e o provedor de serviço provisionará esses no seu SBC como um tronco SIP separado para cada servidor de mediação. O provedor de serviços tratará o balanceamento de carga de seus próprios servidores. Nem todos os provedores de serviços ou SBCs podem dar suporte a essas funcionalidades. Além disso, o provedor de serviços pode cobrar mais por essa funcionalidade. Geralmente, cada tronco SIP até o SBC é tarifado mensalmente.
    
- **IP-PBX.** Na direção do pool de servidores de mediação para a terminação SIP IP-PBX, IP-PBX pode receber conexões de qualquer servidor de mediação no pool. Na direção do IP-PBX para o pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Porque a maioria dos IP-PBXs não suportam o balanceamento de carga do DNS, recomendamos que individuais conexões SIP diretas ser definidos de IP-PBX para cada servidor de mediação no pool. Depois disso, o IP-PBX tratará seu próprio balanceamento de carga distribuindo o tráfego pelo grupo de troncos. Presume-se que o grupo de troncos tenha um conjunto de regras de roteamento consistente no IP-PBX. Se um determinado IP-PBX oferece suporte a esse conceito de grupo do tronco e como ele faz interseção com a redundância do IP-PBX próprio e arquitetura de cluster precisa ser determinada antes de você pode decidir se um cluster de servidor de mediação pode interagir corretamente com um IP-PBX.
    
Um pool de servidores de mediação deve ter um modo de exibição uniforme do gateway ponto com a qual ele interage. Isso significa que todos os membros do pool acessam a mesma definição do gateway par a partir do repositório de configurações e têm a mesma probabilidade de interagir com ele para as chamadas de saída. Portanto, não há um meio para segmentar o pool para que alguns servidores de mediação se comunicar com apenas determinados pares de gateway para chamadas de saída. Se tais segmentação for necessária, um pool separado dos servidores de mediação deve ser usado. Isso seria o caso, por exemplo, se as funcionalidades associadas nos gateways PSTN, nos troncos SIP ou nos IP-PBXs para interagir com um pool, conforme detalhado anteriormente neste tópico, não estivessem presentes.
  
Um gateway específico do PSTN, IP-PBX ou ponto de tronco SIP pode rotear para vários servidores de mediação ou troncos. O número de gateways que um determinado pool de servidores de mediação pode controlar depende do número de chamadas que usam bypass de mídia. Se um grande número de chamadas usa bypass de mídia, um servidor de mediação no pool pode manipular várias chamadas mais, porque o processamento de camada de sinalização somente é necessário. 
  

