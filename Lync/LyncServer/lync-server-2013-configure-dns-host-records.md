---
title: 'Lync Server 2013: Configurar registros de host DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e96c23741430f17b6d343606526df230f74c032
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537128"
---
# <a name="configure-dns-host-records-for-lync-server-2013"></a>Configurar registros de host DNS para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

Para concluir com êxito este procedimento, você deve estar conectado no servidor ou domínio no mínimo como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.

<div>

## <a name="to-configure-dns-host-a-records"></a>Para configurar registros do Host DNS A

1.  No servidor DNS (Sistema de Nomes de Domínio), clique em **Iniciar**, em **Ferramentas Administrativas** e em **DNS**.

2.  Na árvore do console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 será instalado.

3.  Clique em **Novo Host (A ou AAAA)**.

4.  Clique em **Nome**, digite o nome do host para o pool (o nome de domínio é considerado da zona na qual o registro está definido e não precisa ser inserida como parte do registro A).

5.  Clique em **endereço IP**, digite o IP virtual (VIP) do balanceador de carga para o pool de front-ends.
    
    <div>
    

    > [!IMPORTANT]  
    > Nas implantações que usam um pool do Diretor, os registros do host (A) para URLs simples devem apontar para o VIP do balanceador de carga do Diretor.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Se você implantar apenas um servidor Enterprise Edition ou Diretor que esteja conectado à topologia sem um balanceador de carga, ou se você implantar um servidor Standard Edition, digite o endereço IP do servidor Enterprise Edition, o servidor Standard Edition ou o Diretor. Um balanceador de carga será necessário se você implantar mais de um servidor Enterprise Edition ou Diretor em um pool. Os balanceadores de carga não são usados com servidores Standard Edition.

    
    </div>

6.  Clique em **Adicionar Host** e em **OK**.

7.  Para criar um registro A adicional, repita as etapas 4 e 5.

8.  Após criar todos os registros A necessários, clique em **Concluído**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

