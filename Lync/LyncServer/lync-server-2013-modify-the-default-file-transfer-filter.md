---
title: 'Lync Server 2013: modificar o filtro padrão de transferência de arquivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Modificar o filtro de transferência de arquivo padrão no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O Lync Server 2013 fornece um filtro de transferência de arquivo global que bloqueia tipos específicos de arquivos durante as seguintes atividades relacionadas a arquivos em sua implantação do Lync Server 2013:

  - Solicitações de transferência de arquivos durante as conversas de mensagens instantâneas (IM)

  - Uploads e downloads de arquivos durante o uso do recurso folheto no cliente do Office Live Meeting 2007

  - Reprodução de multimídia durante conferências

Dependendo dos tipos de arquivos que você deseja bloquear ou permitir, você pode usar o painel de controle do Lync Server para modificar o filtro global. Para obter detalhes sobre a filtragem de transferência de arquivo, consulte Configurando [a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>Para modificar o filtro de transferência de arquivo padrão

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **mensagens instantâneas e presença** e, em seguida, clique em **filtro de arquivo**.

4.  Na página **filtro de arquivo** , clique duas vezes no filtro **global** .

5.  Em **Editar Filtro de arquivo**, marque a caixa de seleção **habilitar filtro de arquivo** .

6.  Na caixa de listagem suspensa **transferência de arquivo** , clique em **bloquear todos** ou **bloquear tipos de arquivo específicos**.

7.  Se você clicou em **bloquear tudo**, pule para a etapa 9.

8.  Se você clicou em **bloquear tipos de arquivo específicos**, faça o seguinte:
    
    1.  Clique em **selecionar** para modificar a lista padrão de extensões de tipo de arquivo que você deseja bloquear.
    
    2.  Em **Selecionar tipo de arquivo**, selecione os tipos de arquivo que você deseja bloquear ou permitir, adicionando ou removendo suas extensões das categorias em **extensões de tipo de arquivo**.
    
    3.  Se você não vir a extensão para um tipo de arquivo que deseja bloquear, digite a extensão na caixa de texto em **adicionar extensões de tipo de arquivo à lista**e, em seguida, clique em **Adicionar**.
    
    4.  Clique em **OK**.

9.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Criar um novo filtro de URL no Lync Server 2013 para manipular hiperlinks em conversas de mensagens instantâneas](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Modificar o filtro de URL padrão no Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

