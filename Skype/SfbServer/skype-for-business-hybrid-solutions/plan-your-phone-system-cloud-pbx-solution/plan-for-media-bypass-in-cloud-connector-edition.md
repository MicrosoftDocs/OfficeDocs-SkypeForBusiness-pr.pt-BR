---
title: Plano para bypass de mídia no Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Leia este tópico para revisar as considerações de planejamento para implementar o bypass de mídia com o Cloud Connector Edition versão 2.0 e posterior. Para obter informações sobre como implantar o bypass de mídia, consulte Implantar bypass de mídia no Cloud Connector Edition.
ms.openlocfilehash: 568fa13584a44540d8351ea2eb32475c1d276ff7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220251"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Plano para bypass de mídia no Cloud Connector Edition
 
Leia este tópico para revisar as considerações de planejamento para implementar o bypass de mídia com o Cloud Connector Edition versão 2.0 e posterior. Para obter informações sobre como implantar o bypass de mídia, [consulte Implantar bypass de mídia no Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da PSTN (Rede Telefônica Pública Comucionária), um gateway ou Controlador de Borda de Sessão (SBC) e elimine o componente do Cloud Connector Edition do caminho de mídia.
  
O bypass de mídia pode melhorar a qualidade da voz reduzindo a latência, a possibilidade de perda de pacotes e o número de pontos de falha possíveis. A eliminação do processamento de mídia para chamadas ignoradas reduz a carga no Cloud Connector, o que permite um número maior de chamadas simultâneas e pode melhorar a escalabilidade. 
  
 A liberação do Cloud Connector das tarefas de processamento de mídia pode reduzir o número de dispositivos do Cloud Connector que uma infraestrutura exige, portanto, você deve habilitar o bypass de mídia sempre que possível.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Como o bypass de mídia afeta os caminhos de mídia e sinalização

Embora a sinalização desdobra o mesmo caminho com ou sem bypass de mídia, o fluxo de mídia será diferente. Os diagramas a seguir mostram caminhos de mídia e sinalização em topologias com e sem bypass de mídia. 
  
Por exemplo, na topologia a seguir, que não emprega bypass de mídia, um cliente do Skype for Business faz uma chamada PSTN para um número externo, a sinalização SIP vai para o Microsoft 365 ou Office 365, que direciona o tráfego de sinalização de acordo com a política de voz do usuário final. Para usuários do Cloud Connector, a política de voz direciona o tráfego de sinalização para o Servidor de Borda do Cloud Connector, que, em seguida, encaminha o tráfego de sinalização para um SBC (Controlador de Borda de Sessão) PSTN ou gateway por meio do Servidor de Mediação do Cloud Connector. A mídia flui do cliente Skype for Business para o Servidor de Mediação do Cloud Connector e, em seguida, para o SBC ou gateway, conforme mostrado no diagrama a seguir:
  
**Caminhos de sinalização e mídia sem bypass de mídia**

![sinalização sem bypass de mídia](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Uma chamada de entrada da PSTN usa o mesmo caminho de sinalização na direção inversa. Para usuários internos, a mídia ainda fluirá entre o cliente do Skype for Business e o Servidor de Mediação do Cloud Connector e, em seguida, o SBC ou gateway.
  
Na próxima topologia, que emprega bypass de mídia, a sinalização segue o mesmo caminho, mas a mídia flui diretamente entre o cliente Skype for Business e o SBC ou gateway, conforme mostrado no diagrama a seguir:
  
**Caminhos de sinalização e mídia com bypass de mídia**

![sinalização com bypass de mídia](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Cenário de vários sites e bypass de mídia

O bypass de mídia também é útil quando você deseja fornecer serviços de telefonia a vários sites usando um único dispositivo do Cloud Connector. Como o Cloud Connector não pode rotear chamadas com base em números de origem ou destino, a maioria das empresas implanta um SBC ou gateway por trás do Cloud Connector para tomar decisões de roteamento. O bypass de mídia neste cenário elimina o salto entre o cliente e o SBC ou gateway central, conforme mostrado no diagrama a seguir:
  
**Aplicativo multissu site**

![Exemplo de multissite do Cloud Connector](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. O tráfego SIP flui do usuário em Zurique para o Microsoft 365 ou Office 365.
    
2. Em seguida, o tráfego é roteado para o dispositivo do Cloud Connector em Amsterdã, conforme especificado na política de roteamento de voz do usuário.
    
3. O dispositivo do Cloud Connector em Amsterdã envia o tráfego SIP para o gateway central em Amsterdã.
    
4. O gateway central em Amsterdã toma as decisões de roteamento apropriadas e envia o tráfego para um SBC ou gateway em Zurique, enquanto a mídia flui diretamente entre o cliente Skype for Business e o SBC ou gateway em Amsterdã.
    
   Essa abordagem permite atender a mais usuários por implantação do Cloud Connector em que o Cloud Connector está centralizado. Mesmo que o Cloud Connector seja eliminado do caminho de mídia, uma mídia centralizada de cenário multissu site ainda pode atravessar a WAN duas vezes conforme necessário para fluir pelo SBC ou gateway centralizado.
  
Se um cliente estiver fora da rede corporativa fazendo uma chamada de saída, o tráfego de mídia fluirá através dos servidores de Borda e mediação do Cloud Connector e do link WAN entre Zurique e Amsterdã, conforme mostrado no diagrama a seguir:
  
![Exemplo 2 de multissite do Cloud Connector](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clientes com suporte para bypass de mídia

Com a primeira versão do bypass de mídia, o único cliente com suporte é o Skype for Business 2016 Windows Client, que faz parte do Microsoft 365 Apps para empresas, versão 16.0.7870.2020 ou superior. Os clientes podem usar qualquer canal: Atual, Adiado ou Primeiro Lançamento Adiado. 
  
> [!NOTE]
> Se você estiver usando uma solução VPN do cliente em combinação com o cliente Skype for Business, o bypass de mídia só será suportado com uma configuração de túnel dividido de VPN. 
  
Para obter mais informações sobre os canais de lançamento, consulte Visão geral dos canais [de atualização do Microsoft 365 Apps para empresas.](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)
  
Para a versão atual dos clientes em diferentes canais, confira Informações de versão das atualizações do [Microsoft 365 Apps para empresas.](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Considerações de capacidade do Cloud Connector com bypass de mídia

Sem bypass de mídia — e dependendo do hardware — um dispositivo do Cloud Connector pode lidar com chamadas simultâneas de 50 a 500 que exigem mídia para percorrer um Servidor de Mediação. Para obter mais informações, [consulte Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
Com o bypass de mídia habilitado, os clientes internos na versão suportada não usam o Servidor de Mediação, portanto, o número de clientes internos pode aumentar significativamente. 
  
Conforme mencionado acima, clientes externos ou clientes sem suporte usarão a Borda do Cloud Connector e os servidores de Mediação para mídia. Ao calcular quantos dispositivos do Cloud Connector devem ser colocados em um site, você deve considerar o tráfego de usuários externos e usuários em clientes sem suporte.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>O Cloud Connector dá suporte ao modo Sempre Ignorar

O Cloud Connector dá suporte somente ao modo Sempre Ignorar. Em ambientes locais, há duas opções: Sempre Ignorar e Usar Informações do Site e da Região.
  
Sempre ignorar significa que o bypass de mídia será tentado para todas as chamadas PSTN com clientes internos como um ponto de origem ou de destino. Para determinar se o cliente é interno ou externo, um site na máquina virtual do servidor de mediação é usado. Se o cliente puder alcançar o site, ele será considerado interno e o bypass de mídia será usado. Se o cliente não conseguir alcançar o site (por exemplo, o cliente está em uma rede local), o bypass de mídia não será usado. 
  
Sempre ignorar requer conectividade desobstruída entre os usuários e os gateways PSTN dentro de um site PSTN. 
  
Para obter mais informações, [consulte Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
Por exemplo, no diagrama abaixo, os usuários da Europa devem estar bem conectados aos três SBCs (Controladores de Borda de Sessão) em Amsterdã, enquanto os usuários do Oeste dos EUA devem estar bem conectados aos dois SBCs em Seattle. Bem conectados significa que eles estão localizados nos mesmos sites de rede que os SBCs ou gateways ou em links WAN com largura de banda adequada.
  
![Capacidade do Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Se um usuário de Zurique viaja para o escritório de Seattle e você deseja usar a rede interna para fornecer tráfego de mídia entre o usuário em viagem e gateways na Europa (em vez de passar pela Internet), você deve certificar-se de que o escritório de Seattle e o escritório de Amsterdã onde os SBCs europeus ou gateways estão localizados se qualificam como bem conectados. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs usados no bypass de mídia

Com o bypass de mídia habilitado, o tráfego de mídia entre um cliente e um SBC ou gateway usa o codec G.711. 
  
## <a name="see-also"></a>Confira também

[Implantar bypass de mídia no Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
