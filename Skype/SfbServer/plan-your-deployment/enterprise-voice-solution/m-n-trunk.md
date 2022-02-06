---
title: Tronco MN no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: 'Skype for Business Server Enterprise Voice suporte ao tronco M:N entre o Servidor de Mediação e componentes, como gateways PSTN, controladores de borda de sessão e IP-PBX.'
---

# <a name="mn-trunk-in-skype-for-business-server"></a>Tronco M:N no Skype for Business Server
 
Skype for Business Server Enterprise Voice suporte ao tronco M:N entre o Servidor de Mediação e componentes, como gateways PSTN, controladores de borda de sessão e IP-PBX.
  
Skype for Business Server oferece maior flexibilidade na definição de um tronco para fins de roteamento de chamadas de versões anteriores. Um tronco é uma associação lógica entre um Servidor de Mediação e o número da porta de escuta com um gateway e um número de porta de escuta. Isso implica em várias coisas: um Servidor de Mediação pode ter vários troncos para o mesmo gateway; um Servidor de Mediação pode ter vários troncos para gateways diferentes; inversamente, um gateway pode ter vários troncos para diferentes Servidores de Mediação.
  
Você ainda deve criar um tronco raiz sempre que usar o Construtor de Topologias para adicionar um gateway à topologia. O número de gateways que um determinado Servidor de Mediação pode manipular depende da capacidade de processamento do servidor durante o horário de pico de ocupado. Se você implantar um Servidor de Mediação em hardware que exceda os requisitos mínimos de hardware para o Skype for Business Server, conforme descrito em Requisitos de servidor para [o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), a estimativa de quantas chamadas ativas que um Servidor de Mediação autônomo pode manipular é de aproximadamente 1.000 chamadas. Quando implantado no hardware que cumpre essas especificações, espera-se que o Servidor de Mediação execute a transcodificação, mas ainda roteia chamadas para vários gateways, mesmo que os gateways não suportem o bypass de mídia.
  
Ao definir uma rota de chamada, especifique os troncos associados a essa rota, mas não especifique quais Servidores de Mediação estão associados a essa rota. Em vez disso, você usa o Construtor de Topologias para associar troncos aos Servidores de Mediação. Em outras palavras, o roteamento determina qual tronco usar para uma chamada e, posteriormente, o Servidor de Mediação associado a esse tronco é enviado para a sinalização dessa chamada.
  
O Servidor de Mediação pode ser implantado como um pool; esse pool pode ser alocado com um pool de Front-End ou pode ser implantado como um pool autônomo. Quando um Servidor de Mediação é alocado com um pool de Front-End, o tamanho do pool pode ter no máximo 12 (o limite do tamanho do pool do Registrador). Juntos, esses novos recursos aumentam a confiabilidade e a flexibilidade de implantação para Servidores de Mediação, mas exigem recursos associados nas seguintes entidades pares:
  
- **Gateway PSTN.** Um gateway Skype for Business Server qualificado deve implementar o balanceamento de carga DNS, que permite que um gateway PSTN (rede telefônica pública comutado) qualificado atue como um balanceador de carga para um pool de Servidores de Mediação e, assim, balancee as chamadas em todo o pool.
    
- **Controlador de Borda de Sessão.** Para um tronco SIP, a entidade par é um Controlador de Borda de Sessão (SBC) em um provedor de serviços de telefonia da Internet. Na direção do pool do Servidor de Mediação para o SBC, o SBC pode receber conexões de qualquer Servidor de Mediação no pool. Na direção do SBC para o pool, o tráfego pode ser enviado para qualquer Servidor de Mediação no pool. Um método para alcançar isso é por meio do balanceamento de carga DNS, se suportado pelo provedor de serviços e pelo SBC. Uma alternativa é dar ao provedor de serviços os endereços IP de todos os Servidores de Mediação no pool, e o provedor de serviços os provisionará em seu SBC como um tronco SIP separado para cada Servidor de Mediação. Em seguida, o provedor de serviços manipulará o balanceamento de carga para seus próprios servidores. Nem todos os provedores de serviços ou SBCs podem dar suporte a esses recursos. Além disso, o provedor de serviços pode cobrar extra por esse recurso. Normalmente, cada tronco SIP para o SBC incorre em uma taxa mensal.
    
- **IP-PBX.** Na direção do pool do Servidor de Mediação até a terminação SIP IP-PBX, o IP-PBX pode receber conexões de qualquer Servidor de Mediação no pool. Na direção do IP-PBX para o pool, o tráfego pode ser enviado para qualquer Servidor de Mediação no pool. Como a maioria IP-PBXs não suporta o balanceamento de carga DNS, recomendamos que as conexões SIP diretas individuais sejam definidas do IP-PBX para cada Servidor de Mediação no pool. O IP-PBX tratará seu próprio balanceamento de carga distribuindo tráfego sobre o grupo de troncos. A suposição é que o grupo de troncos tem um conjunto consistente de regras de roteamento no IP-PBX. Se um IP-PBX específico dá suporte a esse conceito de grupo de tronco e como ele interseção com a própria redundância e a arquitetura de cluster do IP-PBX precisa ser determinado antes de decidir se um cluster do Servidor de Mediação pode interagir corretamente com um IP-PBX.
    
Um pool do Servidor de Mediação deve ter uma exibição uniforme do gateway par com o qual ele interage. Isso significa que todos os membros do pool acessam a mesma definição do gateway par do armazenamento de configuração e têm a mesma probabilidade de interagir com ele para chamadas de saída. Portanto, não há como segmentar o pool para que alguns Servidores de Mediação se comuniquem apenas com determinados pares de gateway para chamadas de saída. Se essa segmentação for necessária, um pool separado de Servidores de Mediação deve ser usado. Esse seria o caso, por exemplo, se os recursos associados em gateways PSTN, troncos SIP ou IP-PBXs interagir com um pool conforme detalhado anteriormente neste tópico não estão presentes.
  
Um gateway PSTN específico, IP-PBX ou par de tronco SIP pode rotear para vários Servidores de Mediação ou troncos. O número de gateways que um pool específico de Servidores de Mediação pode controlar depende do número de chamadas que usam bypass de mídia. Se um grande número de chamadas usar bypass de mídia, um Servidor de Mediação no pool poderá lidar com muitas outras chamadas, pois somente o processamento da camada de sinalização é necessário. 
  

