---
title: 'Lync Server 2013: Implantar tipos de endereço IP em um Servidor Front-End Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33ab774cc5b0f15ed04d3803741b6355230130fb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>Implantar tipos de endereço IP em um Servidor Front-End Server para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-07-28_

Usando o construtor de topologias, execute as etapas do procedimento a seguir para implantar tipos de endereços IP em um servidor front-end.

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Implantar tipos de endereço IP em um Servidor Front-End

1.  Em **Pools de Front-Ends do Enterprise Edition**, clique com o botão direito em um servidor de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).

2.  Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.
    
    **Editar a caixa de diálogo Propriedades do pool do servidor front-end**
    
    ![Caixa de diálogo Propriedades de edição do servidor front-end] (images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Caixa de diálogo Propriedades de edição do servidor front-end")
    
      - **Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.
        
        <div>
        

        > [!NOTE]  
        > Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6).

        
        </div>
    
      - **Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o **Endereço IP principal**.
    
      - **Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.
    
      - **Endereço IP da PSTN**. A instalação de placas de interface de rede (NIC) adicionais para dar suporte à configuração de endereço IP PSTN para o Lync Server 2013 não é suportada nas funções do servidor de mediação posicionado. Para obter mais informações sobre as configurações da NIC com suporte para o Lync Server 2013, consulte [plataformas de hardware do servidor para o Lync server 2013](lync-server-2013-server-hardware-platforms.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

