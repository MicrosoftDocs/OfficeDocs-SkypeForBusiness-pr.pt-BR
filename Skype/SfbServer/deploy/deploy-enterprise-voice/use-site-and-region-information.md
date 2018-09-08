---
title: Configurar as configurações globais de desvio de mídia no Skype para Business Server usem informações de site e da região
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configure o bypass de mídia a ser usado para apenas alguns sites e regiões Skype para Business Server Enterprise Voice.
ms.openlocfilehash: cb3d29a57fa3ff9719ae26197106005667921ade
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888669"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>Configurar as configurações globais de desvio de mídia no Skype para Business Server usem informações de site e da região
 
Configure o bypass de mídia a ser usado para apenas alguns sites e regiões Skype para Business Server Enterprise Voice. 
  
 Se você usar as etapas deste tópico para definir as configurações globais para o media bypass, pressupõe-se que você não tem boa conectividade entre todos os Skype para pontos de extremidade de negócios e qualquer ponto para o qual você configurou o desvio de mídia na conexão do tronco.
  
> [!NOTE]
> As informações de região de rede e de site de rede são compartilhadas entre os recursos avançados do Enterprise Voice de controle de admissão de chamadas e de desvio de mídia quando os dois estão habilitados. Portanto, se você já configurou o controle de admissão de chamadas, não é preciso usar o procedimento a seguir para editar as informações do site e da região especificamente para o bypass de mídia. Siga as etapas neste procedimento se você ainda não tiver configurado as regiões e os sites de rede quanto ao controle de admissão de chamadas e se quiser alterar as configurações do bypass de chamada. 
  
Bypass de mídia para funcionar corretamente deve haver consistência entre um site conforme definido no construtor de topologia e como ele é definido quando você configura regiões de rede e locais de rede. Por exemplo, se você tiver um site de filial que você definiu no construtor de topologias como tendo apenas um gateway PSTN implantado e esse site de filial deve ser configurado com uma política do Enterprise Voice que permite aos usuários do site de filial ter suas chamadas PSTN roteadas pela PSTN gateway no site da filial.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>Para configurar informações de site e de região para bypass de mídia

1. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
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
> Se ainda não tiverem sido criadas as regiões e os sites de rede, é preciso criá-los antes de prosseguir com a implantação do bypass de mídia. Para obter detalhes, consulte [Deploy regiões de rede, sites e sub-redes em Skype para negócios](deploy-network.md). 
  
## <a name="see-also"></a>Consulte também

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

