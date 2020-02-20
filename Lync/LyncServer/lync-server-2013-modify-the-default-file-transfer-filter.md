---
title: 'Lync Server 2013: modificar o filtro de transferência de arquivo padrão'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998e14fc0f30b29d0477dc1363f03a84a7ffe775
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Modificar o filtro de transferência de arquivo padrão no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O Lync Server 2013 fornece um filtro de transferência de arquivo global que bloqueia tipos específicos de arquivos durante as seguintes atividades relacionadas a arquivos em sua implantação do Lync Server 2013:

  - Solicitações de transferência de arquivo durante conversas de mensagens instantâneas (IM)

  - Carregamentos de arquivo e downloads durante o uso do recurso do folheto do cliente do Office Live Meeting 2007

  - Reprodução de multimídia durante conferências

Dependendo dos tipos de arquivos que você deseja bloquear ou permitir, você pode usar o painel de controle do Lync Server para modificar o filtro global. Para obter detalhes sobre a filtragem de transferência de arquivo, consulte [Configuring File Transfer and URL Filter for im (mensagens instantâneas) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>Para modificar o filtro de transferência de arquivo padrão

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **IM e Presença** e em **Filtro de Arquivos**.

4.  Na página **Filtro de Arquivo**, clique duas vezes no filtro **Global**.

5.  Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Habilitar filtro de arquivo**.

6.  Na caixa de listagem suspensa **Transferência de arquivos**, clique em **Bloquear tudo** ou em **Bloquear tipos de arquivo específicos**.

7.  Se você clicou em **Bloquear Tudo**, pule para a etapa 9.

8.  Se você clicou em **Bloquear tipos de arquivos específicos**, faça o seguinte:
    
    1.  Clique em **Selecionar** para modificar a lista padrão de extensões do tipo de arquivo que você deseja bloquear.
    
    2.  Em **Selecionar Tipo de Arquivo**, selecione os tipos de arquivo que você deseja bloquear ou permitir adicionando ou removendo suas extensões das categorias em **Extensões do tipo de arquivo**.
    
    3.  Se você não ver a extensão para um tipo de arquivo que deseja bloquear, digite a extensão na caixa de texto em **Adicionar extensões do tipo de arquivo à lista** e clique em **Adicionar**.
    
    4.  Clique em **OK**.

9.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Criar um novo filtro de URL no Lync Server 2013 para lidar com hiperlinks em conversas de IM](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Modificar o filtro de URL padrão no Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

