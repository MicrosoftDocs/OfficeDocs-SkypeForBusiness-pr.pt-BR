---
title: Configurar tipos de endereço IP no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumo: revise as considerações de tipo de endereço IP abaixo antes de implementar o Skype for Business Server.'
ms.openlocfilehash: 21e6254255766874872a342a2316dc8cddd5f9d2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297047"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configure IP address types in Skype for Business

**Resumo:** Examine as considerações de tipo de endereço IP abaixo antes de implementar o Skype for Business Server.

Implante tipos de endereços IP usando as configurações de topologia que você configura no construtor de topologias. Esta seção descreve como implantar tipos de endereço IP em servidores de front-end, servidores de mediação e servidores de borda.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Implantar tipos de endereço IP em um Servidor Front-End Server

Usando o construtor de topologias, execute as etapas do procedimento a seguir para implantar tipos de endereços IP em um servidor front-end.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Implantar tipos de endereço IP em um Servidor Front-End

1. Em **Pools de Front-Ends do Enterprise Edition**, clique com o botão direito em um servidor de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).

2. Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dupla, selecione **habilitar IPv4** e **habilitar IPv6**.

   **Editar a caixa de diálogo Propriedades do pool do servidor front-end**

   - **Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.

     > [!NOTE]
     > Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6).

   - **Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o **Endereço IP principal**.

   - **Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.

   - **Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor Front-End. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.

> [!NOTE]
> A instalação de placas de interface de rede adicionais (NICs) para dar suporte à configuração de endereço IP PSTN (ou por qualquer outro motivo) não é compatível com os servidores front-end. Para obter mais informações sobre as configurações da NIC com suporte para o Skype for Business Server, consulte [plataformas de hardware do servidor para o Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Implantar tipos de endereço IP no Servidor de Mediação

Usando o construtor de topologias, execute as etapas do procedimento a seguir para implantar tipos de endereços IP em um servidor de mediação.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implantar os tipos de endereço IP em um Servidor de Mediação

- No construtor de topologias ****, em pools de mediação, clique com o botão direito do mouse no servidor dentro de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar Propriedades** no menu **Ação**.)

- Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.

   **Caixa de diálogo Editar Propriedades para o pool de Servidores de Mediação**

  - **Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.

    > [!NOTE]
    > Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6).

  - **Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o Endereço IP principal.

  - **Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.

  - **Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor Front-End. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.
> [!IMPORTANT]
> Só damos suporte a dois cartões de rede em servidores *dedicados* de mediação. Se a função de sServer de mediação estiver posicionada no front-end, os dois cartões de rede não são compatíveis. 

> [!NOTE]
> - Para obter mais informações sobre as configurações de NIC compatíveis com o Skype for Business Server 2015, consulte [hardware para o Skype for Business server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Para obter mais informações sobre as configurações de NIC compatíveis com o Skype for Business Server 2019, consulte [hardware para o Skype for Business server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Implantar tipos de endereço IP em um Servidor de Borda

Usando o construtor de topologias, execute as seguintes etapas:

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Para implantar tipos de endereço IP em um servidor de borda

1. Em Construtor de topologia, em **conjuntos de bordas**, clique com o botão direito do mouse no servidor dentro de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar Propriedades** no menu **Ação**.)

2. Na janela **Editar Propriedades**, selecione a configuração de endereço IP para a qual deseja oferecer suporte.

3. Para cada tipo de endereço selecionado, você deve fornecer os endereços internos e externos apropriados.
