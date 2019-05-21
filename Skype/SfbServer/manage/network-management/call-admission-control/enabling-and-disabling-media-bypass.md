---
title: Habilitando e desabilitando o bypass de mídia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use os procedimentos deste artigo para habilitar ou desabilitar o bypass de mídia usando o painel de controle do Skype for Business Server.
ms.openlocfilehash: acfa963e71f3c3b89d0e79648d00871b1ab44616
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279582"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Habilitar e desabilitar bypass de mídia no Skype for Business Server

Use os procedimentos deste artigo para habilitar ou desabilitar o bypass de mídia usando o painel de controle do Skype for Business Server.

## <a name="enable-network-media-bypass"></a>Habilitar bypass de mídia de rede 

As configurações de bypass de mídia se aplicam globalmente em uma implantação do Skype for Business Server. O bypass de mídia permite que as chamadas ignorem o servidor de mediação. Para obter detalhes sobre quando usar o bypass de mídia, consulte [planejar a bypass de mídia](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Você pode habilitar e configurar o bypass de mídia no painel de controle do Skype for Business Server.


### <a name="to-enable-and-configure-media-bypass"></a>Para habilitar e configurar o bypass de mídia

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **global**.

4.  Na página **global** , clique em configuração **global** . Sempre existe apenas uma configuração, e ela é sempre chamada de global.

5.  No menu **Editar** , clique em **Exibir detalhes**.

6.  Na página **Editar configuração global** , clique na caixa de seleção **habilitar bypass de mídia** .

7.  Selecione uma das seguintes opções:
    
      - **Sempre ignorar**   Selecione esta opção para tentar ignorar a mídia em todas as chamadas. Essa opção não estará disponível se o controle de admissão de chamadas (CAC) estiver habilitado. Se o CAC não estiver habilitado, selecione esta opção nas seguintes situações:
        
          - Não há necessidade de controle de largura de banda.
        
          - Não é preciso ter uma configuração refinada para determinar quando bypass deve acontecer.
        
          - Há conectividade total entre gateways e clientes.
    
      - **Usar a configuração**   de sites e regiões se o CAC estiver habilitado, essa opção será selecionada por padrão e não poderá ser alterada. Quando essa opção estiver selecionada, os sites de configuração de rede e regiões serão usados para determinar quando o bypass de mídia é possível. Se você selecionar essa opção, poderá optar por habilitar o bypass para sites que não estão mapeados. Marque a caixa de seleção **Permitir bypass para sites não mapeados** somente se você tiver um ou mais sites grandes associados à mesma região que não têm restrições de largura de banda (por exemplo, um site central grande) e também tem alguns sites de filiais associados ao mesma região que tem restrições de largura de banda. Quando você habilita o bypass para sites não mapeados, a configuração é simplificada porque você especifica somente as sub-redes associadas a sites de ramificação, em vez de precisar especificar todas as sub-redes associadas a todos os sites. Recomendamos que você não marque a caixa de seleção **Permitir bypass para sites não mapeados** se o CAC estiver habilitado.

8.  Clique em **confirmar** para salvar as alterações.


## <a name="disable-network-media-bypass"></a>Desabilitar bypass de mídia de rede

As configurações de bypass de mídia se aplicam globalmente em uma implantação do Skype for Business Server. O bypass de mídia permite que as chamadas ignorem o servidor de mediação. Para obter detalhes sobre quando usar o bypass de mídia, consulte [planejar a bypass de mídia](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Você pode desativar o bypass de mídia no painel de controle do Skype for Business Server. 


### <a name="to-disable-media-bypass"></a>Para desativar o bypass de mídia

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **global**.

4.  Na página **global** , clique em configuração **global** . Sempre existe apenas uma configuração, e ela é sempre chamada de global.

5.  No menu **Editar** , clique em **Exibir detalhes**.

6.  Na página **Editar configuração global** , desmarque a caixa de seleção **habilitar bypass de mídia** .

7.  Clique em **confirmar** para salvar as alterações.

  
