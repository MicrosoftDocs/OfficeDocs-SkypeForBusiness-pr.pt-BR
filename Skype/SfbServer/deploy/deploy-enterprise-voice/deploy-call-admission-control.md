---
title: Implantar o controle de admissão de chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: O controle de admissão de chamadas é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836881"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Implantar o controle de admissão de chamadas no Skype for Business Server
 
O controle de admissão de chamadas é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas. Para obter mais informações, [consulte Planejar o controle de admissão de chamadas no Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
### <a name="to-deploy-call-admission-control"></a>Para implantar o Controle de Admissão de Chamada

1.  Reúna todas as informações necessárias para sua topologia de rede corporativa, conforme descrito em Exemplo: Coletando requisitos para o controle de admissão de chamadas no [Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
    
2. Se você ainda não tiver feito isso, deverá definir regiões de rede e sites e associar sub-redes a sites de rede. Para obter detalhes, [consulte Implantar regiões de rede, sites e sub-redes no Skype for Business.](deploy-network.md)
    
3. Criar perfis de política de largura de banda, conforme detalhado em [Criar perfis de](create-bandwidth-policy-profiles.md) política de largura de banda no Skype for Business Server
    
4. Crie links de região de rede, conforme detalhado em [Criar links de região de rede no Skype for Business Server.](create-network-region-links.md)
    
5. Crie rotas entre regiões de rede, conforme detalhado em Criar rotas [entre regiões de rede no Skype for Business Server.](create-network-interregional-routes.md)
    
6. Crie políticas entre locais de rede, conforme detalhado em [Criar políticas entre locais de rede no Skype for Business Server.](create-network-intersite-policies.md)
    
7. Habilitar o controle de admissão de chamadas, conforme detalhado em [Habilitar o controle de admissão de chamadas no Skype for Business Server.](enable-call-admission-control.md)
    
8. Verifique algumas configurações finais, para garantir que tudo está definido corretamente. Para obter detalhes, consulte [Implantação do controle de admissão de chamadas: lista de verificação final do Skype for Business Server.](final-checklist.md)
    

