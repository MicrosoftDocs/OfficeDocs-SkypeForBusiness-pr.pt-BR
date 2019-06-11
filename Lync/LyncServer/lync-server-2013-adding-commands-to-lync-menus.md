---
title: 'Lync Server 2013: adicionar comandos aos menus do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Adicionar comandos aos menus do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-04-11_

Você pode adicionar comandos personalizados aos menus do Lync 2013 e passar o URI (Uniform Resource Identifier) do SIP do usuário atual e os contatos selecionados para o aplicativo que o comando personalizado inicia.

Os comandos personalizados que você adiciona podem aparecer em um ou mais dos seguintes menus:

  - O menu ferramentas, na barra de menus da janela principal do Lync

  - O menu de atalho para contatos na lista de contatos

  - O menu mais opções, na janela de conversa

  - O menu de atalho para as pessoas listadas na lista de participantes da janela de conversa

  - O menu opções em um cartão de visita

Você pode definir comandos personalizados para dois tipos de aplicativos — aplicativos que executam um dos seguintes procedimentos:

  - Aplicar somente ao usuário atual e são iniciados no computador local.

  - Envolver usuários adicionais, como um programa de colaboração online, e deve ser iniciado no computador de cada usuário.

O comando personalizado pode ser invocado das seguintes maneiras:

  - Selecione um ou mais usuários e, em seguida, escolha o comando personalizado.

  - Inicie uma conversa entre duas pessoas ou vários participantes e, em seguida, escolha o comando personalizado.

<div>

## <a name="to-add-a-custom-command"></a>Para adicionar um comando personalizado

Use as configurações do registro na tabela a seguir para adicionar um comando aos menus. Essas entradas são colocadas no registro em um dos seguintes locais:

  - Para o sistema operacional de\_32\_bits\\:\\hKey\\local\\Machine\\software\\Microsoft Office\\15,0 Lync SessionManager apps

  - Para OS sistemas operacionais de\_64\_bits\\:\\hKey\\local\\Machine\\software\\Wow6432Node\\Microsoft Office\\15,0 Lync SessionManager apps

### <a name="custom-command-registry-entries"></a>Entradas de registro de comando personalizado

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Dados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nome do aplicativo exibido no menu.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DUPLA</p></td>
<td><p>0 = executável (padrão)</p>
<div>

> [!NOTE]  
> Requer ApplicationInstallPath.


</div>
<p>1 = protocolo</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Caminho completo do executável.</p>
<div>

> [!NOTE]  
> Deve ser especificado se ApplicationType for 0 (executável).


</div></td>
</tr>
<tr class="even">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Caminho completo para ser iniciado juntamente com qualquer parâmetro, incluindo os parâmetros padrão <em>% User-ID%</em> e <em>% Contact-ID%</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DUPLA</p></td>
<td><p>0 = sessão local. O aplicativo é iniciado no computador local.</p>
<p>1 = sessão de dois participantes (padrão). O Lync 2013 inicia o aplicativo localmente e, em seguida, envia uma notificação da área de trabalho para o outro usuário. O outro usuário clica na notificação para iniciar o aplicativo em seu computador.</p>
<p>2 = sessão com vários participantes. O Lync 2013 inicia o aplicativo localmente e, em seguida, envia notificações da área de trabalho para os outros usuários. O outro usuário clica na notificação para iniciar o aplicativo especificado em seu computador.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Uma lista dos menus em que esse comando será exibido, separados por ponto-e-vírgula. Os valores possíveis são:</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Se ExtensibleMenu não for definido, os valores padrão de MainWindowRightClick e ConversationWindowActions serão usados.</p></td>
</tr>
</tbody>
</table>


Por exemplo, o seguinte editor de registro (. REG) mostra os resultados da adição de um item de menu do Gerenciador de contatos de vendas da Contoso ao menu ações na janela de conversa:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a>Para acessar um comando personalizado

Para acessar um comando personalizado após ele ser adicionado, siga um destes procedimentos, dependendo dos valores de ExtensibleMenu que você definir:

  - **MainWindowActions**   na janela principal do Lync, clique em **ferramentas**e, em seguida, clique em seu comando personalizado.

  - **MainWindowRightClick**   na janela principal do Lync, clique com o botão direito do mouse em um contato e clique no comando personalizado.

  - **ConversationWindowActions**   na janela de conversa, clique no ícone **mais opções** e, em seguida, clique em seu comando personalizado.

  - **ConversationWindowRightClick**   na janela de conversa, clique com o botão direito do mouse no nome de um contato e, em seguida, clique em seu comando personalizado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

