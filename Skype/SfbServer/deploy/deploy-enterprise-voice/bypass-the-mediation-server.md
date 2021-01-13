---
title: Configurar o bypass de mídia no Skype for Business Server para sempre ignorar o Servidor de Mediação
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
description: Habilita o bypass de mídia para sempre ignorar o Servidor de Mediação no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804211"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurar o bypass de mídia no Skype for Business Server para sempre ignorar o Servidor de Mediação
 
Habilita o bypass de mídia para sempre ignorar o Servidor de Mediação no Skype for Business Server Enterprise Voice. 
  
 Se você usar as etapas deste tópico para definir as configurações globais para o bypass de mídia, a suposição é de que você tem uma boa conectividade entre os pontos de extremidade do Skype for Business e qualquer ponto para o qual tenha configurado o bypass de mídia na conexão de tronco.
  
Se você não tiver uma boa conectividade entre os pontos de extremidade do Skype for Business e todos os pontos do Servidor de Mediação cujas respectivas conexões de tronco foram habilitadas para bypass de mídia, você deve definir configurações globais de bypass de mídia para usar informações de site e região ao empregar bypass de mídia. Isso permite maior controle ao determinar quando a mídia desvia do servidor de mediação. Para fazer isso, use as etapas em Configurar definições globais de bypass de mídia no [Skype for Business Server](use-site-and-region-information.md) para usar informações de site e região e associar uma [sub-rede a](deploy-network.md#BKMK_AssociateSubnets) um site de rede.
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação

1. Abra o Painel de Controle do Skype for Business Server.
    
2. Na barra de navegação da esquerda, clique em **Configuração da Rede**.
    
3. Clique duas vezes na configuração **Global** na lista.
    
4. Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.
    
5. Clique em **Sempre desviar**.
    
6. Clique em **Comprometer**.
    
## <a name="see-also"></a>Confira também

[Planejar bypass de mídia no Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Implantar bypass de mídia no Skype for Business Server](deploy-media-bypass.md)

