---
title: 'Lync Server 2013: configurar políticas de site para arquivamento'
description: 'Lync Server 2013: configurar políticas de site para arquivamento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e5b80b7f62ddc18d418415307457c7f2c4010d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558387"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>Configurando políticas de site para arquivamento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

Você pode habilitar ou desabilitar o arquivamento de sites específicos criando e configurando uma política de arquivamento para cada um desses sites. Uma política de site substitui a política global, mas as políticas de usuário substituem as políticas de site. As políticas de arquivamento só se aplicam se você não usar a integração com o Microsoft Exchange ou, se você usar a integração com o Microsoft Exchange, mas tiver alguns usuários que não estão hospedados no Exchange 2013 e ter suas caixas de correio colocadas em In-Place.

Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works na](lync-server-2013-how-archiving-works.md) documentação de planejamento, documentação de implantação ou documentação de operações do Lync Server 2013.

<div>


> [!NOTE]  
> Se você habilitar a integração do Microsoft Exchange para sua implantação, as políticas de retenção do Exchange In-Place controlará se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e se suas caixas de correio serão colocadas In-Place isenção. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.<BR>Você deve especificar todas as opções adequadas nas configurações de Arquivamento antes de habilitar o Arquivamento de comunicações internas e externas nas políticas de Arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>Para criar uma política de arquivamento para um site

1.  A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013.

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.
    
    Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works na](lync-server-2013-how-archiving-works.md) documentação de planejamento, documentação de implantação ou documentação de operações do Lync Server 2013.

4.  Clique em **Novo** e, em seguida, em **Política de site**.

5.  Em **selecionar um site**, clique no site ao qual a política deve ser aplicada.

6.  Em **Nova Política de Arquivamento**, faça o seguinte:
    
      - Em **nome**, especifique o nome da política de site.
    
      - Em **Descrição**, forneça informações sobre o que é a política de site (por exemplo, política de site para Redmond).
    
      - Para controlar o arquivamento de comunicações internas do site especificado, marque ou desmarque a caixa de seleção **arquivar comunicações internas** .
    
      - Para controlar o arquivamento de comunicações externas para o site especificado, marque ou desmarque a caixa de seleção **arquivar comunicações externas** .

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

