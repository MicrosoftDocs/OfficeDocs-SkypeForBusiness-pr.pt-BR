---
title: Implantar o controle de admissão de chamada no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.
ms.openlocfilehash: 6ea527bc48f4a61bfe128eb935231200bb88b29f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892759"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Implantar o controle de admissão de chamada no Skype para Business Server
 
O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas. Para obter mais informações, consulte [Planejar o controle de admissão de chamada no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Para implantar o Serviço de Controle de Admissão de Chamadas

1.  Reunir todas as informações necessárias para a sua topologia de rede empresarial, conforme descrito em [exemplo: coletando os requisitos para o controle de admissão de chamada no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Se você não tiver feito isso, você deve definir as regiões e os sites da rede e associar sub-redes aos sites da rede. Para obter detalhes, consulte [Deploy regiões de rede, sites e sub-redes em Skype para negócios](deploy-network.md).
    
3. Criar perfis de política, conforme detalhado no [criar perfis de política de largura de banda em Skype para Business Server](create-bandwidth-policy-profiles.md) de largura de banda
    
4. Crie links de região de rede, conforme detalhado no [criar links de região de rede no Skype para Business Server](create-network-region-links.md).
    
5. Crie rotas de inter-região de rede, conforme detalhado no [criar rotas interregional da rede no Skype para Business Server](create-network-interregional-routes.md).
    
6. Crie políticas entre sites de rede, conforme detalhado no [políticas entre sites de rede de criar no Skype para Business Server](create-network-intersite-policies.md).
    
7. Habilite o controle de admissão de chamada, conforme detalhado no [Habilitar o controle de admissão de chamada no Skype para Business Server](enable-call-admission-control.md).
    
8. Verifique algumas configurações finais para certificar-se de que tudo está definido corretamente. Para obter detalhes, consulte [implantação do controle de admissão de chamada: lista de verificação final do Skype para Business Server](final-checklist.md).
    

