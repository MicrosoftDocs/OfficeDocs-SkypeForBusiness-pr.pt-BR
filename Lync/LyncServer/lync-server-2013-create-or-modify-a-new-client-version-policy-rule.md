---
title: 'Lync Server 2013: criar ou modificar uma nova regra de política de versão do cliente'
description: 'Lync Server 2013: criar ou modificar uma nova regra de política de versão do cliente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11ebcf17d5cb14fd519fba8ad36be10894fabdb9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574617"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Criar ou modificar uma nova regra de política de versão do cliente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-21_

As regras de política de versão do cliente definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes e versões de cliente específicos. Você pode criar ou modificar regras individuais para uma política de versão de cliente no painel de controle do Lync Server 2013.

<div>


> [!IMPORTANT]  
> As regras são listadas em ordem de precedência. Por exemplo, se você tiver uma regra que permita que os clientes executando a versão 1,5 se conectem, seguido por uma regra que bloqueia clientes que executam uma versão anterior a 2,0, a primeira regra tem precedência e os clientes executando a versão 1,5 têm permissão para se conectar.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Para criar ou modificar as regras de política de versão do cliente com o painel de controle do Lync Server

1.  [Criar ou modificar uma nova política de versão do cliente no Lync server 2013 com o](lync-server-2013-create-or-modify-a-new-client-version-policy.md) painel de controle do Lync Server.

2.  Na página **Editar política de versão do cliente** , execute um dos seguintes procedimentos:
    
      - Clique em **Nova** para criar uma nova regra de versão de cliente.
    
      - Clique em um dos tipos de cliente definidos na lista e em **Mostrar detalhes**.
    
    <div>
    

    > [!NOTE]  
    > É possível usar caracteres curinga para indicar o tipo de cliente.

    
    </div>

3.  Em **Agente do usuário**, selecione um tipo de cliente.

4.  Em **Número de versão**, faça o seguinte:
    
      - Em **Versão principal**, digite o número que corresponde à versão principal do cliente.
    
      - Em **Versão secundária**, digite o número que corresponde à versão secundária do cliente.
    
      - Em **Compilação**, digite o número que corresponde à versão principal e secundária do cliente.
    
      - Em **Atualização**, digite o número que corresponde à versão atualizada do cliente.
    
    <div>
    

    > [!NOTE]  
    > Você pode usar caracteres curinga para indicar o número da versão do cliente.

    
    </div>

5.  Para especificar a operação correspondente para a versão do cliente especificada nas etapas anteriores, em **Operação de comparação**, clique em um dos seguintes:
    
      - **Igual a**
    
      - **Não é**
    
      - **Mais novo que**
    
      - **Mais novo ou igual a**
    
      - **Mais antigo que**
    
      - **Mais antigo ou igual a**

6.  Para especificar a ação a ser executada quando os critérios nas etapas anteriores forem atendidos, clique em uma das seguintes opções em **Ação**:
    
      - Para permitir o logon do cliente, clique em **Permitir**.
    
      - Para permitir que o cliente faça o login e receba atualizações do Windows Server Update Service ou Microsoft Update, clique em **Permitir e atualizar**. Esta seção está disponível apenas quando o agente de usuário **OC** é selecionado.
        
        <div>
        

        > [!NOTE]  
        > Selecionar esta ação faz com que uma notificação seja exibida na próxima vez que os usuários entrarem no Lync 2013. A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update. Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis.

        
        </div>
    
      - Para permitir que o cliente faça logon e exiba uma mensagem sobre onde baixar outra versão de cliente, clique em **Permitir com URL**. Você especifica a URL posteriormente neste procedimento.
    
      - Para impedir que o cliente faça logon, clique em **Bloquear**.
    
      - Para evitar que o cliente faça o login e permitir que ele receba atualizações do Windows Server Update Service ou Microsoft Update, clique em **Bloquear e atualizar**. Esta ação está disponível apenas quando o agente do usuário **OC** é selecionado.
    
      - Para impedir o cliente de fazer logon e exibir uma mensagem sobre onde baixar outra versão de cliente, clique em **Bloquear com URL**. Você especifica a URL posteriormente neste procedimento.

7.  (Opcional) se você clicou em **Permitir com URL** ou **Bloquear com URL** na etapa anterior, digite a URL de download do cliente para incluir na mensagem em **URL**.

8.  Clique em **OK** e clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

