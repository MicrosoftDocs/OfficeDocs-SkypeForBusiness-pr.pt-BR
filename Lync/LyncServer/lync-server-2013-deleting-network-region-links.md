---
title: 'Lync Server 2013: excluindo links de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c467d499b0a0c9a3e85884927aed8ab819467d61
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525338"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a>Excluindo links de região de rede no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. Regiões dentro de uma rede são vinculadas por conectividade de WAN física. Você pode usar o painel de controle do Lync Server para excluir um link existente entre duas regiões de rede. Para obter detalhes sobre como criar ou modificar um link de região de rede, confira [Configurando links de região de rede no Lync Server 2013](lync-server-2013-configuring-network-region-links.md)

<div>

## <a name="to-delete-a-network-region-link"></a>Para excluir um link de região de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Configuração da rede** e em **Link da região**.

4.  Na página **link de região** , clique no link de região que deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de um link de região por vez. Para fazer isso, pressione CTRL e selecione vários links de região mantendo pressionada a tecla CTRL. Ou, para selecionar todos os links de região, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .

    
    </div>

5.  No menu **Editar** , selecione **excluir**.

6.  Clique em **OK**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando links de região de rede no Lync Server 2013](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

