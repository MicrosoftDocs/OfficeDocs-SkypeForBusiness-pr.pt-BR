---
title: 'Lync Server 2013: criar um novo filtro de transferência de arquivo para um site específico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a374cb234567c5aeb44ce6071f6e67559c5159ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

Além de modificar o filtro de transferência de arquivo global, você pode configurar filtros de transferência de arquivo personalizados para sites específicos em sua implantação do Lync Server 2013. Para obter detalhes sobre a filtragem de transferência de arquivo, consulte [Configuring File Transfer and URL Filter for im (mensagens instantâneas) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Para criar um filtro de transferência de arquivo para um site específico

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **IM e Presença** e em **Filtro de Arquivos**.

4.  Na página **filtro de arquivo** , clique em **novo**.

5.  Na caixa de diálogo **selecionar um site** , clique no site para o qual você deseja criar o filtro de transferência de arquivo e clique em **OK**.

6.  Em **novo filtro de arquivo**, clique na caixa de seleção **habilitar filtro de arquivo** .

7.  Na caixa de listagem suspensa **transferência de arquivo** , clique em **bloquear tudo** ou **bloquear tipos de arquivos específicos**.

8.  Se você clicou em **bloquear tudo**, pule para a etapa 10.

9.  Se você clicou em **Bloquear tipos de arquivos específicos**, faça o seguinte:
    
    1.  Clique em **Selecionar** para modificar a lista padrão de extensões do tipo de arquivo que você deseja bloquear.
    
    2.  Na caixa de diálogo **Selecionar tipo de arquivo** , selecione os tipos de arquivo que você deseja bloquear ou permitir, adicionando ou removendo suas extensões das categorias em **extensões de tipo de arquivo**.
    
    3.  Se você não ver a extensão para um tipo de arquivo que deseja bloquear, digite a extensão na caixa de texto em **Adicionar extensões do tipo de arquivo à lista** e clique em **Adicionar**.
    
    4.  Clique em **OK**.

10. Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Criar um novo filtro de URL no Lync Server 2013 para lidar com hiperlinks em conversas de IM](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modificar o filtro de transferência de arquivo padrão no Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificar o filtro de URL padrão no Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

