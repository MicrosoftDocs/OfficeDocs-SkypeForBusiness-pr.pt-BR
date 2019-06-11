---
title: 'Lync Server 2013: Configurar registros de Host DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Configurar registros de Host DNS para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou domínio no mínimo como membro do grupo Domain admins ou um membro do grupo DnsAdmins.

<div>

## <a name="to-configure-dns-host-a-records"></a>Para configurar registros do host DNS A

1.  No servidor DNS (sistema de nomes de domínio), clique em **Iniciar**, clique em **Ferramentas administrativas**e clique em **DNS**.

2.  Na árvore de console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 será instalado.

3.  Clique em **novo host (A ou aaaa)**.

4.  Clique em **nome**, digite o nome do host do pool (o nome do domínio é presumido na zona em que o registro é definido e não precisa ser inserido como parte do registro a).

5.  Clique em **endereço IP**, digite o IP virtual (VIP) do balanceador de carga do pool de front-ends.
    
    <div>
    

    > [!IMPORTANT]  
    > Em implantações que usam um pool de directors, os registros de host (A) para as URLs simples devem apontar para o VIP do balanceador de carga do diretor.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Se você implantar apenas um servidor ou diretor da Enterprise Edition que esteja conectado à topologia sem um balanceador de carga ou se implantar um servidor Standard Edition, digite o endereço IP do servidor Enterprise Edition, do servidor Standard Edition ou do director. Um balanceador de carga será necessário se você implantar mais de um servidor ou diretor Enterprise Edition em um pool. Balanceadores de carga não são usados com servidores Standard Edition.

    
    </div>

6.  Clique em **Adicionar host**e, em seguida, clique em **OK**.

7.  Para criar um registro adicional adicional, repita as etapas 4 e 5.

8.  Quando terminar de criar todos os registros necessários, clique em **concluído**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

