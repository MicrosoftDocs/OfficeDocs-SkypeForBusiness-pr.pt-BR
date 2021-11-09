---
title: Implantar bypass de mídia Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Implante o bypass de mídia Skype for Business Server Enterprise Voice. Inclui pré-requisitos e lista de verificação do processo de implantação.
ms.openlocfilehash: c5699d1116faa6bc3b8ae0178ec617bcf06c1ef4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834689"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Implantar bypass de mídia Skype for Business Server
 
Implante o bypass de mídia Skype for Business Server Enterprise Voice. Inclui pré-requisitos e lista de verificação do processo de implantação.
  
Este tópico supõe que você já tenha publicado e configurado pelo menos um ou mais Servidores de Mediação e pelo menos um par de gateway para fornecer conectividade PSTN. Para obter mais detalhes sobre essas tarefas, consulte [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md) and Define a gateway in [Topology Builder in Skype for Business Server](define-a-gateway.md).
  
 Se o par ao qual você se conectar for o SBC de um provedor de tronco SIP, certifique-se de que o provedor é um provedor qualificado e que o provedor dá suporte ao bypass de mídia. Por exemplo, vários provedores de tronco SIP permitirão que seu SBC receba tráfego do Servidor de Mediação. Caso sim, o bypass não deve ser habilitado para o tronco em questão. Além disso, não é possível habilitar o bypass de mídia a não ser que sua organização releve seus endereços IP de rede internos para o provedor de tronco SIP.
  
> [!NOTE]
> O bypass de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e fez alguns testes com o Cisco IP-PBXs. O bypass de mídia só é suportado com produtos e versões listados no Programa de Interoperabilidade Aberta de Comunicações [Unificadas - Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). 
  
Se você já configurou opcionalmente o controle de admissão de chamada (CAC), outro recurso do Enterprise Voice avançado, observe que a reserva de largura de banda realizada pelo controle de admissão de chamada não é aplicada a qualquer chamada na qual o bypass de mídia é implantado. A verificação se a implantação do bypass de mídia é realizado primeiro e se o bypass de mídia é implantado, o controle de admissão de chamada não é usado para a chamada; apenas se a verificação do bypass de mídia falhar, a verificação é realizada para o controle de admissão de chamada. Os dois recursos são mutuamente exclusivos para qualquer chamada roteada para o PSTN. Esta é a lógica porque o bypass de mídia assume que as restrições de largura de banda não existam entre os pontos de extremidade de mídia em uma chamada; o bypass de mídia não pode ser realizado em links com largura de banda restrita. Como resultado, um dos seguintes serão aplicados em uma chamada PSTN: a) a mídia ignora o Servidor de Mediação e o controle de admissão de chamada não reserva largura de banda para a chamada; ou b) o controle de admissão de chamada aplica a reserva de banda larga para a chamada e a mídia é processada pelo Servidor de Mediação envolvido na chamada.
  
Além de habilitar o bypass de mídia para conexões individuais de tronco associadas a um par, você deve também habilitá-lo globalmente. As configurações de bypass de mídia global podem especificar que o bypass de mídia sempre é tentado para chamadas para a PSTN ou que o bypass de mídia é empregado usando o mapeamento de sub-redes para sites de rede e regiões de rede, semelhante ao que é feito pelo controle de admissão de chamadas, outro recurso avançado de voz. Quando o bypass de mídia e o controle de admissão de chamada estão habilitados, as informações da região de rede, do site de rede e da sub-rede especificadas para o controle de admissão de chamada são usadas automaticamente ao determinar se é necessário empregar o bypass de mídia. Isso significa que você não pode especificar que o bypass de mídia sempre é tentado para chamadas para a PSTN quando o controle de admissão de chamadas está habilitado.
  
> [!NOTE]
> Ao usar estas etapas para configurar o bypass de mídia, pressupõe-se que você possui uma boa conectividade entre os clientes e o par do Servidor de Mediação (por exemplo, um gateway PSTN, um IP-PBX, ou um SBC em um provedor de tronco SIP). Se houver qualquer limitação de largura de banda no link, o bypass de mídia não poderá ser aplicado na chamada. O bypass de mídia não interopera com todos os gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e fez alguns testes com o Cisco IP-PBXs. O bypass de mídia só é suportado com produtos e versões listados no Programa de Interoperabilidade Aberta de Comunicações [Unificadas - Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). 
  
## <a name="deployment-process-for-media-bypass"></a>Processo de implantação para bypass de mídia

A tabela a seguir fornece uma visão geral do processo de implantação de bypass de mídia. 
  
|**Fase**|**Etapas**|**Funções**|**Documentação de Implantação**|
|:-----|:-----|:-----|:-----|
|Configurar troncos para bypass de mídia  <br/> |Se você ainda não tiver feito isso, configure um ou mais troncos para bypass de mídia.  <br/> | Um membro do grupo RTCUniversalServerAdmins ou membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurar um tronco com bypass de mídia Skype for Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Configurar o bypass de mídia globalmente  <br/> |Configure o bypass de mídia para todas as chamadas para a PSTN ou determinadas chamadas com base em sites de rede e regiões de rede.  <br/> | Um membro do grupo RTCUniversalServerAdmins ou membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Configurar o bypass de mídia Skype for Business Server sempre ignorar o Servidor de Mediação](bypass-the-mediation-server.md) <br/> [Configurar configurações globais de bypass de mídia Skype for Business Server usar informações de site e região](use-site-and-region-information.md) <br/> |
|Associar sub-redes a sites de rede, se necessário  <br/> |Se você configurar o bypass de mídia para usar informações de site e região, deverá associar as sub-redes de sua implantação a sites e regiões de rede (se ainda não tiver feito isso para outro recurso de voz).)  <br/> | Um membro do grupo RTCUniversalServerAdmins ou membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator <br/> |[Associar uma sub-rede a um site de rede](deploy-network.md#BKMK_AssociateSubnets) <br/> |
