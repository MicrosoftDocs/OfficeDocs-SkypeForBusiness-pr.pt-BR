---
title: 'Lync Server 2013: excluindo um site de rede existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772d653e0bde803f47a5742a4f3824bdef01c3f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Excluindo um site de rede existente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou implantação 9-1-1 aprimorada. Você pode usar o painel de controle do Lync Server 2013 para configurar sites e associá-los a regiões. Por exemplo, uma região de rede para a América do Norte pode estar associada a sites de redes como Chicago, Redmond e Vancouver. Um site de rede do CAC deve ser criado para cada site dentro de uma organização, mesmo que esse site não tenha limitações de largura de banda. No painel de controle do Lync Server, você pode criar, modificar e excluir sites de rede. Use o procedimento a seguir para excluir um site de rede existente. Para obter detalhes sobre como criar ou modificar sites de rede, consulte [criando ou modificando sites de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>Para excluir um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **site**.

4.  Na página do **site** , clique no site que você deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de um site de cada vez. Para fazer isso, pressione CTRL e selecione vários sites enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todos os sites, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .

    
    </div>

5.  No menu **Editar** , clique em **excluir**.

6.  Clique em **OK**.
    
    <div>
    

    > [!WARNING]  
    > Você não pode remover um site de rede se ele estiver associado a uma sub-rede de rede. Se você tentar remover um site associado a uma sub-rede, receberá uma mensagem de erro. Para ver se um site está associado a qualquer sub-rede, clique no site e, em seguida, clique em <STRONG>Mostrar detalhes</STRONG> no menu <STRONG>Editar</STRONG> .

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

