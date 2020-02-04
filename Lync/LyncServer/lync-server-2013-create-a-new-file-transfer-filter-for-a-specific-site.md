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
ms.openlocfilehash: edaf0afabff9d212cdd3b5353a8e54840979f827
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

Além de modificar o filtro de transferência de arquivo global, você pode configurar filtros de transferência de arquivo personalizados para sites específicos na sua implantação do Lync Server 2013. Para obter detalhes sobre a filtragem de transferência de arquivo, consulte [Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Para criar um filtro de transferência de arquivo para um site específico

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **mensagens instantâneas e presença** e, em seguida, clique em **filtro de arquivo**.

4.  Na página **filtro de arquivo** , clique em **novo**.

5.  Na caixa de diálogo **selecionar um site** , clique no site para o qual você deseja criar o filtro de transferência de arquivo e, em seguida, clique em **OK**.

6.  Em **novo filtro de arquivo**, clique na caixa de seleção **habilitar filtro de arquivo** .

7.  Na caixa de listagem suspensa **transferência de arquivo** , clique em **bloquear tudo** ou **bloquear tipos de arquivos específicos**.

8.  Se você clicou em **bloquear tudo**, pule para a etapa 10.

9.  Se você clicou em **bloquear tipos de arquivo específicos**, faça o seguinte:
    
    1.  Clique em **selecionar** para modificar a lista padrão de extensões de tipo de arquivo que você deseja bloquear.
    
    2.  Na caixa de diálogo **Selecionar tipo de arquivo** , selecione os tipos de arquivo que você deseja bloquear ou permitir, adicionando ou removendo suas extensões das categorias em **extensões de tipo de arquivo**.
    
    3.  Se você não vir a extensão para um tipo de arquivo que deseja bloquear, digite a extensão na caixa de texto em **adicionar extensões de tipo de arquivo à lista**e, em seguida, clique em **Adicionar**.
    
    4.  Clique em **OK**.

10. Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Criar um novo filtro de URL no Lync Server 2013 para manipular hiperlinks em conversas de mensagens instantâneas](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modificar o filtro de transferência de arquivo padrão no Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificar o filtro de URL padrão no Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

