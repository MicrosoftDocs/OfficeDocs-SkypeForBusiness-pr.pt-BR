---
title: Adicionar Aparelho de Filial Persistente do Lync Server 2013 a sua topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fc2dd7426006d0c8f19b38b85ba778744fff2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Adicionar Aparelho de Filial Persistente do Lync Server 2013 a sua topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-07_

Microsoft Lync Server 2013 não é possível associar aparelhos de ramificação sobreviventes (SBA) a um pool de front-end do Microsoft Lync Server 2010 como um registrador de backup. O SBA deve estar associado a um pool de front-ends do Microsoft Lync Server 2013. Estas etapas pressupõem um Microsoft Lync Server 2013 SBA. Execute este procedimento no site central.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Para adicionar sites de filiais com o Microsoft Lync Server 2013 SBA à sua topologia

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na árvore de console, expanda o site central, expanda **sites de ramificação**e clique em **novo site de filial**.

3.  Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite um nome para o novo site de filial.

4.  Adicionais Clique em **Descrição**e digite uma descrição significativa para o site da filial.

5.  Click **Next**.

6.  Adicionais Na caixa de diálogo próximo **definir novo site de filiais** , siga um destes procedimentos:
    
      - Clique em **cidade**e digite o nome da cidade na qual o site da filial está localizado.
    
      - Clique em **estado/região**e, em seguida, digite o nome do Estado ou da região em que o site da filial está localizado.
    
      - Clique em **código do país**e, em seguida, digite o código de chamada de dois dígitos para o país/região no qual o site da filial está localizado.

7.  Clique em **Avançar**e, em seguida, siga um destes procedimentos:
    
      - Se você estiver usando um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes neste site, certifique-se de que a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** esteja marcada.
    
      - Se você não estiver usando um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes neste site, desmarque a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** .
    
      - Clique em **concluir**e siga as instruções no assistente que é aberto. Para saber mais sobre os itens do assistente, confira [definir um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Repita as etapas anteriores para cada site de ramificação que você deseja adicionar à topologia.

</div>

<div>

## <a name="see-also"></a>Confira também


[Definir um Servidor ou Aparelho de Filial Persistente no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definir um gateway de PSTN para um site de filial no Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

