---
title: Implantar o serviço de controle de admissão de chamadas no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas. Para obter mais informações, consulte Plan para controle de admissão de chamada no Skype for Business Server 2015.
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a>Implantar o serviço de controle de admissão de chamadas no Skype for Business Server 2015
 
O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas. Para obter mais informações, consulte [Planejar o controle de admissão de chamada no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Para implantar o Serviço de Controle de Admissão de Chamadas

1.  Reunir todas as informações necessárias para a sua topologia de rede empresarial, conforme descrito em [exemplo: coletando os requisitos para o controle de admissão de chamada no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Se você não tiver feito isso, você deve definir as regiões e os sites da rede e associar sub-redes aos sites da rede. Para obter detalhes, consulte [Deploy regiões de rede, sites e sub-redes em Skype para negócios 2015](deploy-network.md).
    
3. Criar perfis de política, conforme detalhado no [criar perfis de política de largura de banda em Skype para Business Server 2015](create-bandwidth-policy-profiles.md) de largura de banda
    
4. Crie links de região de rede, conforme detalhado no [criar links de região de rede no Skype para Business Server 2015](create-network-region-links.md).
    
5. Crie rotas de inter-região de rede, conforme detalhado no [criar rotas interregional da rede no Skype para Business Server 2015](create-network-interregional-routes.md).
    
6. Crie políticas entre sites de rede, conforme detalhado no [políticas entre sites de rede de criar no Skype para Business Server 2015](create-network-intersite-policies.md).
    
7. Habilite o controle de admissão de chamada, conforme detalhado no [Habilitar o controle de admissão de chamada no Skype para Business Server 2015](enable-call-admission-control.md).
    
8. Verifique algumas configurações finais para certificar-se de que tudo está definido corretamente. Para obter detalhes, consulte [implantação do controle de admissão de chamada: lista de verificação final do Skype para Business Server 2015](final-checklist.md).
    

