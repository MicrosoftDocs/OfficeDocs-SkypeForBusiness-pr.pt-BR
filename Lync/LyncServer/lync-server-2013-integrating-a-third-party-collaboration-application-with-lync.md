---
title: Integrando um aplicativo de colaboração de terceiros com o Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 075c8289a55683b18b0a006319b426c94796f9cd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="83069-102">Integrando um aplicativo de colaboração de terceiros com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83069-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83069-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="83069-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="83069-104">Você pode integrar o Lync 2013 com qualquer aplicativo de colaboração online de terceiros adicionando informações sobre o aplicativo ao registro.</span><span class="sxs-lookup"><span data-stu-id="83069-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="83069-105">Você pode usar o Lync 2013 para iniciar sessões de conferência de dados hospedadas em um servidor interno, um serviço baseado na Internet ou ambos.</span><span class="sxs-lookup"><span data-stu-id="83069-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="83069-106">A colaboração ou sessão de conferência de dados pode ser iniciada a partir da lista de Contatos de uma sessão de IM, voz ou vídeo existente.</span><span class="sxs-lookup"><span data-stu-id="83069-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="83069-107">O Lync 2013 atua somente como o veículo para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="83069-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="83069-108">Todas as conversas existentes do Lync 2013 permanecerão ativas após o início da sessão de colaboração online.</span><span class="sxs-lookup"><span data-stu-id="83069-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="83069-109">As seções a seguir descrevem como integrar o Lync 2013 com aplicativos de colaboração baseados na Internet e no servidor.</span><span class="sxs-lookup"><span data-stu-id="83069-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="83069-110">Integrando um aplicativo de colaboração baseado na Internet com o Lync 2013</span><span class="sxs-lookup"><span data-stu-id="83069-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="83069-111">Normalmente, as etapas envolvidas na integração de um aplicativo de colaboração de terceiros são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="83069-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="83069-112">Informações sobre o aplicativo são adicionadas ao registro.</span><span class="sxs-lookup"><span data-stu-id="83069-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="83069-113">O organizador entra no Lync 2013 e seleciona contatos para compartilhamento de dados e colaboração.</span><span class="sxs-lookup"><span data-stu-id="83069-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="83069-114">O organizador pode também já estar em uma conversa e decide adicionar conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="83069-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="83069-115">O Lync 2013 lê o registro, inicia o aplicativo de colaboração e, em seguida, envia uma mensagem SIP personalizada — um appINVITE — para os participantes selecionados.</span><span class="sxs-lookup"><span data-stu-id="83069-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="83069-116">Os participantes aceitam o convite e o aplicativo de colaboração é inicializado no computador de cada pessoa.</span><span class="sxs-lookup"><span data-stu-id="83069-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="83069-117">O Lync 2013 usa o registro para determinar qual aplicativo de colaboração usar e, em seguida, inicia esse aplicativo usando os parâmetros incluídos na mensagem appINVITE.</span><span class="sxs-lookup"><span data-stu-id="83069-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="83069-118">A tabela a seguir descreve as entradas do Registro necessárias para integrar um aplicativo de colaboração baseado na Internet com o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="83069-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="83069-119">Essas entradas são colocadas no registro no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="83069-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="83069-120">HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\aplicativos\\parâmetros</span><span class="sxs-lookup"><span data-stu-id="83069-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="83069-121">Entradas de Registro para um Aplicativo de Colaboração baseado em Internet</span><span class="sxs-lookup"><span data-stu-id="83069-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83069-122">Nome</span><span class="sxs-lookup"><span data-stu-id="83069-122">Name</span></span></th>
<th><span data-ttu-id="83069-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="83069-123">Type</span></span></th>
<th><span data-ttu-id="83069-124">Dados</span><span class="sxs-lookup"><span data-stu-id="83069-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83069-125">Nome</span><span class="sxs-lookup"><span data-stu-id="83069-125">Name</span></span></p></td>
<td><p><span data-ttu-id="83069-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-127">O nome do aplicativo para os menus do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="83069-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83069-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="83069-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="83069-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-130">Caminho de um ícone com 16 pixels x 16 pixels, BMP ou PNG.</span><span class="sxs-lookup"><span data-stu-id="83069-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83069-131">Path</span><span class="sxs-lookup"><span data-stu-id="83069-131">Path</span></span></p></td>
<td><p><span data-ttu-id="83069-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-133">Caminho de participante para iniciar o aplicativo de colaboração on-line.</span><span class="sxs-lookup"><span data-stu-id="83069-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83069-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="83069-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="83069-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-136">Caminho de organizador para iniciar o aplicativo de colaboração on-line.</span><span class="sxs-lookup"><span data-stu-id="83069-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="83069-137">Este caminho pode conter um ou mais parâmetros personalizados, como definidos na sub-chave Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="83069-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="83069-138">Por exemplo, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="83069-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83069-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="83069-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="83069-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="83069-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="83069-p106">0 = Sessão local. O aplicativo é iniciado no computador local.</span><span class="sxs-lookup"><span data-stu-id="83069-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="83069-143">1 = Sessão de dois participantes (padrão).</span><span class="sxs-lookup"><span data-stu-id="83069-143">1 = Two-party session (default).</span></span> <span data-ttu-id="83069-144">O Lync 2013 inicia o aplicativo localmente e, em seguida, envia uma notificação do sistema para o outro usuário.</span><span class="sxs-lookup"><span data-stu-id="83069-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="83069-145">O outro usuário clica na notificação e inicia o aplicativo especificado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="83069-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="83069-146">2 = Sessão de múltiplas partes.</span><span class="sxs-lookup"><span data-stu-id="83069-146">2 = Multiparty session.</span></span> <span data-ttu-id="83069-147">O Lync 2013 inicia o aplicativo localmente e envia notificações do sistema aos outros usuários, solicitando que eles iniciem o aplicativo especificado em seu próprio computador.</span><span class="sxs-lookup"><span data-stu-id="83069-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83069-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="83069-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="83069-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-p109">Uma lista  de menus onde este comando aparecerá, separada por ponto e vírgula. Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="83069-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="83069-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="83069-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="83069-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="83069-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="83069-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="83069-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="83069-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="83069-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="83069-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="83069-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="83069-157">Se ExtensibleMenu não estiver definido, os valores padrão de MainWindowRightClick e ConversationWindowActions são usados.</span><span class="sxs-lookup"><span data-stu-id="83069-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83069-158">A tabela a seguir descreve as entradas de registro para os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="83069-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="83069-159">Essas entradas são locais no HKEY\_user\_software\\\\User atual\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\apps Parameters.</span><span class="sxs-lookup"><span data-stu-id="83069-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="83069-160">Entradas de Registro para um Aplicativo de Colaboração baseado em Internet</span><span class="sxs-lookup"><span data-stu-id="83069-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83069-161">Nome</span><span class="sxs-lookup"><span data-stu-id="83069-161">Name</span></span></th>
<th><span data-ttu-id="83069-162">Tipo</span><span class="sxs-lookup"><span data-stu-id="83069-162">Type</span></span></th>
<th><span data-ttu-id="83069-163">Dados</span><span class="sxs-lookup"><span data-stu-id="83069-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83069-164">Param1</span><span class="sxs-lookup"><span data-stu-id="83069-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="83069-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-166">Usado no formato de token (<code>%Parm1%</code>) para adicionar valores específicos do usuário à chave do Registro OriginatorPath.</span><span class="sxs-lookup"><span data-stu-id="83069-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83069-167">Param2</span><span class="sxs-lookup"><span data-stu-id="83069-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="83069-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-169">Consulte Param1.</span><span class="sxs-lookup"><span data-stu-id="83069-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83069-170">Param3</span><span class="sxs-lookup"><span data-stu-id="83069-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="83069-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-172">Consulte Param1.</span><span class="sxs-lookup"><span data-stu-id="83069-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83069-173">As configurações de registro de exemplo a seguir integram o cliente de colaboração do ADatum com o Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="83069-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="83069-174">Integrando um aplicativo de colaboração baseado em servidor com o Lync 2013</span><span class="sxs-lookup"><span data-stu-id="83069-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="83069-175">As configurações para adicionar comandos para iniciar um aplicativo de colaboração baseado em servidor no Lync 2013 são semelhantes às descritas na seção anterior, integrando um aplicativo de colaboração baseado na Internet com o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="83069-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="83069-176">No entanto, o OriginatorPath não é exigido e alguns valores são diferentes.</span><span class="sxs-lookup"><span data-stu-id="83069-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="83069-177">As entradas do registro são colocadas no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="83069-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="83069-178">HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\aplicativos\\parâmetros</span><span class="sxs-lookup"><span data-stu-id="83069-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="83069-179">Entradas de Registro de um Aplicativo de Colaboração baseado em Servidor</span><span class="sxs-lookup"><span data-stu-id="83069-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83069-180">Nome</span><span class="sxs-lookup"><span data-stu-id="83069-180">Name</span></span></th>
<th><span data-ttu-id="83069-181">Tipo</span><span class="sxs-lookup"><span data-stu-id="83069-181">Type</span></span></th>
<th><span data-ttu-id="83069-182">Dados</span><span class="sxs-lookup"><span data-stu-id="83069-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83069-183">Nome</span><span class="sxs-lookup"><span data-stu-id="83069-183">Name</span></span></p></td>
<td><p><span data-ttu-id="83069-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-185">Nome do aplicativo conforme aparece no menu.</span><span class="sxs-lookup"><span data-stu-id="83069-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83069-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="83069-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="83069-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="83069-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="83069-188">Valor = 1.</span><span class="sxs-lookup"><span data-stu-id="83069-188">Value = 1.</span></span> <span data-ttu-id="83069-189">Define o tipo de aplicativo como protocolo.</span><span class="sxs-lookup"><span data-stu-id="83069-189">Sets the application type to protocol.</span></span> <span data-ttu-id="83069-190">Os outros valores possíveis não se aplicam neste caso.</span><span class="sxs-lookup"><span data-stu-id="83069-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="83069-191">Se não estiver presente, ApplicationType é definido como 0 (executável).</span><span class="sxs-lookup"><span data-stu-id="83069-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83069-192">Path</span><span class="sxs-lookup"><span data-stu-id="83069-192">Path</span></span></p></td>
<td><p><span data-ttu-id="83069-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-194">Protocolo usado para iniciar o aplicativo de colaboração.</span><span class="sxs-lookup"><span data-stu-id="83069-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="83069-195">Para o Live Meeting 2007, o valor de Path é definido <code>meet:%conf-uri%</code>como.</span><span class="sxs-lookup"><span data-stu-id="83069-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83069-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="83069-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="83069-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="83069-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="83069-p114">0 = Sessão local. O aplicativo é iniciado no computador local.</span><span class="sxs-lookup"><span data-stu-id="83069-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="83069-200">1 = Sessão de dois participantes (padrão).</span><span class="sxs-lookup"><span data-stu-id="83069-200">1 = Two-party session (default).</span></span> <span data-ttu-id="83069-201">O Lync 2013 inicia o aplicativo localmente e, em seguida, envia uma notificação do sistema para o outro usuário.</span><span class="sxs-lookup"><span data-stu-id="83069-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="83069-202">O outro usuário clica na notificação e inicia o aplicativo especificado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="83069-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="83069-203">2 = Sessão de múltiplas partes.</span><span class="sxs-lookup"><span data-stu-id="83069-203">2 = Multiparty session.</span></span> <span data-ttu-id="83069-204">O Lync 2013 inicia o aplicativo localmente e envia notificações do sistema aos outros usuários, solicitando que eles iniciem o aplicativo especificado em seus computadores.</span><span class="sxs-lookup"><span data-stu-id="83069-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83069-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="83069-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="83069-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-207">DATA = O tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="83069-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83069-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="83069-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="83069-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="83069-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="83069-210">Uma lista dos menus onde este comando será exibido, separados por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="83069-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="83069-211">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="83069-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="83069-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="83069-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="83069-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="83069-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="83069-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="83069-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="83069-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="83069-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="83069-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="83069-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="83069-217">Se ExtensibleMenu não estiver definido, os valores padrão de MainWindowRightClick e ConversationWindowActions são usados.</span><span class="sxs-lookup"><span data-stu-id="83069-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83069-218">O exemplo a seguir adiciona comandos para iniciar o ADatum Collaboration Client de dentro do Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="83069-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

