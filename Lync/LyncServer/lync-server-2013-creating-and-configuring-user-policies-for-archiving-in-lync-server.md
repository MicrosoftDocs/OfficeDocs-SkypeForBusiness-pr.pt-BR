---
title: Criando e Configurando políticas de usuário para arquivamento no Lync Server
description: Criando e Configurando políticas de usuário para arquivamento no Lync Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dad260910f01e10c71dbbde67af98ea9a207e33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563087"
---
# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Criando e Configurando políticas de usuário para arquivamento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

Para habilitar ou desabilitar o arquivamento para usuários específicos hospedados no Lync Server, você deve primeiro criar uma política de usuário e, em seguida, aplicar a política a um ou mais usuários ou grupos de usuários. Para obter detalhes sobre como aplicar políticas de usuário a usuários específicos e grupos de usuários, consulte [aplicando uma política de arquivamento do Lync Server a um usuário no Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) na documentação de implantação.

Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, na documentação de implantação ou na documentação operações.

<div>


> [!NOTE]
> Se você habilitou a integração do Microsoft Exchange para sua implantação, as políticas de retenção do Exchange In-Place controlam se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e que suas caixas de correio sejam colocadas In-Place isenção. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.<BR>Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Para configurar uma política de arquivamento para usuários hospedados no Lync Server

1.  A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoração e Arquivamento** e em **Política de Arquivamento**.

4.  Clique em **Novo** e em **Política do usuário**.

5.  Em **Nova Política de Arquivamento**, faça o seguinte:
    
      - Em **Nome**, especifique o nome da política de usuário.
    
      - Em **Descrição**, forneça informações sobre a política de usuário (por exemplo, política de usuário do departamento jurídico).
    
      - Para controlar o arquivamento das comunicações internas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
      - Para controlar o arquivamento das comunicações externas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.

6.  Clique em **Confirmar**.

Uma política de usuário aplica-se somente aos usuários aos quais você a atribui. Para obter detalhes sobre como aplicar uma política de usuário a usuários específicos, consulte [aplicando uma política de arquivamento do Lync Server a um usuário no Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) na documentação de implantação.

</div>

</div>

<span> </span>

</div>

</div>

</div>

