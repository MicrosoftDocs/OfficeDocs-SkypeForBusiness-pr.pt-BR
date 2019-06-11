---
title: Configurar registros de DNS para implantação de pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0425d8adf0e09f3a0d081b1708d7e67e3f53a24
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configurar registros de DNS para implantação de pool piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-24_

Antes de implantar o pool piloto do Lync Server 2013, você deve atualizar as entradas do host DNS a para o pool piloto. Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou domínio no mínimo como membro do grupo Domain admins ou um membro do grupo DnsAdmins.

**Para configurar registros do host DNS A**

1.  No servidor DNS (sistema de nomes de domínio), clique em **Iniciar**, clique em **Ferramentas administrativas**e clique em **DNS**.

2.  Na árvore de console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 será instalado.

3.  Clique em **novo host (A ou aaaa)**.

4.  Clique em **nome**, digite o nome do host do pool (o nome do domínio é presumido na zona em que o registro é definido e não precisa ser inserido como parte do registro a).

5.  Clique em **endereço IP**, digite o endereço IP do pool de front-ends.

6.  Clique em **Adicionar host**e, em seguida, clique em **OK**.

7.  Quando terminar, clique em **concluído**.

</div>

<span> </span>

</div>

</div>

</div>

