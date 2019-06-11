---
title: 'Lync Server 2013: criar ou modificar uma nova regra de política de versão do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Criar ou modificar uma nova regra de política de versão do cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-21_

As regras de política de versão do cliente definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes e versões específicas do cliente. Você pode criar ou modificar regras individuais para uma política de versão do cliente no painel de controle do Lync Server 2013.

<div>


> [!IMPORTANT]  
> As regras são listadas em ordem de prioridade. Por exemplo, se você tiver uma regra que permita que os clientes que executam a versão 1,5 se conectem, seguido por uma regra que bloqueia clientes que executam uma versão anterior a 2,0, a primeira regra tem prioridade e os clientes que executam a versão 1,5 têm permissão para se conectar.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Para criar ou modificar regras de política de versão do cliente com o painel de controle do Lync Server

1.  [Crie ou modifique uma nova política de versão do cliente no Lync server 2013 com o](lync-server-2013-create-or-modify-a-new-client-version-policy.md) painel de controle do Lync Server.

2.  Na página **Editar política de versão do cliente** , siga um destes procedimentos:
    
      - Clique em **novo** para criar uma nova regra de versão do cliente.
    
      - Clique em um dos tipos de cliente definidos na lista e, em seguida, clique em **Mostrar detalhes**.
    
    <div>
    

    > [!NOTE]  
    > Você pode usar caracteres curinga para indicar o tipo de cliente.

    
    </div>

3.  Em **agente do usuário**, selecione um tipo de cliente.

4.  Em **número de versão**, faça o seguinte:
    
      - Na **versão principal**, digite o número que corresponde à versão principal do cliente.
    
      - Em **versão secundária**, digite o número que corresponde à versão secundária do cliente.
    
      - Em **Compilar**, digite o número que corresponde à versão principal e secundária do cliente.
    
      - Em **Atualizar**, digite o número que corresponde à versão atualizada do cliente.
    
    <div>
    

    > [!NOTE]  
    > Você pode usar caracteres curinga para indicar o número da versão do cliente.

    
    </div>

5.  Para especificar a operação correspondente à versão do cliente que você especificou nas etapas anteriores, em **operação de comparação**, clique em uma das seguintes opções:
    
      - **Igual a**
    
      - **Não é**
    
      - **Mais novo que**
    
      - **Mais novo ou igual a**
    
      - **Mais antigo que**
    
      - **Mais antigo ou igual a**

6.  Para especificar a ação a ser executada quando os critérios nas etapas anteriores forem atendidos, clique em um dos seguintes itens em **ação**:
    
      - Para permitir que o cliente faça logon, clique em **permitir**.
    
      - Para permitir que o cliente faça logon e Receba atualizações do Windows Server Update Service ou do Microsoft Update, clique em **permitir e atualizar**. Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.
        
        <div>
        

        > [!NOTE]  
        > Selecionar essa ação faz com que uma notificação seja exibida na próxima vez que os usuários entrarem no Lync 2013. A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update. Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis.

        
        </div>
    
      - Para permitir que o cliente faça logon e exiba uma mensagem sobre onde baixar outra versão do cliente, clique em **permitir com URL**. Você especifica a URL mais adiante neste procedimento.
    
      - Para impedir que o cliente faça logon, clique em **Bloquear**.
    
      - Para impedir que o cliente faça logon e permita que o cliente Receba atualizações do Windows Server Update Service ou do Microsoft Update, clique em **bloquear e atualizar**. Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.
    
      - Para impedir que o cliente faça logon e exiba uma mensagem sobre onde baixar outra versão do cliente, clique em **Bloquear com URL**. Você especifica a URL mais adiante neste procedimento.

7.  Adicionais Se você clicou em **permitir com URL** ou **bloco com URL** na etapa anterior, digite a URL de download do cliente a ser incluída na mensagem em **URL**.

8.  Clique em **OK**e, em seguida, clique em **confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

