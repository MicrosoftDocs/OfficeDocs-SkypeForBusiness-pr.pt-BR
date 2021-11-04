---
title: Configurar configurações globais de bypass de mídia Skype for Business Server usar informações de site e região
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configure o bypass de mídia a ser usado apenas para determinados sites e regiões no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 2d1c10ce06421635783a50bf97286c8d752f478b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741347"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurar configurações globais de bypass de mídia Skype for Business Server usar informações de site e região
 
Configure o bypass de mídia a ser usado apenas para determinados sites e regiões no Skype for Business Server Enterprise Voice. 
  
 Se você usar as etapas deste tópico para definir configurações globais para bypass de mídia, a suposição é de que você não tem uma boa conectividade entre todos os pontos de extremidade Skype for Business e qualquer ponto para o qual você configurou o bypass de mídia na conexão de tronco.
  
> [!NOTE]
> As informações de região de rede e de site de rede são compartilhadas entre os recursos avançados do Enterprise Voice de controle de admissão de chamadas e de desvio de mídia quando os dois estão habilitados. Portanto, se você já configurou o controle de admissão de chamadas, não é preciso usar o procedimento a seguir para editar as informações do site e da região especificamente para o desvio de mídia. Siga as etapas neste procedimento se você ainda não tiver configurado as regiões e os sites de rede quanto ao controle de admissão de chamadas e se quiser alterar as configurações do desvio de chamada. 
  
Para que o bypass de mídia funcione corretamente, deve haver consistência entre um site conforme definido no Construtor de Topologias e como ele é definido quando você configura regiões de rede e sites de rede. Por exemplo, se você tiver um site de filial definido no Construtor de Topologias como tendo apenas um gateway PSTN implantado, esse site de filial deve ser configurado com uma política de Enterprise Voice que permite que os usuários do site de filial tenham suas chamadas PSTN roteadas pelo gateway PSTN no site de filial.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Para configurar informações de site e de região para desvio de mídia

1. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
2. Na barra de navegação à esquerda, clique em **Configurações de rede**.
    
3. Dê dois cliques na configuração **Global** na tabela.
    
4. Na página **Editar Configurações Globais**, marque a caixa de seleção **Habilitar desvio de mídia**.
    
5. Clique em **Usar as configurações de sites e região**.
    
6. Se necessário, marque a caixa de seleção **Habilitar desvio de mídia para sites não mapeados**.
    
    > [!NOTE]
    > Marque essa caixa de seleção somente se você tiver um ou mais sites grandes associados na mesma região e que não possuem restrições de largura de banda (por exemplo, um grande site central), mas também tem sites de filial associados à mesma região e que possuem restrições de largura de banda. Ao habilitar o desvio para sites não mapeados, a configuração é simplificada de forma que você especifica apenas as sub-redes associadas com os sites de filial em vez de precisar especificar todas as sub-redes associadas com todos os sites. Recomendamos que você não marque essa caixa de seleção se o controle de admissão de chamadas estiver habilitado. 
  
7. Clique em **Confirmar**.
    
Em seguida, adicione sub-redes ao site de rede, conforme descrito em [Associar uma sub-rede a um site de rede.](deploy-network.md#BKMK_AssociateSubnets) Depois de associar todas as sub-redes com os sites de rede, a implantação do desvio de mídia estará completa.
> [!IMPORTANT]
> Se ainda não tiverem sido criadas as regiões e os sites de rede, é preciso criá-los antes de prosseguir com a implantação do desvio de mídia. Para obter detalhes, [consulte Deploy network regions, sites and subnets in Skype for Business](deploy-network.md). 
  
## <a name="see-also"></a>Confira também

[Associar uma sub-rede a um site de rede](deploy-network.md#BKMK_AssociateSubnets)

