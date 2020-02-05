---
title: Implantar bypass de mídia no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Implantar bypass de mídia no Skype for Business Server Enterprise Voice. Inclui os pré-requisitos e a lista de verificação do processo de implantação.
ms.openlocfilehash: 744fe56b554bd6b97171798e5dcc7baab69b6dbf
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767534"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Implantar bypass de mídia no Skype for Business Server
 
Implantar bypass de mídia no Skype for Business Server Enterprise Voice. Inclui os pré-requisitos e a lista de verificação do processo de implantação.
  
Este tópico pressupõe que você já publicou e configurou pelo menos um ou mais servidores de mediação e pelo menos um peer de gateway para fornecer conectividade PSTN. Para obter mais detalhes sobre essas tarefas, consulte [implantar um servidor de mediação no construtor de topologias no Skype for Business Server](deploy-a-mediation-server.md) e [definir um gateway no construtor de topologias no Skype for Business Server](define-a-gateway.md).
  
 Se o par ao qual você está se conectando for o SBC de um provedor de tronco SIP, certifique-se de que o provedor seja qualificado e suporte bypass de mídia. Por exemplo, vários provedores de tronco SIP permitirão que seu SBC receba tráfego do Servidor de Mediação. Em caso afirmativo, o bypass não deve ser habilitado para o tronco em questão. Além disso, não é possível habilitar o bypass de mídia, a não ser que sua organização revele seus endereços IP de rede internos para o provedor de tronco SIP.
  
> [!NOTE]
> O bypass de mídia não interoperará com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no [programa de interoperabilidade aberta da comunicação unificada-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Se você já configurou opcionalmente o controle de admissão de chamada (CAC), outro recurso do Enterprise Voice avançado, observe que a reserva de largura de banda realizada pelo controle de admissão de chamada não é aplicada a qualquer chamada na qual o bypass de mídia é implantado. A verificação se a implantação do bypass de mídia é realizada primeiro, e se o bypass de mídia estiver implantado, o controle de admissão de chamada não será usado para a chamada. A verificação será realizada para o controle de admissão de chamada apenas se a verificação do bypass de mídia falhar. Os dois recursos são mutuamente exclusivos para qualquer chamada roteada para o PSTN. Esta é a lógica porque o bypass de mídia assume que as restrições de largura de banda não existem entre os pontos de extremidade de mídia em uma chamada; o bypass de mídia não pode ser realizado em links com largura de banda restrita. Como resultado, um dos seguintes serão aplicados em uma chamada PSTN: a) a mídia ignora o Servidor de Mediação e o controle de admissão de chamada não reserva largura de banda para a chamada; ou b) o controle de admissão de chamada aplica a reserva de banda larga para a chamada e a mídia é processada pelo Servidor de Mediação envolvido na chamada.
  
Além de habilitar o bypass de mídia para conexões individuais de tronco associadas a um par, você deve também habilitá-lo globalmente. As configurações globais de bypass de mídia podem tanto especificar que o bypass de mídia sempre recebe tentativas de chamadas para o PSTN ou que o bypass de mídia é implantado usando o mapeamento de subredes para sites de rede e regiões de rede - similar ao que é feito pelo controle de admissão de chamada, outro recurso de voz avançado. Quando o bypass de mídia e o controle de admissão de chamadas estão ativados a região de rede, o site de rede e as informações da subrede especificadas pelo controle de admissão de chamada são usados automaticamente ao determinar se usam ou não o bypass de mídia. Isso significa que você não pode especificar se o bypass de mídia sempre recebe tentativas de chamada para o PSTN quando o controle de admissão de chamada está ativado.
  
> [!NOTE]
> Ao usar estas etapas para configurar o bypass de mídia, pressupõe-se que você possui uma boa conectividade entre os clientes e o par do Servidor de Mediação (por exemplo, um gateway PSTN, um IP-PBX ou um SBC em um provedor de tronco SIP). Se houver qualquer limitação de largura de banda no link, o bypass de mídia não poderá ser aplicado na chamada. O bypass de mídia não interopera com todos os gateways PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no [programa de interoperabilidade aberta da comunicação unificada-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
## <a name="deployment-process-for-media-bypass"></a>Processo de implantação para bypass de mídia

A tabela a seguir apresenta uma visão geral do processo de implantação do bypass de mídia. 
  
|**Fase**|**Etapas**|**Funções**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Configurar troncos para bypass de mídia  <br/> |Se você ainda não tiver feito isso, configure um ou mais troncos para bypass de mídia.  <br/> | Um membro do grupo RTCUniversalServerAdmins ou um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurar um tronco com bypass de mídia no Skype for Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Configurar bypass de mídia globalmente  <br/> |Configurar bypass de mídia para todas as chamadas para o PSTN ou certas chamadas com base em sites de rede e regiões de rede.  <br/> | Um membro do grupo RTCUniversalServerAdmins ou um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurar o bypass de mídia no Skype for Business Server para sempre ignorar o servidor de mediação](bypass-the-mediation-server.md) <br/> [Configurar as definições globais do bypass de mídia no Skype for Business Server para usar as informações do site e da região](use-site-and-region-information.md) <br/> |
|Associar sub-redes a sites da rede, se necessário  <br/> |Se você configurar o bypass de mídia para usar informações do site e da região, deverá associar as sub-redes de sua implantação a sites e regiões da rede (caso ainda não tenha feito isso para outro recurso de voz).  <br/> | Um membro do grupo RTCUniversalServerAdmins ou um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

