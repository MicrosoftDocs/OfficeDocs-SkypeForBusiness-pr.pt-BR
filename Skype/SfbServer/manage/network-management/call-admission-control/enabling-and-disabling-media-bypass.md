---
title: Habilitando e desabilitando o bypass de mídia
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Use os procedimentos deste artigo para habilitar ou desabilitar o bypass de mídia usando o painel Skype for Business Server Controle.
ms.openlocfilehash: abbbc6bf77a5fe1aea22de9c5f225ac694cf1d1d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750280"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Habilitar e desabilitar bypass de mídia no Skype for Business Server

Use os procedimentos deste artigo para habilitar ou desabilitar o bypass de mídia usando o painel Skype for Business Server Controle.

## <a name="enable-network-media-bypass"></a>Habilitar bypass de mídia de rede 

As configurações de bypass de mídia se aplicam globalmente em uma implantação Skype for Business Server mídia. O desvio de mídia permite que chamadas ignorem o Servidor de Mediação. Para obter detalhes sobre quando usar o bypass de mídia, consulte [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Você pode habilitar e configurar o bypass de mídia Skype for Business Server Painel de Controle.


### <a name="to-enable-and-configure-media-bypass"></a>Para habilitar e configurar o desvio de mídia

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Global**.

4.  Na página **Global**, clique na configuração **Global**. Sempre existe somente uma configuração, sempre chamada Global.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar Configuração Global**, clique na opção **Habilitar desvio de mídia**.

7.  Selecione uma das seguintes opções:
    
      - **Sempre desviar**   Selecione esta opção para tentar o desvio de mídia em todas as chamadas. Esta opção estará indisponível se o controle de admissão de chamadas (CAC) estiver habilitado. Se o CAC não estiver habilitado, selecione esta opção nas seguintes situações:
        
          - Não existe a necessidade de controle de largura de banda.
        
          - Não existe a necessidade de uma configuração refinada para determinar quando o desvio deve acontecer.
        
          - Existe conectividade total entre gateways e clientes.
    
      - **Use a configuração de sites e região**   Se o CAC estiver habilitado, esta opção será selecionada por padrão e não poderá ser alterada. Quando esta opção está selecionada, a configuração de rede de sites e regiões será usada para determinar quando o desvio de mídia será possível. Se esta opção for selecionada, você pode optar por habilitar o desvio para sites que não estão mapeados. Clique na opção **Habilitar desvio para sites não mapeados** somente se você tiver um ou mais sites grandes associados à mesma região, que não possuem restrições de largura de banda (por exemplo, um site central grande) e se tiver também alguns sites de filial associados à mesma região que executa as restrições de largura de banda. Ao habilitar o desvio para sites não mapeados, a configuração é eficiente porque somente as sub-redes associadas aos sites de filial são especificadas, em vez da necessidade de especificas todas as sub-redes associadas as todos os sites. É recomendável não selecionar a opção **Habilitar desvio para sites não mapeados** se o CAC estiver habilitado.

8.  Clique em **Confirmar** para salvar suas alterações.


## <a name="disable-network-media-bypass"></a>Desabilitar bypass de mídia de rede

As configurações de bypass de mídia se aplicam globalmente em uma implantação Skype for Business Server mídia. O desvio de mídia permite que chamadas ignorem o Servidor de Mediação. Para obter detalhes sobre quando usar o bypass de mídia, consulte [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Você pode desabilitar o bypass de mídia Skype for Business Server Painel de Controle. 


### <a name="to-disable-media-bypass"></a>Para desativar o desvio de mídia

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Global**.

4.  Na página **Global**, clique na configuração **Global**. Sempre existe somente uma configuração, sempre chamada Global.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar Configuração Global**, desmarque a caixa de seleção **Ativar desvio de mídia**.

7.  Clique em **Confirmar** para salvar suas alterações.

  
