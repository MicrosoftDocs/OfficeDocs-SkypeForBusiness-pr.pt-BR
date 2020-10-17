---
title: 'Lync Server 2013: adicionando comandos aos menus do Lync'
description: 'Lync Server 2013: adicionando comandos aos menus do Lync.'
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
ms.openlocfilehash: ed4d62d085eaf115d107244ae50a7cc69e0aacd5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558227"
---
# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="208d8-103">Adicionando comandos aos menus do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="208d8-103">Adding commands to Lync menus in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="208d8-104">_**Última modificação do tópico:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="208d8-104">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="208d8-105">Você pode adicionar comandos personalizados aos menus do Lync 2013 e passar o URI (Uniform Resource Identifier) do SIP do usuário atual e dos contatos selecionados para o aplicativo que o comando personalizado inicia.</span><span class="sxs-lookup"><span data-stu-id="208d8-105">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="208d8-106">Os comandos adicionados podem aparecer em um ou mais dos seguintes menus:</span><span class="sxs-lookup"><span data-stu-id="208d8-106">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="208d8-107">O menu Ferramentas, na barra de menus da janela principal do Lync</span><span class="sxs-lookup"><span data-stu-id="208d8-107">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="208d8-108">O menu de atalho para contatos na lista de Contatos</span><span class="sxs-lookup"><span data-stu-id="208d8-108">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="208d8-109">O menu mais opções, na janela de conversa</span><span class="sxs-lookup"><span data-stu-id="208d8-109">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="208d8-110">O menu de atalho para pessoas na lista de participantes na janela de Conversas</span><span class="sxs-lookup"><span data-stu-id="208d8-110">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="208d8-111">O menu de opções em um cartão de visitas</span><span class="sxs-lookup"><span data-stu-id="208d8-111">The options menu in a contact card</span></span>

<span data-ttu-id="208d8-112">Você pode definir comandos personalizados para dois tipos de aplicativos — aqueles que:</span><span class="sxs-lookup"><span data-stu-id="208d8-112">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="208d8-113">Aplicam-se somente ao usuário atual e são iniciados no computador local.</span><span class="sxs-lookup"><span data-stu-id="208d8-113">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="208d8-114">Envolvem usuários adicionais, como programas de colaboração online, e devem ser iniciados no computador de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="208d8-114">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="208d8-115">O comando personalizado pode ser chamado das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="208d8-115">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="208d8-116">Selecione um ou mais usuários e escolha o comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="208d8-116">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="208d8-117">Inicie uma conversa com dois ou vários participantes e escolha o comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="208d8-117">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="208d8-118">Para adicionar um comando personalizado</span><span class="sxs-lookup"><span data-stu-id="208d8-118">To add a custom command</span></span>

