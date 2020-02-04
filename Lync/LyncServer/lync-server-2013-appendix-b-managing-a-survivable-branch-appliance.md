---
title: 'Lync Server 2013: Anexo B: Gerenciando um Aplicativo de Filial Persistente'
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
ms.openlocfilehash: b16d4c55197785a6df12ad2031dbd2e624501ebd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Anexo B: Gerenciando um Aplicativo de Filial Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

Este tópico descreve os procedimentos para gerenciar um aparelho de ramificação sobreviventes. Especificamente, como substituir e renomear um aparelho de ramificação sobreviventes e como alterar o pool de front-ends do Lync Server 2013 ao qual o aparelho de ramificação sobreviventes está associado.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Para substituir um aparelho de ramificação sobreviventes

1.  Pare todos os serviços do Lync Server 2013 no aparelho de ramificação sobreviventes. (Consulte a documentação do fornecedor da solução ramificada da ramificação.)

2.  Usar Remova o aparelho de ramificação sobreviventes do domínio.

3.  Exclua o objeto de computador de aparelho de ramificação sobreviventes nos serviços de domínio Active Directory, seguindo estas etapas:
    
      - Faça logon em um servidor membro como membro do grupo Administradores da empresa.
    
      - Clique em **Iniciar**, em **Ferramentas administrativas**e em **usuários e computadores do Active Directory**.
    
      - Clique com o botão direito do mouse no objeto de aparelho de ramificação sobreviventes e clique em **excluir**.

4.  Adicione o objeto de computador de aparelho de ramificação sobreviventes novamente. (Consulte [Adicionar um aparelho de ramificação sobreviventes ao Active Directory no Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)

5.  Aguarde a duplicação do Active Directory ocorrer.

6.  Abra o Shell de gerenciamento do Lync Server e digite **Enable-CSTopology**.

7.  Conecte o novo aplicativo de ramificação sobreviventes à rede e siga as etapas em [implantando um aplicativo ou aplicativo de ramificação sobreviventes com o Lync server 2013 – tarefas de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implante um aplicativo ou aplicativo de ramificação sobreviventes com o Lync Server 2013-tarefa de site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Para renomear um aparelho de ramificação sobreviventes

1.  Mover usuários para o site central. Para obter detalhes, consulte [mover usuários para outro pool no Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Pare todos os serviços do Lync Server 2013 no aparelho de ramificação sobreviventes. (Consulte a documentação do fornecedor da solução ramificada da ramificação.)

3.  Remova o aparelho de ramificação sobreviventes da topologia seguindo estas etapas:
    
      - Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server**e, em seguida, clique em **Construtor de topologia do Lync Server**.
    
      - Na árvore do console, expanda **Branch sites**, clique no aparelho da ramificação sobreviventes e clique em **excluir** no painel ação.

4.  Remova o aparelho de ramificação sobreviventes do domínio.

5.  Exclua o objeto de computador de aparelho de ramificação sobreviventes do Active Directory seguindo estas etapas:
    
      - Faça logon em um controlador de domínio como membro do grupo Administradores da empresa.
    
      - Clique em **Iniciar**, em **Ferramentas administrativas**e em **usuários e computadores do Active Directory**.
    
      - Clique com o botão direito do mouse no objeto de aparelho de ramificação sobreviventes e clique em **excluir**.

6.  Restaure o aparelho de ramificação sobreviventes para os padrões de fábrica. (Consulte a documentação do fornecedor da solução ramificada da ramificação.)

7.  Siga as etapas em [implantando um aplicativo ou aplicativo de ramificação sobreviventes com o Lync server 2013 – tarefas de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implante um aplicativo ou aplicativo de ramificação sobreviventes com o Lync Server 2013-tarefa do site de filial](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Mover usuários para o aparelho de ramificação renomeado. Para obter detalhes, consulte [mover usuários para outro pool no Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Para alterar o pool de front-ends do Lync Server ao qual o aparelho de ramificação sobreviventes está associado

1.  Mova os usuários do aparelho de ramificação sobreviventes para o pool de front-ends do Lync Server no site central. Para obter detalhes, consulte [mover usuários para outro pool no Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Pare todos os serviços do Lync Server no aparelho de ramificação sobreviventes. (Consulte a documentação do fornecedor da solução ramificada da ramificação).

3.  Atualize o pool de front-ends do Lync Server ao qual o aparelho de ramificação sobreviventes está associado, seguindo estas etapas:
    
      - Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server**e, em seguida, clique em **Construtor de topologia do Lync Server**.
    
      - Expanda **sites de filiais**.
    
      - Clique com o botão direito do mouse no objeto de aparelho de ramificação sobreviventes para modificar e clique em **Editar propriedades** .
    
      - Em resiliência, selecione o novo pool de front-ends ao qual o aparelho de ramificação sobreviventes deve estar associado e clique em **Avançar**.
    
      - Na árvore de console, clique com o botão direito do mouse no novo aplicativo de ramificação sobreviventes, clique em **topologia**e, em seguida, clique em **publicar**.

4.  Reinicie todos os serviços do Lync Server no aparelho de ramificação sobreviventes.

5.  Teste o aparelho de ramificação sobreviventes. Para obter detalhes, consulte [usuários residenciais em um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Mova os usuários do pool de front-ends do Lync Server no site central para o aparelho de ramificação sobreviventes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

