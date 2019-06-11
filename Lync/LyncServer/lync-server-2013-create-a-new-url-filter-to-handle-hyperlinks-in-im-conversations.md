---
title: Criar um novo filtro de URL para manipular hiperlinks em conversas de mensagens instantâneas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8f9a06dd80f87f2758269ddd2d468aeae2014d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Criar um novo filtro de URL no Lync Server 2013 para manipular hiperlinks em conversas de mensagens instantâneas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-26_

Além de modificar o filtro de URL global, você pode configurar filtros de URL personalizados para sites individuais na implantação do Lync Server 2013. Para obter detalhes sobre a filtragem de URL, consulte Configurando [a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>Para criar um novo filtro de URL

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **mensagens instantâneas e presença**e, em seguida, clique em **filtro de URL**.

4.  Na página **filtro de URL** , clique em **novo**.

5.  Em **selecionar um site**, clique no site para o qual você deseja criar o filtro de URL e, em seguida, clique em **OK**.

6.  Na caixa de diálogo **novo filtro de URL** , marque a caixa de seleção **habilitar filtro de URL** para habilitar a filtragem de URL do site.

7.  Para bloquear qualquer URL ativa que contenha um arquivo com uma extensão listada em **extensões de tipo de arquivo para bloquear** no **filtro de arquivo de edição**, marque a caixa de seleção **Bloquear URLs com extensão de arquivo** .

8.  Na caixa de listagem suspensa **prefixo do hiperlink** , clique na opção que corresponde à maneira como você deseja manipular URLs nas conversas de mensagem instantânea.
    
    A caixa de **mensagem permitir** permite que uma mensagem de aviso seja enviada ao usuário ao enviar hiperlinks que podem ser enviados.

9.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Modificar o filtro de transferência de arquivo padrão no Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificar o filtro de URL padrão no Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

