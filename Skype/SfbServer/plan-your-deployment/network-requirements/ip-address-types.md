---
title: Configurar tipos de endereço IP no Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumo: Revise as considerações de tipo de endereço IP abaixo antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: adebab15a0c10310b25af30f6e933625df61dc3d
ms.sourcegitcommit: a612ebe25e06c2cb090f776325712caf3cf3b943
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2018
ms.locfileid: "19630144"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurar tipos de endereço IP no Skype for Business
 
**Resumo:** Revise as considerações de tipo de endereço IP abaixo antes de implementar Skype para Business Server 2015.
  
Você pode implantar tipos de endereço IP usando as configurações de topologia que você configurar no construtor de topologias. Esta seção descreve como implantar os tipos de endereço IP em servidores Front-End, servidores de mediação e servidores de borda.
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Implantar tipos de endereço IP em um Servidor Front-End

Usando o construtor de topologias, execute as etapas no procedimento a seguir para implantar tipos de endereço IP em um servidor Front-End.
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Implantar tipos de endereço IP em um Servidor Front-End

1. Em **Pools de Front-Ends do Enterprise Edition**, clique com o botão direito em um servidor de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).
    
2. Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.
    
   **Editar caixa de diálogo de propriedades para o pool do servidor Front-End**

  - **Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado. 
    
    > [!NOTE]
    > Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6). 
  
  - **Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o **Endereço IP principal**.
    
  - **Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.
    
  - **Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor Front-End. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.
    
    > [!NOTE]
    > Não há suporte para a instalação de placas de interface de rede adicionais (NICs) para dar suporte a configuração de endereço IP PSTN nos servidores Front-End. Para obter mais informações sobre configurações de NIC com suporte para Skype para Business Server, consulte [Server hardware platforms do Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Implantar tipos de endereço IP no Servidor de Mediação

Usando o construtor de topologias, execute as etapas no procedimento a seguir para implantar tipos de endereço IP em um servidor de mediação.
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implantar os tipos de endereço IP em um Servidor de Mediação

- No construtor de topologia, em **pools de mediação**, o servidor de um pool do mouse em e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar Propriedades** no menu **Ação**.)
    
- Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.
    
   **Editar caixa de diálogo de propriedades para o pool do servidor de mediação**

  - **Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado. 
    
    > [!NOTE]
    > Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6). 
  
  - **Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o Endereço IP principal.
    
  - **Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.
    
  - **Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor Front-End. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.
    
    > [!NOTE]
    > Não há suporte para a instalação de NICs adicionais para dar suporte a configuração de endereço IP PSTN nos servidores de mediação autônomo. Para obter mais informações sobre configurações de NIC com suporte para Skype para Business Server, consulte [Server hardware platforms do Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). 
  
## <a name="deploy-ip-address-types-on-an-edge-server"></a>Implantar tipos de endereço IP em um Servidor de Borda

Usando o construtor de topologias, execute as seguintes etapas:
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Para implantar tipos de endereço IP em um servidor de borda

1. No construtor de topologia, em **pools de borda**, o servidor de um pool do mouse em e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar Propriedades** no menu **Ação**.)
    
2. Na janela **Editar Propriedades**, selecione a configuração de endereço IP para a qual deseja oferecer suporte.    

3. Para cada tipo de endereço selecionado, você deve fornecer os endereços internos e externos apropriados.
    