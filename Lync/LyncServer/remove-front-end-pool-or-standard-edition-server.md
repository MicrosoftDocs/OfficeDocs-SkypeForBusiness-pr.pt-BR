---
title: Remover pool de front-ends ou servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47aa2edebe202f6ed21d1b802d899faea563feba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>Remover pool de front-ends ou servidor Standard Edition

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Este tópico orienta você durante o processo de remoção de um pool de front-ends ou de um servidor front-end Standard Edition. Ao remover um pool de front-ends, você remove cada servidor de front-end que pertence ao pool como parte do processo de remoção do pool. Ao remover um servidor front-end Standard Edition, você deve remover a definição do repositório SQL do construtor de topologias.

<div>

## <a name="to-remove-a-front-end-server-pool"></a>Para remover um pool de Servidor Front-End

1.  Abra o Construtor de Topologia.

2.  Navegue até o nó do Lync Server 2010.

3.  Expanda **pools de front-ends Enterprise Edition**, expanda o pool de front-ends, clique com o botão direito do mouse no pool de front-ends que você deseja remover e clique em **excluir**.

4.  Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Lync Server conforme necessário.

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>Para remover um Servidor Front-End Standard Edition

1.  Abra o Construtor de Topologia.

2.  Navegue até o nó do Lync Server 2010.

3.  Expanda **servidores front-end Standard Edition**, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.

4.  Expanda **repositórios SQL**, clique com o botão direito do mouse no banco de dados do SQL Server que está associado ao servidor front-end Standard Edition e clique em **excluir**.
    
    <div>
    

    > [!IMPORTANT]  
    > Você deve remover a definição dos bancos de dados do SQL Server posicionados do servidor front-end Standard Edition.

    
    </div>

5.  Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Lync Server conforme necessário.

</div>

</div>

<span> </span>

</div>

</div>

</div>

