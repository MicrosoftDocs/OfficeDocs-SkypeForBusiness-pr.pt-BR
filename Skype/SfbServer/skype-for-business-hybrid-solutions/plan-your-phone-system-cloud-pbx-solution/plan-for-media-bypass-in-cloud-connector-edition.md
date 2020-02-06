---
title: Planejar o bypass de mídia no Cloud Connector Edition
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
description: Leia este tópico para revisar as considerações de planejamento para implementar o bypass de mídia com a versão 2.0 do Cloud Connector Edition e posteriores. Para obter informações sobre a implantação do bypass de mídia, consulte Implantar bypass de mídia na nuvem Connector Edition.
ms.openlocfilehash: 67598cbe31dac074bf360ba6fe1462544fe12c5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814489"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planejar o bypass de mídia no Cloud Connector Edition
 
Leia este tópico para revisar as considerações de planejamento para implementar o bypass de mídia com a versão 2.0 do Cloud Connector Edition e posteriores. Para obter informações sobre a implantação do bypass de mídia, consulte [implantar bypass de mídia na nuvem Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da rede telefônica pública comutada (PSTN), um gateway ou um controlador de borda de sessão (SBC), e elimine o componente da edição do conector de nuvem do caminho de mídia.
  
O bypass de mídia pode aprimorar a qualidade da voz reduzindo a latência, a possibilidade de perda de pacotes e o número de pontos de falha possíveis. A eliminação do processamento de mídia para chamadas ignoradas reduz a carga no conector de nuvem, o que permite um número maior de chamadas simultâneas e pode melhorar a escalabilidade. 
  
 Liberar o conector de nuvem de tarefas de processamento de mídia pode reduzir o número de dispositivos de conector de nuvem que uma infraestrutura requer, portanto, você deve habilitar o bypass de mídia sempre que possível.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Como o bypass de mídia afeta os caminhos de sinalização e mídia

Embora a sinalização pegue o mesmo caminho com ou sem bypass de mídia, o fluxo de mídia será diferente. Os seguintes diagramas mostram caminhos de sinalização e mídia em topologias com e sem bypass de mídia.  
  
Por exemplo, na topologia a seguir, que não emprega o bypass de mídia, um cliente Skype for Business coloca uma chamada PSTN em um número externo, a sinalização SIP vai para o Office 365 e o Office 365 direciona o tráfego de sinalização de acordo com a voz do usuário final regras. Para os usuários do conector de nuvem, a política de voz direciona o tráfego de sinalização para o servidor de borda do conector de nuvem, que então roteia o tráfego de sinalização para um controlador de borda de sessão PSTN (SBC) ou Gateway por meio do servidor de mediação do conector de nuvem. O fluxo de mídia do cliente Skype for Business para o servidor de mediação do conector de nuvem e, em seguida, ao gateway ou SBC, conforme mostrado no diagrama a seguir:
  
**Caminhos de sinalização e mídia sem o bypass de mídia**

![Sinalizar sem bypass de mídia](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Uma chamada de entrada de PSTN usa o mesmo caminho de sinalização na direção inversa. Para usuários internos, a mídia ainda vai fluir entre o cliente Skype for Business e o servidor de mediação do conector de nuvem e, em seguida, o SBC ou o gateway.
  
Na próxima topologia, que emprega o bypass de mídia – a sinalização usa o mesmo caminho, mas a mídia flui diretamente entre o cliente Skype for Business e o SBC ou o gateway, conforme mostrado no diagrama a seguir:
  
**Caminhos de sinalização e mídia com o bypass de mídia**

![sinalizar com bypass de mídia](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Cenário de vários sites e bypass de mídia

O bypass de mídia também é útil quando você deseja fornecer serviços de telefonia a vários sites usando um único aparelho de conector de nuvem. Como o conector de nuvem não pode encaminhar chamadas com base nos números de origem ou de destino, a maioria das empresas implanta um SBC ou gateway atrás do conector de nuvem para fazer decisões de roteamento. O bypass de mídia nesse cenário elimina o salto entre o cliente e o SBC ou o gateway central, conforme mostrado no seguinte diagrama:
  
**Aplicativo multissite**

![Exemplo de multissite do conector de nuvem](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. O tráfego SIP flui do usuário em Zurique para o Office 365.
    
2. O tráfego então roteia para o aparelho do conector de nuvem em Amsterdã conforme especificado na política de roteamento de voz do usuário.
    
3. O aparelho do conector de nuvem em Amsterdã envia o tráfego SIP para o gateway central em Amsterdã.
    
4. O gateway central em Amsterdã faz as decisões de roteamento adequadas e, em seguida, envia o tráfego para um SBC ou gateway em Zurique, enquanto a mídia flui diretamente entre o cliente Skype for Business e o SBC ou o gateway em Amsterdã.
    
   Essa abordagem permite atender mais usuários por uma implantação do conector de nuvem onde o conector de nuvem é centralizado. Mesmo que o Cloud Connector seja eliminado do caminho de mídia, em uma mídia de cenário de vários locais centralizado ainda pode atravessar a WAN duas vezes, conforme necessário, para fluir pelo SBC ou gateway centralizado.
  
Se um cliente estiver fora da rede corporativa que está fazendo uma chamada de saída, o tráfego de mídia fluirá pelos servidores de borda e de mediação do conector de nuvem e do link de WAN entre Zurique e Amsterdã, conforme mostrado no diagrama a seguir:
  
![Exemplo de multissite do conector de nuvem 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clientes compatíveis com o bypass de mídia

Com o primeiro lançamento do bypass de mídia, o único cliente com suporte é o cliente do Skype for Business 2016 do Windows que faz parte do Office 365 ProPlus, versão 16.0.7870.2020 ou superior. Os clientes podem usar qualquer canal: Atual, Adiado ou Primeiro Lançamento Adiado. 
  
> [!NOTE]
> Se você estiver usando uma solução de VPN cliente em combinação com o cliente Skype for Business, o bypass de mídia só será compatível com uma configuração de túnel dividido de VPN. 
  
Para obter mais informações sobre os canais de lançamento, consulte [visão geral dos canais de atualização do Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Para a versão de lançamento atual dos clientes em diferentes canais, confira [informações de lançamento para atualizações do Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Considerações de capacidade do Cloud Connector com bypass de mídia

Sem bypass de mídia — e dependendo do hardware — um aparelho de conector de nuvem pode manipular de 50 a 500 chamadas simultâneas que exigem que a mídia se desloque por meio de um servidor de mediação. Para obter mais informações, consulte [planejar o Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Com o bypass de mídia habilitado, os clientes internos na versão com suporte não usam o Servidor de Mediação. Portanto, o número de clientes internos pode aumentar significativamente. 
  
Conforme observado acima, clientes externos ou clientes sem suporte usarão os servidores de borda e mediação do conector de nuvem para mídia. Ao calcular quantos aparelhos de conexão de nuvem devem ser colocados em um site, você deve considerar o tráfego de usuários externos e usuários em clientes sem suporte.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>O Cloud Connector é compatível com o modo Sempre ignorar

O Cloud Connector suporta sempre o modo ignorar. Em ambientes locais, existem duas opções: Sempre Ignorar e Usar informações do Site e da Região.
  
Sempre ignorar significa que o bypass de mídia será tentado para todas as chamadas PSTN com clientes internos como ponto de origem ou de destino. Para determinar se o cliente é interno ou externo, usa-se um site na máquina virtual do servidor de mediação. Se o cliente conseguir acessar o site, ele será considerado interno e o bypass de mídia será usado. Se o cliente não conseguir acessar o site (por exemplo, o cliente está em uma rede doméstica), o bypass de mídia não será usado.  
  
Sempre Ignorar requer uma conectividade livre entre os usuários e os gateways PSTN dentro de um local de PSTN. 
  
Para obter mais informações, consulte [planejar o Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Por exemplo, no diagrama abaixo, os usuários da Europa devem estar bem conectados às três controladoras de borda de sessão (SBCs) em Amsterdã, enquanto os usuários do oeste dos EUA devem estar bem conectados a dois SBCs em Seattle. Bem conectados significa que eles estão localizados quer nos mesmos sites da rede que os SBCs ou gateways, quer em ligações WAN com banda larga adequada.
  
![Capacidade do conector de nuvem](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Se um usuário de Zurique viajar para o escritório de Seattle e você quiser usar a rede interna para entregar o tráfego de mídia entre o usuário viajante e os gateways na Europa (ao invés de ir pela Internet), você deverá se certificar de que o escritório de Seattle e o escritório de Amsterdã, onde os SBCs europeus ou os gateways estão localizados, são considerados bem conectados. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs utilizados no bypass de mídia

Com o bypass de mídia habilitado, o tráfego de mídia entre um cliente e um SBC ou gateway usa o codec G.711. 
  
## <a name="see-also"></a>Confira também

[Implantar o bypass de mídia no Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
