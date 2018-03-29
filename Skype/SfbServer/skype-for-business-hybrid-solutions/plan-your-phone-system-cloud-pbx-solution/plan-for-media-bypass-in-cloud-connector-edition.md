---
title: Planejar o bypass de mídia no Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Leia este tópico para revisar as considerações de planejamento para implementar o bypass de mídia com a versão 2.0 do Cloud Connector Edition e posteriores. Para obter informações sobre como implantar o media bypass, consulte Deploy media bypass na nuvem conector Edition.
ms.openlocfilehash: bf659b7ea7b872a09e8c8ce2358c04cde2ba11d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planejar o bypass de mídia no Cloud Connector Edition
 
Leia este tópico para revisar as considerações de planejamento para implementar o bypass de mídia com a versão 2.0 do Cloud Connector Edition e posteriores. Para obter informações sobre como implantar o media bypass, consulte [o bypass de mídia de implantar na nuvem conector Edition](deploy-media-bypass-in-cloud-connector.md).
  
Bypass de mídia permite que um cliente enviar mídia diretamente para o próximo salto de rede de telefônica pública comutada (PSTN) — um gateway ou controlador de borda de sessão (SBC) — e eliminar o componente de edição do conector de nuvem do caminho de mídia.
  
O bypass de mídia pode aprimorar a qualidade da voz reduzindo a latência, a possibilidade de perda de pacotes e o número de pontos de falha possíveis. Eliminação da mídia de processamento de chamadas ignoradas reduz a carga no conector de nuvem, que permite que um número maior de chamadas simultâneas, e pode melhorar a escalabilidade. 
  
 Dispensando o conector de nuvem de tarefas de processamento de mídia pode reduzir o número de aparelhos de conector de nuvem que uma infraestrutura exige, portanto, você deve habilitar o bypass de mídia sempre que possível.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Como o bypass de mídia afeta os caminhos de sinalização e mídia

Embora a sinalização pegue o mesmo caminho com ou sem bypass de mídia, o fluxo de mídia será diferente. Os seguintes diagramas mostram caminhos de sinalização e mídia em topologias com e sem bypass de mídia.  
  
Por exemplo, nesta topologia — que não o utilizam media bypass — um Skype para o cliente de negócios faz uma chamada PSTN para um número externo, a sinalização SIP vai para o Office 365 e Office 365, em seguida, direciona o tráfego de sinalização de acordo com a voz do usuário final política. Para usuários do conector de nuvem, a política de voz direciona o tráfego de sinalização para o servidor de borda de conector de nuvem, que encaminha o tráfego de sinalização para um controlador de borda de sessão (SBC) PSTN ou gateway através do servidor de mediação de conector de nuvem. Mídia flui do Skype para o cliente de negócios para o servidor de mediação do conector de nuvem e depois para o SBC ou gateway, conforme mostrado no diagrama a seguir:
  
**Bypass de mídia e sinalização básicos sem mídia**

