---
title: 'Lync Server 2013: Adicionar sites de filial a sua topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029627060ff03b804d0d2f76f40fdd4052f0d1c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Adicionar sites de filial a sua topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

Os sites de filiais representam filiais físicas conectadas a seus escritórios principais por meio de um link de WAN. Para adicionar um site de ramificação à sua topologia do Lync, execute este procedimento no site central.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>Para adicionar sites de filiais à sua topologia

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server**e, em seguida, clique em **Construtor de topologia do Lync Server**.

2.  Na árvore de console, expanda o site central, clique com o botão direito do mouse em **sites**de ramificação e clique em **novo site de filial**.

3.  Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite o nome do site de filial.

4.  Adicionais Clique em **Descrição**e digite uma descrição significativa para o site da filial.

5.  Click **Next**.

6.  Adicionais Na caixa de diálogo próximo **definir novo site** de filiais, siga um destes procedimentos:
    
      - Clique em **cidade**e digite o nome da cidade na qual o site da filial está localizado.
    
      - Clique em **estado/região**e, em seguida, digite o nome do Estado ou da região em que o site da filial está localizado.
    
      - Clique em **código do país**e, em seguida, digite o código de chamada de dois dígitos para o país/região no qual o site da filial está localizado.

7.  Clique em **Avançar**e, em seguida, siga um destes procedimentos:
    
      - Se você estiver usando um aplicativo ou um aplicativo de ramificação sobreviventes neste site, certifique-se de que a caixa de seleção **abrir o assistente para uso futuro quando este assistente for fechado** estiver marcada, clique em **concluir**e siga as instruções no assistente que é aberta. Para saber mais sobre os itens do assistente, confira [definir um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Se você não estiver usando um aplicativo ou aplicativo de ramificação sobreviventes neste site, desmarque a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** e clique em **concluir**.

8.  Repita as etapas anteriores para cada site de ramificação que você deseja adicionar à topologia.

**Próxima etapa:**

Para aplicativos ou aparelhos de ramificação sobreviventes: [definir um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Para conectividade PSTN não resiliente: [defina um gateway PSTN para um site de filial no Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)ou [Configure um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