<span data-ttu-id="208d8-119">Use as configurações do registro na tabela a seguir para adicionar um comando aos menus.</span><span class="sxs-lookup"><span data-stu-id="208d8-119">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="208d8-120">Essas entradas são colocadas no registro em um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="208d8-120">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="208d8-121">Para sistema operacional de 32 bits: HKEY \_ local \_ Machine \\ SOFTWARE \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ apps</span><span class="sxs-lookup"><span data-stu-id="208d8-121">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="208d8-122">Para sistema operacional de 64 bits: HKEY \_ local \_ Machine \\ software \\ Wow6432Node \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ apps</span><span class="sxs-lookup"><span data-stu-id="208d8-122">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="208d8-123">Entradas de Registro de Comandos Personalizados</span><span class="sxs-lookup"><span data-stu-id="208d8-123">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="208d8-124">Nome</span><span class="sxs-lookup"><span data-stu-id="208d8-124">Name</span></span></th>
<th><span data-ttu-id="208d8-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="208d8-125">Type</span></span></th>
<th><span data-ttu-id="208d8-126">Dados</span><span class="sxs-lookup"><span data-stu-id="208d8-126">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="208d8-127">Nome</span><span class="sxs-lookup"><span data-stu-id="208d8-127">Name</span></span></p></td>
<td><p><span data-ttu-id="208d8-128">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="208d8-128">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="208d8-129">Nome do aplicativo conforme aparece no menu.</span><span class="sxs-lookup"><span data-stu-id="208d8-129">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="208d8-130">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="208d8-130">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="208d8-131">DWORD</span><span class="sxs-lookup"><span data-stu-id="208d8-131">DWORD</span></span></p></td>
<td><p><span data-ttu-id="208d8-132">0 = Executável (padrão)</span><span class="sxs-lookup"><span data-stu-id="208d8-132">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="208d8-133">Requer ApplicationInstallPath.</span><span class="sxs-lookup"><span data-stu-id="208d8-133">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="208d8-134">1 = Protocolo</span><span class="sxs-lookup"><span data-stu-id="208d8-134">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="208d8-135">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="208d8-135">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="208d8-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="208d8-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="208d8-137">Caminho completo do executável.</span><span class="sxs-lookup"><span data-stu-id="208d8-137">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="208d8-138">Deve ser especificado se o Tipo de Aplicativo for 0 (Executável).</span><span class="sxs-lookup"><span data-stu-id="208d8-138">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="208d8-139">Path</span><span class="sxs-lookup"><span data-stu-id="208d8-139">Path</span></span></p></td>
<td><p><span data-ttu-id="208d8-140">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="208d8-140">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="208d8-141">Caminho completo a ser iniciado junto com quaisquer parâmetros, incluindo os parâmetros padrão <em>%user-id%</em> e <em>%contact-id%</em>.</span><span class="sxs-lookup"><span data-stu-id="208d8-141">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="208d8-142">SessionType</span><span class="sxs-lookup"><span data-stu-id="208d8-142">SessionType</span></span></p></td>
<td><p><span data-ttu-id="208d8-143">DWORD</span><span class="sxs-lookup"><span data-stu-id="208d8-143">DWORD</span></span></p></td>
<td><p><span data-ttu-id="208d8-p102">0 = Sessão local. O aplicativo é iniciado no computador local.</span><span class="sxs-lookup"><span data-stu-id="208d8-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="208d8-146">1 = Sessão de dois participantes (padrão).</span><span class="sxs-lookup"><span data-stu-id="208d8-146">1 = Two-party session (default).</span></span> <span data-ttu-id="208d8-147">O Lync 2013 inicia o aplicativo localmente e, em seguida, envia uma notificação de área de trabalho para o outro usuário.</span><span class="sxs-lookup"><span data-stu-id="208d8-147">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="208d8-148">O outro usuário clica na notificação para iniciar o aplicativo em seu computador.</span><span class="sxs-lookup"><span data-stu-id="208d8-148">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="208d8-149">2 = Sessão de vários participantes.</span><span class="sxs-lookup"><span data-stu-id="208d8-149">2 = Multiparty session.</span></span> <span data-ttu-id="208d8-150">O Lync 2013 inicia o aplicativo localmente e, em seguida, envia notificações da área de trabalho para os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="208d8-150">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="208d8-151">O outro usuário clica na notificação para iniciar o aplicativo especificado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="208d8-151">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="208d8-152">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="208d8-152">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="208d8-153">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="208d8-153">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="208d8-154">Uma lista dos menus onde este comando será exibido, separados por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="208d8-154">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="208d8-155">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="208d8-155">Possible values are:</span></span></p>
<p><span data-ttu-id="208d8-156">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="208d8-156">MainWindowActions</span></span></p>
<p><span data-ttu-id="208d8-157">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="208d8-157">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="208d8-158">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="208d8-158">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="208d8-159">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="208d8-159">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="208d8-160">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="208d8-160">ContactCardMenu</span></span></p>
<p><span data-ttu-id="208d8-161">Se ExtensibleMenu não estiver definido, os valores padrão de MainWindowRightClick e ConversationWindowActions são usados.</span><span class="sxs-lookup"><span data-stu-id="208d8-161">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="208d8-162">Por exemplo, o arquivo do Editor do Registro (.REG) a seguir mostra os resultados de adicionar o item Gerente de Contatos de Vendas da Contoso ao menu Ações na janela de Conversas:</span><span class="sxs-lookup"><span data-stu-id="208d8-162">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="208d8-163">Para acessar um comando personalizado</span><span class="sxs-lookup"><span data-stu-id="208d8-163">To access a custom command</span></span>

<span data-ttu-id="208d8-164">Para acessar um comando personalizado depois de adicionado, siga um destes procedimentos, dependendo dos valores de ExtensibleMenu que você definir:</span><span class="sxs-lookup"><span data-stu-id="208d8-164">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="208d8-165">**MainWindowActions**     Na janela principal do Lync, clique em **ferramentas**e em seu comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="208d8-165">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="208d8-166">**MainWindowRightClick**     Na janela principal do Lync, clique com o botão direito em um contato e clique em seu comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="208d8-166">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="208d8-167">**ConversationWindowActions**     Na janela de conversa, clique no ícone **mais opções** e, em seguida, clique em seu comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="208d8-167">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="208d8-168">**ConversationWindowRightClick**     Na janela de conversa, clique com o botão direito do mouse em um nome de contato e clique em seu comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="208d8-168">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

