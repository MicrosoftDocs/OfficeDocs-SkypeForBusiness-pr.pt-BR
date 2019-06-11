---
title: 'Lync Server 2013: Configurar armazenamento de arquivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c34d0f93e94c954b3ad2ab6cbd472a3d6a40e3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Configurar armazenamento de arquivo para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-05-23_

O Lync Server 2013 oferece suporte ao uso de compartilhamentos de arquivos em um sistema de arquivos distribuídos (DFS). Para obter detalhes sobre o DFS para Windows Server 2008, consulte o guia passo a passo do DFS para Windows Server 2008 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)em. Para usar um DFS, o Lync Server 2013 requer o seguinte:

  - Namespaces são baseados em domínio

  - Todos os servidores de namespace estão executando no mínimo um Windows 2008

O programa de instalação do Lync Server 2013 exige que as permissões em uma pasta compartilhada permitam acesso total ao administrador. O Lync Server 2013 usará as permissões de arquivo NTFS para ACL nas pastas. As permissões de compartilhamento DFS herdadas não serão usadas para restringir o acesso.

Para obter mais detalhes sobre os requisitos de compartilhamento de arquivos, consulte [suporte de armazenamento de arquivos no Lync Server 2013](lync-server-2013-file-storage-support.md) na documentação de suporte.

<div>


> [!NOTE]  
> Você pode estar procurando por informações sobre como configurar um compartilhamento não DFS. Em caso afirmativo, confira <A href="lync-server-2013-hardware-setup.md">a configuração de hardware do Lync Server 2013</A>.



</div>

O procedimento a seguir descreve como configurar corretamente as permissões de pasta compartilhada usando o assistente de namespace do DFS (conforme descrito no guia de configuração do DFS).

<div>

## <a name="to-configure-shared-folder-permissions"></a>Para configurar permissões de pasta compartilhada

1.  Clique em **Iniciar**, aponte para **todos os programas**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento DFS**.

2.  Na árvore de console do snap-in Gerenciamento DFS, clique com o botão direito do mouse no servidor de namespace (por exemplo, filesrv1.contoso.com) e, em seguida, clique em **Editar configurações**.

3.  Selecione **permissões de pasta compartilhada**.

4.  Selecione **usar permissões personalizadas**.

5.  Para o grupo administrador, selecione o seguinte em **permitir**:
    
      - **Controle total**
    
      - **Alteração**
    
      - **Ler**

6.  Clique em **aplicar**e, em seguida, clique em **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

