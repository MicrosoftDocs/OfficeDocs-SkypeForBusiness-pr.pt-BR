---
title: Adicionar site de filial de dispositivo de filial persistente do Lync Server 2013 à sua topologia
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
ms.openlocfilehash: 1e57a7b062cd95012102ba30a527c99c2fba71d6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Adicionar site de filial de dispositivo de filial persistente do Lync Server 2013 à sua topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-07_

Os aparelhos de ramificação persistentes do Microsoft Lync Server 2013 (SBA) não podem ser associados a um pool de front-ends do Microsoft Lync Server 2010 como um registrador de backup. O SBA deve ser associado a um pool de front-ends do Microsoft Lync Server 2013. Estas etapas pressupõem um Microsoft Lync Server 2013 SBA. Execute este procedimento no local central.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Para adicionar sites de filiais com o Microsoft Lync Server 2013 SBA à sua topologia

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na árvore do console, expanda o site central, expanda **sites de filial**e clique em **novo site de filial**.

3.  Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite um nome para o novo site de filial.

4.  (Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.

5.  Clique em **Avançar**.

6.  (Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações:
    
      - Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.
    
      - Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.
    
      - Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.

7.  Clique em **Avançar** e execute uma das seguintes ações:
    
      - Se você estiver usando um aparelho de filial persistente ou servidor de filial persistente neste site, certifique-se de que a caixa de seleção **abrir o assistente de novo persistente quando este assistente for fechado** esteja marcada.
    
      - Se você não estiver usando um aparelho de filial persistente ou servidor de filial persistente neste site, desmarque a caixa de seleção **abrir o novo assistente persistente quando este assistente fechar** .
    
      - Clique em **concluir**e siga as instruções do assistente que são exibidas. Para obter informações sobre itens de assistente, consulte [definir um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Repita as etapas anteriores para cada site de filial que deseja adicionar à topologia.

</div>

<div>

## <a name="see-also"></a>Confira também


[Definir um servidor ou aparelho de filial persistente no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definir um gateway PSTN para um site de filial no Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

