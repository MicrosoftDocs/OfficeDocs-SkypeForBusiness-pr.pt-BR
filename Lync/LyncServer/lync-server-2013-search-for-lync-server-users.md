---
title: 'Lync Server 2013: Pesquisar usuários do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f503736b22453f6c3aafd76bc2fac7211f11dec7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Pesquisar usuários do Lync Server no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-14_

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para o Lync Server 2013. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.

É possível pesquisar por usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory. O procedimento a seguir descreve como usar o painel de controle do Lync Server para pesquisar usuários.

<div>


> [!NOTE]  
> Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos quando você procura por um usuário pelo endereço de email do usuário. Em vez disso, você pode pesquisar usuários especificando um prefixo de endereço SIP, por exemplo, SIP: nome, adicione um filtro de pesquisa e selecione um endereço SIP que contenha um endereço de email parcial ou use o cmdlet <STRONG>Get-CSUser</STRONG> .



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>Para procurar um ou mais usuários

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta Sam, endereço SIP ou URI de linha da conta de usuário que você deseja pesquisar e clique em **Localizar**.

5.  (Opcional) Especifique critérios de busca adicionais para limitar os resultados:
    
    1.  Clique no botão de seta de expansão no canto superior direito da tela acima **resultados da pesquisa**e, em seguida, clique em **Adicionar filtro**.
    
    2.  Insira a propriedade do usuário digitando-a ou clicando na seta na lista suspensa para selecionar uma propriedade do usuário.
    
    3.  Na lista **igual a** , clique em **igual a** ou diferente **de**.
    
    4.  Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e clique em **Localizar**.

6.  Os resultados da pesquisa são exibidos em **resultados da pesquisa**. Você pode selecionar qualquer um ou todos os usuários na lista e realizar tarefas de configuração nos usuários selecionados.

</div>

<div>

## <a name="see-also"></a>Confira também


[Exibindo informações sobre contas de usuário habilitadas para o Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Habilitando e desabilitando usuários para o Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

