---
title: Configurar tipos de endereço IP no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumo: revise as considerações de tipo de endereço IP abaixo antes de implementar o Skype for Business Server.'
ms.openlocfilehash: d5e50b8d3a964bb4e4dcbc502527e5249af3a1e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825251"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurar tipos de endereço IP no Skype for Business

**Resumo:** Revise as considerações de tipo de endereço IP abaixo antes de implementar o Skype for Business Server.

Você implanta tipos de endereço IP usando configurações de topologia que você configura no Construtor de Topologias. Esta seção descreve como implantar tipos de endereço IP em Servidores Front-End, Servidores de Mediação e Servidores de Borda.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Implantar tipos de endereço IP em um Servidor Front-End

Usando o Construtor de Topologias, execute as etapas do procedimento a seguir para implantar tipos de endereço IP em um Servidor Front-End.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Implantar tipos de endereço IP em um Servidor front-end

1. Em **Pools de front-end do Enterprise Edition**, clique com o botão direito em um servidor de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).

2. Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dupla, selecione **Habilitar IPv4** e **Habilitar IPv6**.

   **Editar a caixa de diálogo Propriedades do pool do servidor front-end**

   - **Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.

     > [!NOTE]
     > Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6).

   - **Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o **Endereço IP principal**.

   - **Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.

   - **Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor front-end. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.

> [!NOTE]
> A instalação de NICs (placas de interface de rede) adicionais para dar suporte à configuração de endereço IP PSTN (ou por qualquer outro motivo) em Servidores Front-End não é suportada. Para obter mais informações sobre as configurações NIC suportadas para o Skype for Business Server, consulte Server [hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Implantar tipos de endereço IP em um Servidor de Mediação

Usando o Construtor de Topologias, execute as etapas do procedimento a seguir para implantar tipos de endereço IP em um Servidor de Mediação.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implantar os tipos de endereço IP em um Servidor de Mediação

- No Construtor de Topologias, em **Pools de** Mediação, clique com o botão direito do mouse no servidor dentro de um pool e selecione **Editar Propriedades.** (Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).

- Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.

   **Caixa de diálogo Editar Propriedades para o pool de Servidores de Mediação**

  - **Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.

    > [!NOTE]
    > Essa é a opção recomendada para configurações IPv6.

  - **Limitar o uso do serviço para os endereços IP selecionados**. Selecione esta opção para informar um endereço específico a ser usado no novo servidor. Se você selecionar esta opção, terá que inserir um valor para Endereço IP principal.

  - **Endereço IP principal**. Insira o endereço IP que o servidor usará para todas as comunicações, com exceção de PSTN (rede telefônica pública comutada). O endereço IP inserido deve ter o formato do tipo de endereço selecionado.

  - **Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor front-end. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.
> [!IMPORTANT]
> Só damos suporte a duas placas de rede em *Servidores de* Mediação dedicados. Se a função Servidor de Mediação for locada no Front End, não há suporte para placas de rede duplas. 

> [!NOTE]
> - Para obter mais informações sobre as configurações NIC suportadas para o Skype for Business Server 2015, consulte [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Para obter mais informações sobre configurações de NIC com suporte para o Skype for Business Server 2019, consulte [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Implantar tipos de endereço IP em um Servidor de Borda

Usando o Construtor de Topologias, execute as seguintes etapas:

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Para implantar tipos de endereço IP em um servidor de borda

1. No Construtor de Topologias, em **pools de Borda,** clique com o botão direito do mouse no servidor dentro de um pool e selecione **Editar Propriedades.** (Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).

2. Na janela **Editar Propriedades**, selecione a configuração de endereço IP para a qual deseja oferecer suporte.

3. Para cada tipo de endereço selecionado, você deve fornecer os endereços internos e externos apropriados.
