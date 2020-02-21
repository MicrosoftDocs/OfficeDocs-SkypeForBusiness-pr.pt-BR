---
title: 'Lync Server 2013: Configurando a política global para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f381aeb1493637dae0f5e25a72e3154bfeb76513
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Configurando a política global para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

Ao implantar seus servidores front-end, o Lync Server cria uma política global para arquivamento. Por padrão, o arquivamento está desabilitado na política global. A política global controla se o arquivamento está habilitado para comunicações internas e externas para toda a sua implantação, a menos que você configure políticas de site ou de usuário, que substituem a política global ou se você usar a integração do Microsoft Exchange para alguns ou todos os seus usuários. Se você usar a integração com o Microsoft Exchange, a política global não se aplicará a nenhum usuário hospedado no Exchange 2013 e as caixas de correio serão colocadas em bloqueio in-loco.

Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works na](lync-server-2013-how-archiving-works.md) documentação de planejamento, documentação de implantação ou documentação de operações do Lync Server 2013.

<div>


> [!NOTE]  
> Se você habilitar a integração com o Microsoft Exchange para sua implantação, as políticas de bloqueio in-loco do Exchange controlarão se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e ter suas caixas de correio colocadas em bloqueio in-loco. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.<BR>Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Para configurar a política global para arquivamento ao utilizar bancos de dados de arquivamento do Lync Server

1.  A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.

4.  Na página **Política de Arquivamento**, clique em **Global**, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar Política de Arquivamento - Global**, faça o seguinte:
    
      - Em **Nome**, se não desejar usar o nome padrão de global, especifique um novo nome para a política global.
    
      - Em **Descrição**, forneça informações sobre o que a política é (por exemplo, a política global para *divisionName*).
    
      - Para controlar o arquivamento de comunicações internas para todos os sites e usuários que não estivem sendo controlados especificamente por meio de uma política de site ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
      - Para controlar o arquivamento de comunicações externas para todos os sites e usuários que não estivem sendo controlados especificamente por meio de uma política de site ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

