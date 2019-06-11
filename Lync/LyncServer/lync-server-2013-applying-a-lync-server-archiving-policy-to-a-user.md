---
title: 'Lync Server 2013: aplicando uma política de arquivamento do Lync Server a um usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295f1a0370372d937b07a38eab51cd43d0ef9f5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>Aplicando uma política de arquivamento do Lync Server a um usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-10_

Depois de criar uma política de usuário do Lync Server, você deve aplicá-la a determinados usuários ou grupos de usuários hospedados no Lync Server 2013 para que ele possa entrar em vigor. Para obter detalhes sobre como criar políticas de usuário para usuários específicos, consulte [criando e Configurando políticas de usuário para arquivamento no Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) na documentação de implantação.

Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.

<div>


> [!NOTE]  
> Para configurar e usar arquivamento, você deve primeiro implantar o arquivamento. Para obter detalhes, consulte Implantando o <A href="lync-server-2013-deploying-archiving.md">arquivamento no Lync Server 2013</A> na documentação de implantação.<BR>Se você tiver habilitado a integração do Microsoft Exchange para a sua implantação, as políticas de bloqueio in-loco do Exchange controlarão se o arquivamento está habilitado para os usuários que estão hospedados no Exchange 2013 e ter suas caixas de correio colocadas no bloqueio in-loco. Para obter detalhes, consulte Configurando <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.<BR>Você deve especificar todas as opções adequadas nas configurações de arquivamento antes de habilitar o arquivamento. Para obter detalhes, consulte Configurando <A href="lync-server-2013-configuring-archiving-options.md">Opções de arquivamento no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>Para aplicar uma política de arquivamento do Lync Server a um usuário

1.  Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server 2013. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários** e procure a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique em conta de usuário, em **Editar** e em **Mostrar detalhes**.

5.  Em **Editar o usuário do Lync Server** na **política**de arquivamento, selecione a política de usuário de arquivamento que você deseja aplicar.
    
    <div>
    

    > [!NOTE]  
    > As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de instalação do servidor padrão. Essas configurações são aplicadas automaticamente pelo servidor.

    
    </div>

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

