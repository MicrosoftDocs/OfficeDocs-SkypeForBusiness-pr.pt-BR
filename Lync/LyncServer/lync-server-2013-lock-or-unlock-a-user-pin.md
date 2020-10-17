---
title: 'Lync Server 2013: bloquear ou desbloquear um PIN de usuário'
description: 'Lync Server 2013: bloquear ou desbloquear um PIN de usuário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf04be333e9d17dd0a06e6eb98d314c2960c3b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570547"
---
# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a>Bloquear ou desbloquear um PIN de usuário no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Você pode bloquear ou desbloquear o PIN de um usuário na seção **usuários** do painel de controle do Lync Server 2013.

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a>Para bloquear o PIN de um usuário no painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Utilize um dos métodos a seguir para localizar um usuário:
    
      - Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.
    
      - Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.

5.  (Opcional) Especifique critérios de busca adicionais para limitar os resultados:
    
    1.  Clique em **Adicionar filtro**.
    
    2.  Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.
    
    3.  Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
    4.  Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.
        
        <div>
        

        > [!TIP]  
        > Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.

        
        </div>
    
    5.  Clique em **Localizar**.
    
    6.  Clique no usuário, em **Ação** e, em seguida, em **Bloquear PIN**.

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a>Para desbloquear o PIN de um usuário no painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Utilize um dos métodos a seguir para localizar um usuário:
    
      - Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.
    
      - Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.

5.  (Opcional) Especifique critérios de busca adicionais para limitar os resultados:
    
    1.  Clique em **Adicionar filtro**.
    
    2.  Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.
    
    3.  Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
    4.  Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.
        
        <div>
        

        > [!TIP]  
        > Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.

        
        </div>
    
    5.  Clique em **Localizar**.
    
    6.  Clique no usuário, clique em **Ação** e, então, clique em **Desbloquear PIN**.

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Bloqueio e desbloqueio de PINs do usuário usando cmdlets do Windows PowerShell

Você pode bloquear e desbloquear PINs de usuário usando o Windows PowerShell e os cmdlets Lock-CsClientPin e Unlock-CsClientPin. Você pode executar esses cmdlets do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-lock-a-user-pin"></a>Para bloquear um PIN de usuário

  - Para bloquear o PIN de um usuário, utilize o cmdlet Lock-CsClientPin. Por exemplo:
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a>Para desbloquear um PIN de usuário

  - Para desbloquear o PIN de um usuário, utilize o cmdlet Unlock-CsClientPin. Por exemplo:
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

Para obter mais informações, consulte o tópico de ajuda para os cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) e [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

