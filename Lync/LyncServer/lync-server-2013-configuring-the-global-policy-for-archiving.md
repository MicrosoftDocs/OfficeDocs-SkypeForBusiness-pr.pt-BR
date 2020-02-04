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
ms.openlocfilehash: c14cbb69ce620498e1d804483f97c47da37e8522
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Configurando a política global para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-09_

Quando você implanta seus servidores front-end, o Lync Server cria uma política global para arquivar. Por padrão, o arquivamento está desabilitado na política global. A política global controla se o arquivamento está habilitado para comunicações internas e externas para toda a sua implantação, a menos que você tenha configurado políticas de site ou de usuário, o que substitui a política global, ou se você usa a integração do Microsoft Exchange para alguns ou todos os seus usuários. Se você usar a integração do Microsoft Exchange, a política global não se aplicará a nenhum usuário que estiver hospedado no Exchange 2013 e ter as caixas de correio colocadas no bloqueio in-loco.

Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [como o arquivamento funciona na documentação de planejamento do Lync Server 2013](lync-server-2013-how-archiving-works.md) , documentação de implantação ou documentação de operações.

<div>


> [!NOTE]  
> Se você habilitar a integração do Microsoft Exchange para a implantação, as políticas de bloqueio do Exchange in loco controlarão se o arquivamento está habilitado para os usuários que estão hospedados no Exchange 2013 e ter suas caixas de correio colocadas no bloqueio in-loco. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.<BR>Você deve especificar todas as opções adequadas nas configurações de arquivamento antes de habilitar o arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configurando opções de arquivamento no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Para configurar a política global para arquivamento ao usar bancos de dados de arquivamento do Lync Server

1.  Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server 2013. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.

4.  Na página **Política de Arquivamento**, clique em **Global**, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar Política de Arquivamento - Global**, faça o seguinte:
    
      - Em **Nome**, se não desejar usar o nome padrão da opção Global, especifique um novo nome para a política global.
    
      - Em **Descrição**, forneça informações sobre o que a política é (por exemplo, a Política global para *divisionName*).
    
      - Para controlar o arquivamento de comunicações internas para todos os locais e usuários que não estivem sendo controlados especificamente por meio de uma política de local ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
      - Para controlar o arquivamento de comunicações externas para todos os locais e usuários que não estivem sendo controlados especificamente por meio de uma política de local ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

