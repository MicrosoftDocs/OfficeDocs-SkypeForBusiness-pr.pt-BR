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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Leia este tópico para revisar considerações de planejamento para implementar o bypass de mídia com o Cloud Connector Edition versão 2.0 e posterior. Para obter informações sobre como implantar o bypass de mídia, consulte Deploy media bypass in Cloud Connector Edition.
ms.openlocfilehash: 182defd3d1fb7acf1fb2ba6fcc4e15e88e24a82c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729740"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Plano para bypass de mídia no Cloud Connector Edition
 
Leia este tópico para revisar considerações de planejamento para implementar o bypass de mídia com o Cloud Connector Edition versão 2.0 e posterior. Para obter informações sobre como implantar o bypass de mídia, consulte [Deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da PSTN (Rede Telefônica Pública Comutado), um gateway ou Controlador de Borda de Sessão (SBC) e elimine o componente Cloud Connector Edition do caminho de mídia.
  
O bypass de mídia pode melhorar a qualidade da voz reduzindo a latência, a possibilidade de perda de pacotes e o número de pontos de possível falha. A eliminação do processamento de mídia para chamadas ignoradas reduz a carga no Cloud Connector, que permite um número maior de chamadas simultâneas e pode melhorar a escalabilidade. 
  
 A liberação do Cloud Connector das tarefas de processamento de mídia pode reduzir o número de dispositivos do Cloud Connector que uma infraestrutura exige, portanto, você deve habilitar o bypass de mídia sempre que possível.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Como o bypass de mídia afeta os caminhos de sinalização e mídia

Enquanto a sinalização tem o mesmo caminho com ou sem bypass de mídia, o fluxo de mídia será diferente. Os diagramas a seguir mostram caminhos de mídia e sinalização em topologias com e sem bypass de mídia. 
  
Por exemplo, na topologia a seguir, que não emprega bypass de mídia, um cliente Skype for Business coloca uma chamada PSTN para um número externo, a sinalização SIP vai para Microsoft 365 ou Office 365, que direciona o tráfego de sinalização de acordo com a política de voz do usuário final. Para usuários do Cloud Connector, a política de voz direciona o tráfego de sinalização para o Servidor de Borda do Cloud Connector, que, em seguida, encaminha o tráfego de sinalização para um controlador de borda de sessão PSTN (SBC) ou gateway por meio do Servidor de Mediação do Cloud Connector. A mídia flui do cliente Skype for Business para o Servidor de Mediação do Cloud Connector e, em seguida, para o SBC ou gateway, conforme mostrado no diagrama a seguir:
  
**Caminhos de mídia e sinalização sem bypass de mídia**

![sinalização sem bypass de mídia.](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Uma chamada de entrada da PSTN usa o mesmo caminho de sinalização na direção inversa. Para usuários internos, a mídia ainda fluirá entre o cliente Skype for Business e o Servidor de Mediação do Cloud Connector e, em seguida, o SBC ou gateway.
  
Na próxima topologia, que emprega bypass de mídia, a sinalização segue o mesmo caminho, mas a mídia flui diretamente entre o cliente Skype for Business e o SBC ou gateway, conforme mostrado no diagrama a seguir:
  
**Caminhos de mídia e sinalização com bypass de mídia**

![sinalização com Bypass de Mídia.](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Cenário de vários sites e bypass de mídia

O bypass de mídia também é útil quando você deseja fornecer serviços de telefonia para vários sites usando um único dispositivo do Cloud Connector. Como o Cloud Connector não pode rotear chamadas com base em números de origem ou de destino, a maioria das empresas implanta um SBC ou gateway atrás do Cloud Connector para tomar decisões de roteamento. O desvio de mídia neste cenário elimina o salto entre o cliente e o SBC central ou gateway, conforme mostrado no diagrama a seguir:
  
**Aplicativo multi-site**

![Exemplo de multisite do Cloud Connector.](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. O tráfego SIP flui do usuário em Richrich para Microsoft 365 ou Office 365.
    
2. Em seguida, o tráfego é roteado para o dispositivo Cloud Connector em Amsterdã, conforme especificado na política de roteamento de voz do usuário.
    
3. O dispositivo Cloud Connector em Amsterdã envia o tráfego SIP para o gateway central em Amsterdã.
    
4. O gateway central em Amsterdã toma as decisões de roteamento apropriadas e envia o tráfego para um SBC ou gateway em Zurique, enquanto a mídia flui diretamente entre o cliente Skype for Business e o SBC ou gateway em Amsterdã.
    
   Essa abordagem permite atender a mais usuários por uma implantação do Cloud Connector em que o Cloud Connector está centralizado. Mesmo que o Cloud Connector seja eliminado do caminho de mídia, em uma mídia de cenário multi site centralizada ainda pode percorrer a WAN duas vezes conforme necessário para fluir pelo SBC centralizado ou gateway.
  
Se um cliente estiver fora da rede corporativa fazendo uma chamada de saída, o tráfego de mídia fluirá por meio dos servidores de Borda e Mediação do Cloud Connector e do link WAN entre Zurique e Amsterdã, conforme mostrado no diagrama a seguir:
  
![Cloud Connector Multisite Exemplo 2.](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clientes com suporte para bypass de mídia

Com a primeira versão do bypass de mídia, o único cliente com suporte é o cliente Skype for Business 2016 Windows que faz parte do Microsoft 365 Apps para Grandes Empresas, versão 16.0.7870.2020 ou superior. Os clientes podem usar qualquer canal: Current, Deferred ou First Release Adiado. 
  
> [!NOTE]
> Se você estiver usando uma solução VPN do cliente em combinação com o cliente Skype for Business, o bypass de mídia só será suportado com uma configuração de túnel dividido vpn. 
  
Para obter mais informações sobre os canais de lançamento, consulte [Overview of update channels for Microsoft 365 Apps para Grandes Empresas](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Para a versão atual dos clientes em diferentes canais, consulte Informações de versão [para atualizações para Microsoft 365 Apps para Grandes Empresas](/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Considerações sobre a capacidade do Cloud Connector com bypass de mídia

Sem bypass de mídia e, dependendo do hardware, um dispositivo do Cloud Connector pode manipular de 50 a 500 chamadas simultâneas que exigem que a mídia viaje através de um Servidor de Mediação. Para obter mais informações, [consulte Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md). 
  
Com o bypass de mídia habilitado, os clientes internos na versão com suporte não usam o Servidor de Mediação, portanto, o número de clientes internos pode aumentar significativamente. 
  
Conforme mencionado acima, clientes externos ou clientes sem suporte usarão os servidores de Borda e Mediação do Cloud Connector para mídia. Ao calcular quantos dispositivos do Cloud Connector devem ser colocados em um site, você deve considerar o tráfego de usuários externos e usuários em clientes sem suporte.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>O Cloud Connector dá suporte ao modo Sempre Ignorar

O Cloud Connector dá suporte somente ao modo Sempre Ignorar. Em ambientes locais, há duas opções: Sempre Ignorar e Usar Informações de Site e Região.
  
Sempre Ignorar significa que o bypass de mídia será tentado para todas as chamadas PSTN com clientes internos como uma origem ou ponto de destino. Para determinar se o cliente é interno ou externo, um site na máquina virtual do servidor de mediação é usado. Se o cliente puder alcançar o site, ele será considerado interno e o bypass de mídia será usado. Se o cliente não puder alcançar o site (por exemplo, o cliente está em uma rede local), o bypass de mídia não será usado. 
  
Sempre Ignorar requer conectividade desobstruída entre usuários e os gateways PSTN em um Site PSTN. 
  
Para obter mais informações, [consulte Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md). 
  
Por exemplo, no diagrama abaixo, os usuários da Europa devem estar bem conectados aos três Controladores de Borda de Sessão (SBCs) em Amsterdã, enquanto os usuários do Oeste dos EUA devem estar bem conectados aos dois SBCs em Seattle. Bem conectado significa que eles estão localizados nos mesmos sites de rede que os SBCs ou gateways, ou por meio de links WAN com largura de banda adequada.
  
![Capacidade do Cloud Connector.](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Se um usuário de Richrich viajar para o escritório de Seattle e você quiser usar a rede interna para fornecer tráfego de mídia entre o usuário em viagem e gateways na Europa (em vez de passar pela Internet), você deve garantir que o escritório de Seattle e o escritório de Amsterdã onde os SBCs ou gateways europeus estão localizados se qualificam como bem conectados. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs usados no bypass de mídia

Com o bypass de mídia habilitado, o tráfego de mídia entre um cliente e um SBC ou gateway usa o codec G.711. 
  
## <a name="see-also"></a>Confira também

[Implantar bypass de mídia no Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)