---
title: Remover a associação do Servidor de Monitoramento
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
ms.openlocfilehash: f26a809056674c231212db3f824a2ecb7ce7ecd1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>Remover a associação do Servidor de Monitoramento

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

Para remover o Monitoring Server, você precisa alterar ou limpar a dependência do pool de front-ends associado, servidor front-end, aparelho para ramificação sobreviventes e servidor de ramificação sobreviventes. Edite as propriedades do pool de front-end, servidor front-end, appliances para ramificação sobreviventes e servidor de ramificação sobreviventes para remover a dependência. Depois de limpar a dependência e excluir o servidor no construtor de topologias, você será notificado de que o objeto de repositório de banco de dados associado também será excluído.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>Para remover a associação do Monitoring Server

1.  Abra o servidor front-end do Lync Server 2013, abra o construtor de topologias.

2.  Navegue até o nó do Lync Server 2010.

3.  No construtor de topologia, expanda **pools de front-end do Enterprise Edition**, **servidores front-end da edição padrão**ou **sites de filiais**com base em onde o servidor de monitoramento está definido.

4.  Se você tiver um servidor de ramificação sobreviventes associado, expanda **sites de ramificação**, expanda o nome do site da filial e expanda **aparelhos de ramificação sobreviventes**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Aparelhos de ramificação sobreviventes</STRONG> na interface do usuário se aplicam ao servidor de ramificação sobreviventes e ao aparelho de ramificação sobreviventes.

    
    </div>

5.  Clique com o botão direito do mouse no pool, no servidor ou no dispositivo associado ao Monitoring Server e clique em **Editar propriedades**.

6.  Em **Editar propriedades**, em **geral**, em **associações**, desmarque a caixa de seleção **associar o servidor de monitoramento** e clique em **OK**.

7.  Repita a etapa anterior para qualquer outro pool, servidor ou dispositivo associado ao servidor de monitoramento.

8.  Clique com o botão direito do mouse no servidor de monitoramento e clique em **excluir**.

9.  Em **excluir repositórios dependentes**, clique em **OK**.

10. Publique a topologia, verifique o status da replicação e execute o assistente de implantação do Lync Server conforme necessário.

</div>

</div>

<span> </span>

</div>

</div>

</div>

