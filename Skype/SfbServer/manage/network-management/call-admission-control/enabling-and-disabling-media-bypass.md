---
title: Ativação e desativação de bypass de mídia
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use os procedimentos neste artigo para habilitar ou desabilitar o bypass de mídia usando o Skype para painel de controle do servidor de negócios.
ms.openlocfilehash: eebbc111f0d205be8dced9ec8ddb5150deff8119
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874278"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Habilitar e desabilitar bypass de mídia no Skype for Business Server

Use os procedimentos neste artigo para habilitar ou desabilitar o bypass de mídia usando o Skype para painel de controle do servidor de negócios.

## <a name="enable-network-media-bypass"></a>Habilitar bypass de mídia de rede 

Definições de desvio de mídia são aplicadas globalmente entre um Skype para implantação de servidor de negócios. Bypass de mídia permite que as chamadas para ignorar o servidor de mediação. Para obter detalhes sobre quando usar o desvio de mídia, consulte [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Você pode habilitar e configurar o desvio de mídia a partir do Skype para painel de controle do servidor de negócios.


### <a name="to-enable-and-configure-media-bypass"></a>Para habilitar e configurar o bypass de mídia

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Global**.

4.  Na página **Global** , clique na configuração **Global** . Sempre existe apenas uma configuração, e ele é chamado sempre Global.

5.  No menu **Editar** , clique em **Exibir detalhes**.

6.  Na página **Editar configuração Global** , clique na caixa de seleção **Habilitar bypass de mídia** .

7.  Selecione uma das seguintes opções:
    
      - **Sempre desviar**   Selecione essa opção para executar uma tentativa de mídia desvio de todas as chamadas. Essa opção estará disponível se o controle de admissão de chamadas (CAC) estiver ativado. Se o CAC não estiver habilitado, selecione essa opção nas seguintes situações:
        
          - Não há nenhuma necessidade de controle de largura de banda.
        
          - Não há nenhuma necessidade de configração minuciosa determinar quando o desvio deve acontecer.
        
          - Existe conectividade total entre gateways e clientes.
    
      - **Use os sites e configuração de região**   CAC se estiver habilitado, essa opção é selecionada por padrão e não pode ser alterada. Quando essa opção é selecionada, regiões e sites de configuração de rede serão usados para determinar quando o desvio de mídia é possível. Se você selecionar essa opção, você pode optar por habilitar o desvio para sites que não são mapeadas. Clique na caixa de seleção **Habilitar desvio de mídia para sites não mapeados** somente se você tiver um ou mais sites grandes associados à região mesma que não tem restrições de largura de banda (por exemplo, um grande site central) e também tiver alguns sites de filiais associados a região mesmo que têm restrições de largura de banda. Quando você habilita os endereços sites não mapeados, a configuração é dinâmico porque você especificar apenas as sub-redes associadas aos sites de filial em vez de precisar especificar todas as sub-redes associadas com todos os sites. Recomendamos que você não marque a caixa de seleção **Habilitar desvio de mídia para sites não mapeados** se o CAC esteja habilitado.

8.  Clique em **Confirmar** para salvar suas alterações.


## <a name="disable-network-media-bypass"></a>Desabilitar bypass de mídia de rede

Definições de desvio de mídia são aplicadas globalmente entre um Skype para implantação de servidor de negócios. Bypass de mídia permite que as chamadas para ignorar o servidor de mediação. Para obter detalhes sobre quando usar o desvio de mídia, consulte [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Você pode desabilitar o desvio de mídia a partir do Skype para painel de controle do servidor de negócios. 


### <a name="to-disable-media-bypass"></a>Para desabilitar o bypass de mídia

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Global**.

4.  Na página **Global** , clique na configuração **Global** . Sempre existe apenas uma configuração, e ele é chamado sempre Global.

5.  No menu **Editar** , clique em **Exibir detalhes**.

6.  Na página **Editar configuração Global** , desmarque a caixa de seleção **Habilitar bypass de mídia** .

7.  Clique em **Confirmar** para salvar suas alterações.

  
