---
title: Implantar o controle de admissão de chamada Skype for Business Server
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: O controle de admissão de chamadas é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.
ms.openlocfilehash: f7d813d85a3c3eadd770c1dc939358506c230d44
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861898"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Implantar o controle de admissão de chamada Skype for Business Server
 
O controle de admissão de chamadas é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas. Para obter mais informações, [consulte Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Para implantar o Controle de Admissão de Chamada

1.  Reúna todas as informações necessárias para sua topologia de rede corporativa, conforme descrito em [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Se você ainda não fez isso, defina regiões de rede e sites e associe sub-redes a sites de rede. Para obter detalhes, [consulte Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).
    
3. Criar perfis de política de largura de banda, conforme detalhado em [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)
    
4. Criar links de região de rede, conforme detalhado em Criar links de região de [rede em Skype for Business Server](create-network-region-links.md).
    
5. Criar rotas entre regiões de rede, conforme detalhado em [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).
    
6. Criar políticas de intersite de rede, conforme detalhado em [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).
    
7. Habilitar o controle de admissão de chamada, conforme detalhado em [Habilitar controle de](enable-call-admission-control.md)admissão de chamada em Skype for Business Server .
    
8. Verifique algumas configurações finais, para garantir que tudo está definido corretamente. Para obter detalhes, consulte [Implantação de controle de admissão de chamada: lista de verificação final para Skype for Business Server](final-checklist.md).
    

