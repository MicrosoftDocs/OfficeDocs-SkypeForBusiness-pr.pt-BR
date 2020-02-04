---
title: 'Lync Server 2013: procurar usuários do Lync Server'
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
ms.openlocfilehash: 7134afbc86134471e8d536b36fc8e28142a64db2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Pesquisar usuários do Lync Server no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-14_

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para o Lync Server 2013. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.

Você pode pesquisar usuários usando o painel de controle do Lync Server ou o snap-in usuários e computadores do Active Directory. O procedimento a seguir descreve como usar o painel de controle do Lync Server para pesquisar usuários.

<div>


> [!NOTE]  
> Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos ao pesquisar por um usuário pelo endereço de email do usuário. Em vez disso, você pode procurar usuários especificando um prefixo de endereço SIP, por exemplo, SIP: Name, adicionar um filtro de pesquisa e selecionar um endereço SIP que contenha um endereço de email parcial ou usar o cmdlet <STRONG>Get-CSUser</STRONG> .



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>Para procurar um ou mais usuários

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta Sam, endereço SIP ou URI da linha da conta de usuário que você deseja pesquisar e clique em **Localizar**.

5.  (Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:
    
    1.  Clique no botão de seta de expansão no canto superior direito da tela acima de **resultados da pesquisa**e, em seguida, clique em **Adicionar filtro**.
    
    2.  Digite a propriedade do usuário digitando-a ou clicando na seta na lista suspensa para selecionar uma propriedade de usuário.
    
    3.  Na lista **igual a** , clique em **igual** ou **não igual a**.
    
    4.  Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e, em seguida, clique em **Localizar**.

6.  Os resultados da pesquisa são exibidos em **resultados da pesquisa**. Você pode selecionar qualquer um dos usuários na lista e executar tarefas de configuração nos usuários selecionados.

</div>

<div>

## <a name="see-also"></a>Confira também


[Exibir informações sobre contas de usuário habilitadas para o Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Habilitando e desabilitando usuários do Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

