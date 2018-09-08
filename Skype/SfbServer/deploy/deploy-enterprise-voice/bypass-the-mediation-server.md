---
title: Configurar o bypass de mídia no Skype para Business Server para sempre ignorar o servidor de mediação
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilite bypass de mídia para sempre ignorar o servidor de mediação no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 2671a4df1b7c068e650cba35be6409f97b8682f8
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881851"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurar o bypass de mídia no Skype para Business Server para sempre ignorar o servidor de mediação
 
Habilite bypass de mídia para sempre ignorar o servidor de mediação no Skype para Business Server Enterprise Voice. 
  
 Se você usar as etapas deste tópico para definir as configurações globais para o media bypass, pressupõe-se que você tem boa conectividade entre Skype para pontos de extremidade de negócios e qualquer ponto para o qual você configurou o desvio de mídia na conexão do tronco.
  
Se você não tem boa conectividade entre Skype para pontos de extremidade de negócios e todos os pares para o servidor de mediação cujas conexões de tronco respectivos tiverem sido habilitados para bypass de mídia, você deve configurar as definições de desvio de mídia global para usar as informações do site e da região Quando desvio de mídia empregando. Isso permite que mais controle na determinação quando a mídia ignora o servidor de mediação. Para fazer isso, use as etapas em [configurações globais no Skype para Business Server usem informações de site e a região de bypass de mídia de configurar](use-site-and-region-information.md) e [associar uma sub-rede a um site de rede](deploy-network.md#BKMK_AssociateSubnets) .
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação

1. Abra o Skype para painel de controle do servidor de negócios.
    
2. Na barra de navegação esquerda, clique em **Configuração de rede**.
    
3. Clique duas vezes na configuração **Global** na lista.
    
4. Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.
    
5. Clique em **Sempre desviar**.
    
6. Clique em **Confirmar**.
    
## <a name="see-also"></a>Consulte também

[Planejar o bypass de mídia no Skype para negócios](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Implantar o bypass de mídia no Skype para Business Server](deploy-media-bypass.md)