![Sinalizando Sem Bypass de Mídia](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Uma chamada de entrada de PSTN usa o mesmo caminho de sinalização na direção inversa. Para usuários internos, mídia fluirá ainda basicamente entre o Skype para o cliente de negócios e o servidor de mediação do conector de nuvem e o SBC ou gateway.
  
Na topologia da próxima — que utilizam media bypass — sinalização leva o mesmo caminho, mas a mídia fluirá diretamente entre o Skype para Business client e o SBC ou gateway, conforme mostrado no diagrama a seguir:
  
**Bypass de mídia e sinalização básicos com mídia**

![Sinalizando Com Bypass de Mídia](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Cenário de vários sites e bypass de mídia

Bypass de mídia também é útil quando você deseja fornecer serviços de telefonia para vários sites usando um único appliance de conector de nuvem. Porque o conector de nuvem não é possível rotear chamadas com base em números de origem ou de destino, a maioria das empresas implantar um SBC ou gateway por trás de conector de nuvem para tomar decisões de roteamento. O bypass de mídia nesse cenário elimina o salto entre o cliente e o SBC ou o gateway central, conforme mostrado no seguinte diagrama:
  
**Aplicativo de vários local**

![Exemplo de multissite do Cloud Connector](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Flui o tráfego SIP do usuário em Zurique para o Office 365.
    
2. O tráfego, em seguida, encaminha para o aparelho de conector de nuvem em Amsterdã conforme especificado na política de roteamento de voz do usuário.
    
3. O aparelho de conector de nuvem em Amsterdã envia o tráfego SIP para o gateway central na Amsterdã.
    
4. O gateway central na Amsterdã torna as decisões de roteamento apropriadas e envia o tráfego para um SBC ou gateway na Zurique, enquanto os fluxos de mídia diretamente entre o Skype para o cliente de negócios e SBC ou gateway na Amsterdã.
    
 Essa abordagem permite fazer mais usuários por uma implantação do conector de nuvem em que o conector de nuvem é centralizado. Embora o conector de nuvem é eliminado do caminho de mídia, em um cenário de multi-site centralizado mídia poderá ainda atravessar WAN duas vezes, conforme necessário para fluir através do gateway ou do SBC centralizado.
  
Se um cliente estiver fora da rede corporativa, colocar uma chamada de saída, o tráfego de mídia flui através dos servidores de borda e mediação de link de conector de nuvem e WAN entre Zurique e Amsterdã, conforme mostrado no diagrama a seguir:
  
![Exemplo 2 de multissite do Cloud Connector](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Clientes compatíveis com o bypass de mídia

Com a primeira versão do bypass de mídia, o único cliente com suporte é o Skype para negócios 2016 Windows cliente que faz parte do Office 365 ProPlus, versão 16.0.7870.2020 ou posterior. Os clientes podem usar qualquer canal: Atual, Adiado ou Primeiro Lançamento Adiado. 
  
> [!NOTE]
> Se você estiver usando uma solução de VPN cliente em combinação com o cliente Skype for Business, o bypass de mídia só será compatível com uma configuração de túnel dividido de VPN. 
  
Para obter mais informações sobre os canais de versão, consulte [Overview of canais de atualização do Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Para a versão de lançamento atual dos clientes no canais diferentes, consulte o [canal de versões de atualização de cliente do Office 365](https://technet.microsoft.com/en-us/office/mt465751.aspx). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Considerações de capacidade do Cloud Connector com bypass de mídia

Sem bypass de mídia — e de acordo com o hardware — um aparelho de conector de nuvem pode manipular de 50 a 500 chamadas simultâneas que exigem a mídia para viajam através de um servidor de mediação. Para obter mais informações, consulte [Planejar Skype para o conector de nuvem Business Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Com o bypass de mídia habilitado, os clientes internos na versão com suporte não usam o Servidor de Mediação. Portanto, o número de clientes internos pode aumentar significativamente. 
  
Conforme observado anteriormente, os clientes externos ou não há suporte para clientes usarão os servidores de borda de conector de nuvem e mediação para a mídia. Ao calcular quantos dispositivos de conector de nuvem devem ser colocados em um site, você deve considerar o tráfego de usuários externos e os usuários nos clientes sem suporte.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>O Cloud Connector é compatível com o modo Sempre ignorar

Conector de nuvem suporta somente no modo desviar sempre. Em ambientes locais, existem duas opções: Sempre Ignorar e Usar informações do Site e da Região.
  
Sempre ignorar significa que o bypass de mídia será tentado para todas as chamadas PSTN com clientes internos como ponto de origem ou de destino. Para determinar se o cliente é interno ou externo, usa-se um site na máquina virtual do servidor de mediação. Se o cliente conseguir acessar o site, ele será considerado interno e o bypass de mídia será usado. Se o cliente não conseguir acessar o site (por exemplo, o cliente está em uma rede doméstica), o bypass de mídia não será usado.  
  
Sempre Ignorar requer uma conectividade livre entre os usuários e os gateways PSTN dentro de um local de PSTN. 
  
Para obter mais informações, consulte [Planejar Skype para o conector de nuvem Business Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Por exemplo, no diagrama a seguir, os usuários da Europa devem estar bem conectados para os três controladores de borda de sessão (SBCs) no Amsterdã enquanto usuários conosco Oeste devem ser bem conectados para os dois SBCs em Seattle. Bem conectados significa que eles estão localizados quer nos mesmos sites da rede que os SBCs ou gateways, quer em conexões WAN com banda larga adequada.
  
![Capacidade do Cloud Connector](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Se um usuário de Zurique viajar para o escritório de Seattle e você quiser usar a rede interna para entregar o tráfego de mídia entre o usuário viajante e os gateways na Europa (ao invés de ir pela Internet), você deverá se certificar de que o escritório de Seattle e o escritório de Amsterdã, onde os SBCs europeus ou os gateways estão localizados, são considerados bem conectados. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs utilizados no bypass de mídia

Com o bypass de mídia habilitado, o tráfego de mídia entre um cliente e um SBC ou gateway usa o codec G.711. 
  
## <a name="see-also"></a>Consulte também

#### 

[Implantar o bypass de mídia na nuvem conector Edition](deploy-media-bypass-in-cloud-connector.md)

