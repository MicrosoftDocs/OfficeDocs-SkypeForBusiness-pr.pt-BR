---
title: Implantar o controle de admissão de chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.
ms.openlocfilehash: 7f7f8dee4e25061533564ce517f797281bef042e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280436"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Implantar o controle de admissão de chamadas no Skype for Business Server
 
O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas. Para obter mais informações, consulte [planejar o controle de admissão de chamadas no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Para implantar o Serviço de Controle de Admissão de Chamadas

1.  Reúna todas as informações necessárias para a topologia de rede da sua empresa, conforme descrito no [exemplo: coletando requisitos para controle de admissão de chamadas no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Se você não tiver feito isso, você deve definir as regiões e os sites da rede e associar sub-redes aos sites da rede. Para obter detalhes, consulte [implantar regiões de rede, sites e sub-redes no Skype for Business](deploy-network.md).
    
3. Criar perfis de política de largura de banda, conforme detalhado em [criar perfis de política de largura de banda no Skype for Business Server](create-bandwidth-policy-profiles.md)
    
4. Crie links de região de rede, conforme detalhado em [criar links de região de rede no Skype for Business Server](create-network-region-links.md).
    
5. Crie rotas entre regiões, como detalhado em [criar rotas interregionis de rede no Skype for Business Server](create-network-interregional-routes.md).
    
6. Crie políticas entre sites de rede, conforme detalhado em [criar políticas entre sites de rede no Skype for Business Server](create-network-intersite-policies.md).
    
7. Habilite o controle de admissão de chamadas, conforme detalhado em [habilitar controle de admissão de chamadas no Skype for Business Server](enable-call-admission-control.md).
    
8. Verifique algumas configurações finais para certificar-se de que tudo está definido corretamente. Para obter detalhes, consulte [implantação de controle de admissão de chamadas: lista de verificação final do Skype for Business Server](final-checklist.md).
    

