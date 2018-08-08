---
title: Implantar o bypass de mídia no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Implante o bypass de mídia no Skype para Business Server Enterprise Voice. Inclui os pré-requisitos e a lista de verificação do processo de implantação.
ms.openlocfilehash: ead9ebb099bd671dbbc28607bf11e1131ac7569a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965433"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Implantar o bypass de mídia no Skype para Business Server
 
Implante o bypass de mídia no Skype para Business Server Enterprise Voice. Inclui os pré-requisitos e a lista de verificação do processo de implantação.
  
Este tópico pressupõe que você já publicou e configurado pelo menos um ou mais servidores de mediação e o ponto de pelo menos um gateway para fornecer conectividade PSTN. Para obter mais detalhes sobre essas tarefas, consulte [implantar um servidor de mediação no construtor de topologia no Skype para Business Server](deploy-a-mediation-server.md) e [definir um gateway no construtor de topologia no Skype para Business Server](define-a-gateway.md).
  
 Se o par ao qual você está se conectando for o SBC de um provedor de tronco SIP, certifique-se de que o provedor seja qualificado e suporte bypass de mídia. Por exemplo, vários provedores de tronco SIP permitirão que seu SBC receba tráfego do Servidor de Mediação. Em caso afirmativo, o bypass não deve ser habilitado para o tronco em questão. Além disso, não é possível habilitar o bypass de mídia, a não ser que sua organização revele seus endereços IP de rede internos para o provedor de tronco SIP.
  
> [!NOTE]
> O bypass de mídia não interopera com todos os gateways PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e fez alguns testes com IP-PBXs da Cisco. Bypass de mídia é suportado somente com produtos e versões listadas em [Unified Communications programa de interoperabilidade aberta - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Se você já configurou opcionalmente o controle de admissão de chamada (CAC), outro recurso do Enterprise Voice avançado, observe que a reserva de largura de banda realizada pelo controle de admissão de chamada não é aplicada a qualquer chamada na qual o bypass de mídia é implantado. A verificação se a implantação do bypass de mídia é realizada primeiro, e se o bypass de mídia estiver implantado, o controle de admissão de chamada não será usado para a chamada. A verificação será realizada para o controle de admissão de chamada apenas se a verificação do bypass de mídia falhar. Os dois recursos são mutuamente exclusivos para qualquer chamada roteada para o PSTN. Esta é a lógica porque o bypass de mídia assume que as restrições de largura de banda não existem entre os pontos de extremidade de mídia em uma chamada; o bypass de mídia não pode ser realizado em links com largura de banda restrita. Como resultado, um dos seguintes serão aplicados em uma chamada PSTN: a) a mídia ignora o Servidor de Mediação e o controle de admissão de chamada não reserva largura de banda para a chamada; ou b) o controle de admissão de chamada aplica a reserva de banda larga para a chamada e a mídia é processada pelo Servidor de Mediação envolvido na chamada.
  
Além de habilitar o bypass de mídia para conexões individuais de tronco associadas a um par, você deve também habilitá-lo globalmente. As configurações globais de bypass de mídia podem tanto especificar que o bypass de mídia sempre recebe tentativas de chamadas para o PSTN ou que o bypass de mídia é implantado usando o mapeamento de subredes para sites de rede e regiões de rede - similar ao que é feito pelo controle de admissão de chamada, outro recurso de voz avançado. Quando o bypass de mídia e o controle de admissão de chamadas estão ativados a região de rede, o site de rede e as informações da subrede especificadas pelo controle de admissão de chamada são usados automaticamente ao determinar se usam ou não o bypass de mídia. Isso significa que você não pode especificar se o bypass de mídia sempre recebe tentativas de chamada para o PSTN quando o controle de admissão de chamada está ativado.
  
> [!NOTE]
> Ao usar estas etapas para configurar o bypass de mídia, pressupõe-se que você possui uma boa conectividade entre os clientes e o par do Servidor de Mediação (por exemplo, um gateway PSTN, um IP-PBX ou um SBC em um provedor de tronco SIP). Se houver qualquer limitação de largura de banda no link, o bypass de mídia não poderá ser aplicado na chamada. O bypass de mídia não interopera com todos os gateways PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e fez alguns testes com IP-PBXs da Cisco. Bypass de mídia é suportado somente com produtos e versões listadas em [Unified Communications programa de interoperabilidade aberta - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
## <a name="deployment-process-for-media-bypass"></a>Processo de implantação para bypass de mídia

A tabela a seguir apresenta uma visão geral do processo de implantação do bypass de mídia. 
  
|**Fase**|**Etapas**|**Funções**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Configurar troncos para bypass de mídia  <br/> |Se você ainda não tiver feito isso, configure um ou mais troncos para bypass de mídia.  <br/> | Membro do grupo RTCUniversalServerAdmins ou membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurar um tronco com bypass de mídia no Skype para Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Configurar bypass de mídia globalmente  <br/> |Configurar bypass de mídia para todas as chamadas para o PSTN ou certas chamadas com base em sites de rede e regiões de rede.  <br/> | Membro do grupo RTCUniversalServerAdmins ou membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurar o bypass de mídia no Skype para Business Server para sempre ignorar o servidor de mediação](bypass-the-mediation-server.md) <br/> [Configurar as configurações globais de desvio de mídia no Skype para Business Server usem informações de site e da região](use-site-and-region-information.md) <br/> |
|Associar sub-redes a sites da rede, se necessário  <br/> |Se você configurar o bypass de mídia para usar informações do site e da região, deverá associar as sub-redes de sua implantação a sites e regiões da rede (caso ainda não tenha feito isso para outro recurso de voz).  <br/> | Membro do grupo RTCUniversalServerAdmins ou membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

