---
title: 'Lync Server 2013: Apêndice B: gerenciando um aparelho de filial persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a766ae86d4c74d874f1db747c137f54cf568d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523218"
---
# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Apêndice B: gerenciando um aparelho de filial persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

Este tópico descreve os procedimentos para o gerenciamento de um aparelho de filial persistente. Especificamente, como substituir e renomear um aparelho de filial persistente e como alterar o pool de front-ends do Lync Server 2013 ao qual o aparelho de filial persistente está associado.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Para substituir um aplicativo de filial persistente

1.  Pare todos os serviços do Lync Server 2013 no aparelho de filial persistente. (Consulte a documentação do fornecedor do Aparelho de Filial Persistente.)

2.  Recomenda Remova o aparelho de filial persistente do domínio.

3.  Exclua o objeto de computador aparelho de filial persistente nos serviços de domínio do Active Directory, seguindo estas etapas:
    
      - Faça logon em um servidor membro como um membro do grupo Administração de Empresa.
    
      - Clique em **Iniciar**, depois em **Ferramentas Administrativas** e, em seguida, clique em **Usuários e Computadores do Active Directory**.
    
      - Clique com o botão direito do mouse no objeto aparelho de filial persistente e clique em **excluir**.

4.  Adicione novamente o objeto computador de aparelho de filial persistente. (Consulte [Adicionar um aparelho de filial persistente ao Active Directory no Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)

5.  Aguarde a replicação do Active Directory.

6.  Abra o Shell de gerenciamento do Lync Server e digite **Enable-CSTopology**.

7.  Conecte o novo aparelho de filial persistente à rede e siga as etapas em [implantando um servidor ou aparelho de filial persistente com o Lync server 2013 – tarefas de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implantar um aparelho de filial persistente ou servidor com o Lync Server 2013-tarefa do site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Para renomear um aplicativo de filial persistente

1.  Mova os usuários para o site central. Para obter detalhes, consulte [move users to a outro pool no Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Pare todos os serviços do Lync Server 2013 no aparelho de filial persistente. (Consulte a documentação do fornecedor do Aparelho de Filial Persistente.)

3.  Remova o aparelho de filial persistente da topologia, seguindo estas etapas:
    
      - Clique em **Iniciar **, em **Todos os Programas **, em **Microsoft Lync Server 2010 ** e em **Construtor de Topologia do Lync Server**.
    
      - Na árvore do console, expanda **Branch sites**, clique no aparelho de filial persistente e, em seguida, clique em **excluir** no painel ação.

4.  Remova o aparelho de filial persistente do domínio.

5.  Exclua o objeto de computador aparelho de filial persistente no Active Directory, seguindo estas etapas:
    
      - Faça logon em um controlador de domínio como membro do grupo Administração de Empresa.
    
      - Clique em **Iniciar**, depois em **Ferramentas Administrativas** e, em seguida, clique em **Usuários e Computadores do Active Directory**.
    
      - Clique com o botão direito do mouse no objeto aparelho de filial persistente e clique em **excluir**.

6.  Restaure o aparelho de filial persistente para os padrões de fábrica. (Consulte a documentação do fornecedor do Aparelho de Filial Persistente.)

7.  Siga as etapas em [implantando um servidor ou aparelho de filial persistente com o Lync server 2013-tarefas do site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implantar um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefa do site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Mova os usuários para o aparelho de filial persistente renomeado. Para obter detalhes, consulte [move users to a outro pool no Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Para alterar o pool de front-end do Lync Server que o aplicativo de filial persistente está associado

1.  Mova os usuários do aparelho de filial persistente para o pool de front-ends do Lync Server no site central. Para obter detalhes, consulte [move users to a outro pool no Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Pare todos os serviços do Lync Server no aparelho de filial persistente. (Consulte a documentação do fornecedor do aparelho de filial persistente).

3.  Atualize o pool de front-ends do Lync Server ao qual o aparelho de filial persistente está associado, seguindo estas etapas:
    
      - Clique em **Iniciar **, em **Todos os Programas **, em **Microsoft Lync Server 2010 ** e em **Construtor de Topologia do Lync Server**.
    
      - Expanda **Sites de filial**.
    
      - Clique com o botão direito do mouse no objeto aparelho de filial persistente para modificar e clique em **Editar propriedades**
    
      - Em resiliência, selecione o novo pool de front-ends ao qual o aparelho de filial persistente está associado e clique em **Avançar**.
    
      - Na árvore do console, clique com o botão direito do mouse no novo dispositivo de filial persistente, clique em **topologia**e em **publicar**.

4.  Reinicie todos os serviços do Lync Server no aparelho de filial persistente.

5.  Teste o aparelho de filial persistente. Para obter detalhes, consulte [usuários domésticos em um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Mova os usuários do pool de front-ends do Lync Server no site central para o aparelho de filial persistente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

