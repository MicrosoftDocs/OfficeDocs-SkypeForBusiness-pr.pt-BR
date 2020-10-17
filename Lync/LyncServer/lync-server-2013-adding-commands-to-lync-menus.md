---
title: 'Lync Server 2013: adicionando comandos aos menus do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 738f745d4f91458b95e95e5cc5770c34ed4e8c88
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521348"
---
# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Adicionando comandos aos menus do Lync no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-04-11_

Você pode adicionar comandos personalizados aos menus do Lync 2013 e passar o URI (Uniform Resource Identifier) do SIP do usuário atual e dos contatos selecionados para o aplicativo que o comando personalizado inicia.

Os comandos adicionados podem aparecer em um ou mais dos seguintes menus:

  - O menu Ferramentas, na barra de menus da janela principal do Lync

  - O menu de atalho para contatos na lista de Contatos

  - O menu mais opções, na janela de conversa

  - O menu de atalho para pessoas na lista de participantes na janela de Conversas

  - O menu de opções em um cartão de visitas

Você pode definir comandos personalizados para dois tipos de aplicativos — aqueles que:

  - Aplicam-se somente ao usuário atual e são iniciados no computador local.

  - Envolvem usuários adicionais, como programas de colaboração online, e devem ser iniciados no computador de cada usuário.

O comando personalizado pode ser chamado das seguintes formas:

  - Selecione um ou mais usuários e escolha o comando personalizado.

  - Inicie uma conversa com dois ou vários participantes e escolha o comando personalizado.

<div>

## <a name="to-add-a-custom-command"></a>Para adicionar um comando personalizado

Use as configurações do registro na tabela a seguir para adicionar um comando aos menus. Essas entradas são colocadas no registro em um dos seguintes locais:

  - Para sistema operacional de 32 bits: HKEY \_ local \_ Machine \\ SOFTWARE \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ apps

  - Para sistema operacional de 64 bits: HKEY \_ local \_ Machine \\ software \\ Wow6432Node \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ apps

### <a name="custom-command-registry-entries"></a>Entradas de Registro de Comandos Personalizados

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
<td><p>Nome do aplicativo conforme aparece no menu.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Executável (padrão)</p>
<div>

> [!NOTE]  
> Requer ApplicationInstallPath.


</div>
<p>1 = Protocolo</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Caminho completo do executável.</p>
<div>

> [!NOTE]  
> Deve ser especificado se o Tipo de Aplicativo for 0 (Executável).


</div></td>
</tr>
<tr class="even">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Caminho completo a ser iniciado junto com quaisquer parâmetros, incluindo os parâmetros padrão <em>%user-id%</em> e <em>%contact-id%</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Sessão local. O aplicativo é iniciado no computador local.</p>
<p>1 = Sessão de dois participantes (padrão). O Lync 2013 inicia o aplicativo localmente e, em seguida, envia uma notificação de área de trabalho para o outro usuário. O outro usuário clica na notificação para iniciar o aplicativo em seu computador.</p>
<p>2 = Sessão de vários participantes. O Lync 2013 inicia o aplicativo localmente e, em seguida, envia notificações da área de trabalho para os outros usuários. O outro usuário clica na notificação para iniciar o aplicativo especificado em seu computador.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Uma lista dos menus onde este comando será exibido, separados por ponto e vírgula. Os valores possíveis são:</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Se ExtensibleMenu não estiver definido, os valores padrão de MainWindowRightClick e ConversationWindowActions são usados.</p></td>
</tr>
</tbody>
</table>


Por exemplo, o arquivo do Editor do Registro (.REG) a seguir mostra os resultados de adicionar o item Gerente de Contatos de Vendas da Contoso ao menu Ações na janela de Conversas:

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

Para acessar um comando personalizado depois de adicionado, siga um destes procedimentos, dependendo dos valores de ExtensibleMenu que você definir:

  - **MainWindowActions**     Na janela principal do Lync, clique em **ferramentas**e em seu comando personalizado.

  - **MainWindowRightClick**     Na janela principal do Lync, clique com o botão direito em um contato e clique em seu comando personalizado.

  - **ConversationWindowActions**     Na janela de conversa, clique no ícone **mais opções** e, em seguida, clique em seu comando personalizado.

  - **ConversationWindowRightClick**     Na janela de conversa, clique com o botão direito do mouse em um nome de contato e clique em seu comando personalizado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

