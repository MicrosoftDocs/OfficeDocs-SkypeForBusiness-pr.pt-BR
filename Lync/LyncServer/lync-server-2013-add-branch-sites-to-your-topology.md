---
title: 'Lync Server 2013: adicionar sites de filial à sua topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d4e024ed5cdb29bb8a8a4170b89399f955254bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Adicionar sites de filial à sua topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

Os sites de filial representam os escritórios de filial físicos que estão conectados aos escritórios principais por um link WAN link. Para adicionar um site de filial à sua topologia do Lync, execute este procedimento no site central.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>Para adicionar sites de filiais à sua topologia

1.  Clique em **Iniciar**, **Todos os programas**, **Microsoft Lync Server** e em **Construtor de topologias do Lync Server**.

2.  Na árvore do console, expanda o site central, clique com o botão direito do mouse em **Sites de filia** e clique em **Novo site de filial**.

3.  Na caixa de diálogo **Definir Novo Site de Filial**, clique em **Nome** e digite o nome do site de filial.

4.  (Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.

5.  Clique em **Avançar**.

6.  (Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações:
    
      - Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.
    
      - Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.
    
      - Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.

7.  Clique em **Avançar** e execute uma das seguintes ações:
    
      - Se você estiver usando um aparelho ou servidor de filial persistente neste site, certifique-se de que a caixa de seleção **abrir o novo assistente persistente quando este assistente for fechado** estiver marcada, clique em **concluir**e siga as instruções do assistente que é aberto. Para obter informações sobre itens de assistente, consulte [definir um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Se você não estiver usando um Aparelho de Filial Persistente ou Servidor nesse site, desmarque a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.

8.  Repita as etapas anteriores para cada site de filial que deseja adicionar à topologia.

**Próxima etapa:**

Para servidores ou aplicativos de filial persistentes: [definir um servidor ou aparelho de filial persistente no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Para conectividade PSTN não resiliente: [definir um gateway PSTN para um site de filial no Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)ou [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

