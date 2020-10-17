---
title: Autorizar conexão com o servidor de borda do Office Communications Server 2007 R2
description: Autorizar a conexão com o servidor de borda do Office Communications Server 2007 R2.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8dadb2c476c892f4ffd548ce176d12d3b1a1cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545827"
---
# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autorizar conexão com o servidor de borda do Office Communications Server 2007 R2

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Para cada servidor front-end do Lync Server 2013 ou servidor Standard Edition no pool piloto, você deve atualizar a lista de servidores internos que estão autorizados a se conectar ao servidor de borda do Office Communications Server 2007 R2. Sem estas atualizações, conferências A/V (audiovisual) externas para usuários ingressando usando o Servidor de Borda herdado não irão funcionar.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Para autorizar a conexão com o servidor de borda do Office Communications Server 2007 R2

1.  No servidor de borda do Office Communications Server 2007 R2, no grupo **Ferramentas administrativas** , abra o snap-in **Gerenciamento do computador** .

2.  Na árvore do console, expanda **Serviços e Aplicativos**.

3.  Clique com o botão direito do mouse em **Office Communications Server 2007 R2**e clique em **Propriedades**.

4.  Clique na guia **Interno**.

5.  Em **Adicionar Servidor**, clique em **Adicionar**.

6.  Na caixa de diálogo **Adicionar Office Communications Server**, insira as informações apropriadas:
    
      - Especifique o FQDN (nome de domínio totalmente qualificado) de cada servidor front-end do Lync Server 2013 ou servidor Standard Edition e o pool do Lync Server 2013.
    
      - Especifique o FQDN do diretor do Lync Server 2013 se você configurou uma rota estática no pool que especifica o próximo computador de salto por seu FQDN.

7.  Após adicionar uma entrada para cada Lync Server 2013, servidor front-end, servidor Standard Edition, pool e diretor, clique em **aplicar** e clique em **OK** para fechar a página Propriedades.

</div>

</div>

<span> </span>

</div>

</div>

</div>

