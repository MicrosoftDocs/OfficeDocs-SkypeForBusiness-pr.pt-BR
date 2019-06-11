---
title: Remover a associação de Servidor de Arquivamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ab171493890c610e0f11b7cd124c7c2e1c600c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a>Remover a associação de Servidor de Arquivamento

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

Para remover um servidor de arquivamento, você precisa alterar ou desmarcar a dependência do pool de front-ends associado, servidor front-end, aparelho para filiais e servidor de ramificação sobreviventes. Edite as propriedades do pool de front-end, servidor front-end, appliances para ramificação sobreviventes e servidor de ramificação sobreviventes para remover a dependência. Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto de repositório de banco de dados associado também será excluído.

<div>

## <a name="to-remove-the-archiving-server-association"></a>Para remover a associação do servidor de arquivamento

1.  Abra o servidor front-end do Lync Server 2013, abra o construtor de topologias.

2.  Navegue até o nó do Lync Server 2010.

3.  No construtor de topologia, expanda Pools de **front-end do Enterprise Edition**, **servidores front-end da edição padrão**ou **sites**de filiais com base em onde o servidor de arquivamento está definido.

4.  Se você tiver um servidor de ramificação sobreviventes associado, expanda **sites**de ramificação, expanda o nome do site da filial e expanda **aparelhos de ramificação sobreviventes**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Aparelhos de ramificação sobreviventes</STRONG> na interface do usuário se aplicam ao servidor de ramificação sobreviventes e ao aparelho de ramificação sobreviventes.

    
    </div>

5.  Clique com o botão direito do mouse no pool, no servidor ou no dispositivo associado ao servidor de arquivamento e, em seguida, clique em **Editar propriedades**.

6.  Em **Editar propriedades**, em **geral**, em **associações**, desmarque a caixa de seleção **associar servidor** de arquivamento e clique em **OK**.

7.  Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao servidor de arquivamento que você deseja remover.

8.  Clique com o botão direito do mouse no servidor de arquivamento e, em seguida, clique em **excluir**.

9.  Em **excluir repositórios dependentes**, clique em **OK**.

10. Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Lync Server conforme necessário.

</div>

</div>

<span> </span>

</div>

</div>

</div>

