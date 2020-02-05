---
title: Configurar o bypass de mídia no Skype for Business Server para sempre ignorar o servidor de mediação
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilite o bypass de mídia para sempre ignorar o servidor de mediação no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: cde2a1bff41016e05ac6c74978fa65b45f11a1e7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768264"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurar o bypass de mídia no Skype for Business Server para sempre ignorar o servidor de mediação
 
Habilite o bypass de mídia para sempre ignorar o servidor de mediação no Skype for Business Server Enterprise Voice. 
  
 Se você usar as etapas neste tópico para definir configurações globais para bypass de mídia, pressupõe-se que você tenha uma boa conectividade entre pontos de extremidade do Skype for Business e qualquer ponto para o qual você configurou a mídia ignorada na conexão do tronco.
  
Se você não tiver uma boa conectividade entre os pontos de extremidade do Skype for Business e todos os pares do servidor de mediação cujas conexões de tronco foram habilitadas para bypass de mídia, você deve configurar as definições de bypass de mídia global para usar as informações do site e da região ao empregar o bypass de mídia. Isso permite que você tenha mais controle ao determinar quando a mídia ignora o servidor de mediação. Para fazer isso, use as etapas em [configurar as configurações globais do bypass de mídia no Skype for Business Server para usar as informações de site e região](use-site-and-region-information.md) e [associar uma sub-rede a um site de rede](deploy-network.md#BKMK_AssociateSubnets) em vez disso.
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação

1. Abra o painel de controle do Skype for Business Server.
    
2. Na barra de navegação esquerda, clique em **Configuração de rede**.
    
3. Clique duas vezes na configuração **Global** na lista.
    
4. Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.
    
5. Clique em **Sempre desviar**.
    
6. Clique em **Confirmar**.
    
## <a name="see-also"></a>Confira também

[Planejar a bypass de mídia no Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Implantar bypass de mídia no Skype for Business Server](deploy-media-bypass.md)

