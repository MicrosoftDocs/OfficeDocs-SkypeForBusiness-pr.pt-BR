---
title: Configurar o bypass de mídia Skype for Business Server sempre ignorar o Servidor de Mediação
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilita o bypass de mídia para sempre ignorar o Servidor de Mediação Skype for Business Server Enterprise Voice.
ms.openlocfilehash: c80b3479546e9154480af8f71417b5ebce43b261510eec19332ecf1cf9287bc4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310026"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurar o bypass de mídia Skype for Business Server sempre ignorar o Servidor de Mediação
 
Habilita o bypass de mídia para sempre ignorar o Servidor de Mediação Skype for Business Server Enterprise Voice. 
  
 Se você usar as etapas deste tópico para definir configurações globais para bypass de mídia, a suposição é de que você tem uma boa conectividade entre os pontos de extremidade Skype for Business e qualquer ponto para o qual você configurou o bypass de mídia na conexão de tronco.
  
Se você não tiver uma boa conectividade entre os pontos de extremidade Skype for Business e todos os pares do Servidor de Mediação cujas respectivas conexões de tronco foram habilitadas para bypass de mídia, você deve configurar configurações globais de bypass de mídia para usar informações de site e região ao empregar bypass de mídia. Isso permite maior controle ao determinar quando a mídia desvia do servidor de mediação. Para fazer isso, use as etapas em [Configure media bypass global settings in Skype for Business Server use site](use-site-and-region-information.md) and region information and Associate a [subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação

1. Abra Skype for Business Server Painel de Controle.
    
2. Na barra de navegação da esquerda, clique em **Configuração da Rede**.
    
3. Clique duas vezes na configuração **Global** na lista.
    
4. Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.
    
5. Clique em **Sempre desviar**.
    
6. Clique em **Comprometer**.
    
## <a name="see-also"></a>Confira também

[Planejar o bypass de mídia Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Implantar bypass de mídia Skype for Business Server](deploy-media-bypass.md)

