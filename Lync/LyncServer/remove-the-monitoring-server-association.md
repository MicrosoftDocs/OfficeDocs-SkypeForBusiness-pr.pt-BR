---
title: Remover a associação do Monitoring Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a12ec30f42106c3515376a0d408016e31c1cba5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>Remover a associação do Monitoring Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Para remover o Monitoring Server, você precisa alterar ou limpar a dependência do pool de front-ends associado, servidor front-end, aparelho de filial persistente e servidor de filial persistente. Edite as propriedades do pool de front-ends, servidor front-end, aparelho de filial persistente e servidor de filial persistente para remover a dependência. Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto repositório de banco de dados associado no construtor de topologias também será excluído.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>Para remover a associação do Servidor de Monitoramento

1.  Abra o servidor front-end do Lync Server 2013, abra o construtor de topologias.

2.  Navegue até o nó do Lync Server 2010.

3.  No construtor de topologias, expanda **pools de front-ends Enterprise Edition**, **servidores front-end Standard Edition**ou **sites de filiais**, com base em onde o servidor de monitoramento está definido.

4.  Se você tiver um servidor de filial persistente associado, expanda **sites de filial**, expanda o nome do site de filial e expanda **aparelhos de filial persistente**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Aparelhos de filial persistentes</STRONG> na interface do usuário aplicam-se ao servidor de filial persistente e ao aparelho de filial persistente.

    
    </div>

5.  Clique com o botão direito do mouse no pool, servidor ou dispositivo associado ao servidor de monitoramento e clique em **Editar propriedades**.

6.  Em **Editar Propriedades**, em **Geral**, em **Associações**, limpe a caixa de seleção **Associar Servidor de Monitoramento** e clique em **OK**.

7.  Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao servidor de monitoramento.

8.  Clique com o botão direito do mouse no servidor de monitoramento e clique em **excluir**.

9.  Em **Excluir Repositórios Dependentes**, clique em **OK**.

10. Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Lync Server, conforme necessário.

</div>

</div>

<span> </span>

</div>

</div>

</div>

