---
title: Criar um novo filtro de URL para lidar com hiperlinks em conversas de mensagens instantâneas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 889ba5f0582c96fc43445d28bcb669150cfff961
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Criar um novo filtro de URL no Lync Server 2013 para lidar com hiperlinks em conversas de IM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-26_

Além de modificar o filtro de URL global, você pode configurar filtros de URL personalizados para sites individuais em sua implantação do Lync Server 2013. Para obter detalhes sobre a filtragem de URL, consulte [Configurando a transferência de arquivos e filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>Para criar um novo filtro de URL

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **IM e Presença** e clique em **Filtro de URL**.

4.  Na página **Filtro de URL**, clique em **Novo**.

5.  Em **Selecionar um Site**, clique no site para o qual você deseja criar o filtro de URL e clique em **OK**.

6.  Na caixa de diálogo **Novo Filtro de URL**, marque a caixa de seleção **Habilitar Filtro de URL** para habilitar a filtragem de URL para o site.

7.  Para bloquear qualquer URL ativa que contenha um arquivo com uma extensão listada sob **Extensões de tipos de arquivos a serem bloqueadas** em **Editar Filtro de Arquivo**, marque a caixa de seleção **Bloquear URLs com extensão de arquivo**.

8.  Na caixa de listagem suspensa **Prefixo de hiperlink**, clique na opção que corresponde à forma como você deseja lidar com URLs em conversas de mensagem instantânea.
    
    A caixa **Permitir mensagem** permite que uma mensagem de aviso seja enviada ao usuário ao enviar hiperlinks que têm permissão para serem enviados.

9.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Modificar o filtro de transferência de arquivo padrão no Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificar o filtro de URL padrão no Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

