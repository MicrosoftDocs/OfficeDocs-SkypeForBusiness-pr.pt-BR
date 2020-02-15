---
title: 'Lync Server 2013: configurar armazenamento de arquivo DFS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5ce6be2a3fce1f334e9e4b1d14ea41a3dd57a6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Configurar o armazenamento de arquivos do DFS para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-05-23_

O Lync Server 2013 suporta o uso de compartilhamentos de arquivos em um sistema de arquivos distribuído (DFS). Para obter detalhes sobre o DFS para Windows Server 2008, consulte o guia passo a passo do DFS para o Windows Server [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)2008 em. Para usar um DFS, o Lync Server 2013 requer o seguinte:

  - Namespaces sejam baseados em domínio

  - Todos os servidores de namespace estejam executando um mínimo de Windows 2008

Lync Server 2013 a instalação requer que as permissões em uma pasta compartilhada permitam acesso total ao administrador. O Lync Server 2013 usará as permissões de arquivo NTFS para ACL nas pastas. Permissões de compartilhamento DFS herdadas não serão usadas para acesso restrito.

Para obter mais detalhes sobre os requisitos de compartilhamento de arquivos, consulte [File Storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) na documentação de suporte.

<div>


> [!NOTE]  
> Você pode estar procurando informações sobre como configurar um compartilhamento não DFS. Em caso afirmativo, confira <A href="lync-server-2013-hardware-setup.md">configuração de hardware para o Lync Server 2013</A>.



</div>

O procedimento a seguir descreve como configurar corretamente permissões de pastas compartilhas usando o Assistente de Namespace DFS (como descrito no guia de instalação do DFS)

<div>

## <a name="to-configure-shared-folder-permissions"></a>Para configurar permissões de pastas compartilhadas

1.  clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Ferramentas Administrativas** e clique em **Gerenciamento DFS**.

2.  Na árvore de console do snap-in do Gerenciamento DFS, clique com o botão direito no servidor de namespace (por exemplo, filesrv1.contoso.com) e depois clique em **Editar Configurações**.

3.  Selecione **Permissões de pastas compartilhadas**.

4.  Selecione **Usar permissões personalizadas**.

5.  Para o grupo Administrador, selecione o seguinte sob **Permitir**:
    
      - **Controle total**
    
      - **Alteração**
    
      - **Leitura**

6.  Clique em **Aplicar** e em **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

