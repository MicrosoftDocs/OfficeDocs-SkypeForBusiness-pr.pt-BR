---
title: Configurar as definições globais do bypass de mídia no Skype for Business Server para usar as informações do site e da região
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configure o bypass de mídia para ser usado apenas para determinados sites e regiões no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 3bfb3dca6e53316d5c1de71abad976ae9223c787
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240041"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurar as definições globais do bypass de mídia no Skype for Business Server para usar as informações do site e da região
 
Configure o bypass de mídia para ser usado apenas para determinados sites e regiões no Skype for Business Server Enterprise Voice. 
  
 Se você usar as etapas neste tópico para definir configurações globais para bypass de mídia, pressupõe-se que você não tenha uma boa conectividade entre todos os pontos de extremidade do Skype for Business e qualquer ponto para o qual você configurou o bypass de mídia na conexão do tronco.
  
> [!NOTE]
> As informações de região de rede e de site de rede são compartilhadas entre os recursos avançados do Enterprise Voice de controle de admissão de chamadas e de desvio de mídia quando os dois estão habilitados. Portanto, se você já configurou o controle de admissão de chamadas, não é preciso usar o procedimento a seguir para editar as informações do site e da região especificamente para o bypass de mídia. Siga as etapas neste procedimento se você ainda não tiver configurado as regiões e os sites de rede quanto ao controle de admissão de chamadas e se quiser alterar as configurações do bypass de chamada. 
  
Para que o bypass de mídia funcione corretamente, deve haver consistência entre um site conforme definido no construtor de topologias e conforme é definido quando você configura regiões de rede e sites de rede. Por exemplo, se você tiver um site de ramificação que você definiu no construtor de topologias como tendo apenas um gateway PSTN implantado, esse site de filial deve ser configurado com uma política de voz empresarial que permita que os usuários do site de filial tenham suas chamadas PSTN roteadas por meio da PSTN Gateway no site da filial.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Para configurar informações de site e de região para bypass de mídia

1. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
2. Na barra de navegação esquerda, clique em **Configuração de rede**.
    
3. Dê dois cliques na configuração **Global** na tabela.
    
4. Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar bypass de mídia**.
    
5. Clique em **Usar as configurações de sites e região**.
    
6. Se necessário, marque a caixa de seleção **Habilitar bypass de mídia para sites não mapeados**.
    
    > [!NOTE]
    > Marque essa caixa de seleção somente se você tiver um ou mais sites grandes associados na mesma região e que não possuem restrições de largura de banda (por exemplo, um grande site central), mas também tem sites de filial associados à mesma região e que possuem restrições de largura de banda. Ao habilitar o bypass para sites não mapeados, a configuração é simplificada de forma que você especifica apenas as sub-redes associadas com os sites de filial em vez de precisar especificar todas as sub-redes associadas com todos os sites. Recomendamos que você não marque essa caixa de seleção se o controle de admissão de chamadas estiver habilitado. 
  
7. Clique em **Confirmar**.
    
Em seguida, adicione sub-redes ao site da rede, conforme descrito em [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). Depois que você associar todas as sub-redes aos locais de rede, a implantação do bypass de mídia estará completa.
> [!IMPORTANT]
> Se ainda não tiverem sido criadas as regiões e os sites de rede, é preciso criá-los antes de prosseguir com a implantação do bypass de mídia. Para obter detalhes, consulte [implantar regiões de rede, sites e sub-redes no Skype for Business](deploy-network.md). 
  
## <a name="see-also"></a>Confira também

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

