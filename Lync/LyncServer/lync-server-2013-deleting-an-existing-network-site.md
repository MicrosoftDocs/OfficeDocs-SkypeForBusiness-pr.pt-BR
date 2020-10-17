---
title: 'Lync Server 2013: excluindo um site de rede existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d37e08eddac5b6166043a45d7e669c7e0ecd71a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525378"
---
# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Excluindo um site de rede existente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado. Você pode usar o painel de controle do Lync Server 2013 para configurar sites e associá-los às regiões. Por exemplo, uma região de rede da América do Norte pode ser associada a sites da rede, como Chicago, Redmond e Vancouver. Um site da rede do CAC deve ser criado para cada site da organização, mesmo que esse site não tenha limitações de largura de banda. No painel de controle do Lync Server, você pode criar, modificar e excluir sites de rede. Use o seguinte procedimento para excluir um local de rede existente. Para obter detalhes sobre como criar ou modificar sites de rede, consulte [criando ou modificando sites de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>Para excluir um local de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Configuração da Rede** e em **Local**.

4.  Na página **Local**, clique no local que deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de um local de cada vez. Para fazer isso, pressione CTRL e selecione diversos locais mantendo a tecla pressionada. Ou então, para selecionar todos os locais, clique em <STRONG>Selecionar Tudo</STRONG> no menu <STRONG>Editar</STRONG>.

    
    </div>

5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.
    
    <div>
    

    > [!WARNING]  
    > Você não poderá remover um local de rede se ele estiver associado a uma sub-rede. Se você tentar fazer isso, receberá uma mensagem de erro. Para ver se o local está associado a alguma sub-rede, clique no local e em <STRONG>Mostrar detalhes</STRONG> no menu <STRONG>Editar</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

