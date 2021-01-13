---
title: Habilitando e desabilitando o bypass de mídia
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Use os procedimentos neste artigo para habilitar ou desabilitar o bypass de mídia usando o Painel de Controle do Skype for Business Server.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816491"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Habilitar e desabilitar bypass de mídia no Skype for Business Server

Use os procedimentos neste artigo para habilitar ou desabilitar o bypass de mídia usando o Painel de Controle do Skype for Business Server.

## <a name="enable-network-media-bypass"></a>Habilitar bypass de mídia de rede 

As configurações de bypass de mídia se aplicam globalmente em uma implantação do Skype for Business Server. O desvio de mídia permite que chamadas ignorem o Servidor de Mediação. Para obter detalhes sobre quando usar o bypass de mídia, consulte [Plano para bypass de mídia.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

Você pode habilitar e configurar o bypass de mídia do Painel de Controle do Skype for Business Server.


### <a name="to-enable-and-configure-media-bypass"></a>Para habilitar e configurar o desvio de mídia

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Global.**

4.  Na página **Global**, clique na configuração **Global**. Sempre existe somente uma configuração, sempre chamada Global.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar Configuração Global**, clique na opção **Habilitar desvio de mídia**.

7.  Selecione uma das seguintes opções:
    
      - **Sempre ignorar**   Selecione essa opção para tentar o bypass de mídia em todas as chamadas. Esta opção estará indisponível se o controle de admissão de chamadas (CAC) estiver habilitado. Se o CAC não estiver habilitado, selecione esta opção nas seguintes situações:
        
          - Não existe a necessidade de controle de largura de banda.
        
          - Não existe a necessidade de uma configuração refinada para determinar quando o desvio deve acontecer.
        
          - Existe conectividade total entre gateways e clientes.
    
      - **Usar a configuração de sites e região**   Se o CAC estiver habilitado, essa opção será selecionada por padrão e não poderá ser alterada. Quando esta opção está selecionada, a configuração de rede de sites e regiões será usada para determinar quando o desvio de mídia será possível. Se esta opção for selecionada, você pode optar por habilitar o desvio para sites que não estão mapeados. Clique na opção **Habilitar desvio para sites não mapeados** somente se você tiver um ou mais sites grandes associados à mesma região, que não possuem restrições de largura de banda (por exemplo, um site central grande) e se tiver também alguns sites de filial associados à mesma região que executa as restrições de largura de banda. Ao habilitar o desvio para sites não mapeados, a configuração é eficiente porque somente as sub-redes associadas aos sites de filial são especificadas, em vez da necessidade de especificas todas as sub-redes associadas as todos os sites. É recomendável não selecionar a opção **Habilitar desvio para sites não mapeados** se o CAC estiver habilitado.

8.  Clique em **Confirmar** para salvar suas alterações.


## <a name="disable-network-media-bypass"></a>Desabilitar bypass de mídia de rede

As configurações de bypass de mídia se aplicam globalmente em uma implantação do Skype for Business Server. O desvio de mídia permite que chamadas ignorem o Servidor de Mediação. Para obter detalhes sobre quando usar o bypass de mídia, consulte [Plano para bypass de mídia.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md) Você pode desabilitar o bypass de mídia do Painel de Controle do Skype for Business Server. 


### <a name="to-disable-media-bypass"></a>Para desativar o desvio de mídia

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Global.**

4.  Na página **Global**, clique na configuração **Global**. Sempre existe somente uma configuração, sempre chamada Global.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar Configuração Global**, desmarque a caixa de seleção **Ativar desvio de mídia**.

7.  Clique em **Confirmar** para salvar suas alterações.

  
