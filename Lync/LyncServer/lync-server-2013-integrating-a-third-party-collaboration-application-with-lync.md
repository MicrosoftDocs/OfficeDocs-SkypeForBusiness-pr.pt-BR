---
title: Integrando um aplicativo de colaboração de terceiros com o Lync
description: Integração de um aplicativo de colaboração de terceiros com o Lync.
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
ms.openlocfilehash: 7adbe1abab83a569f581af034fc46abfef4cf819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552647"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="1eed1-103">Integrando um aplicativo de colaboração de terceiros com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eed1-103">Integrating a third-party collaboration application with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eed1-104">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1eed1-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1eed1-105">Você pode integrar o Lync 2013 com qualquer aplicativo de colaboração online de terceiros adicionando informações sobre o aplicativo ao registro.</span><span class="sxs-lookup"><span data-stu-id="1eed1-105">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="1eed1-106">Você pode usar o Lync 2013 para iniciar sessões de conferência de dados hospedadas em um servidor interno, um serviço baseado na Internet ou ambos.</span><span class="sxs-lookup"><span data-stu-id="1eed1-106">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="1eed1-107">A colaboração ou sessão de conferência de dados pode ser iniciada a partir da lista de Contatos de uma sessão de IM, voz ou vídeo existente.</span><span class="sxs-lookup"><span data-stu-id="1eed1-107">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="1eed1-108">O Lync 2013 atua somente como o veículo para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1eed1-108">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="1eed1-109">Todas as conversas existentes do Lync 2013 permanecerão ativas após o início da sessão de colaboração online.</span><span class="sxs-lookup"><span data-stu-id="1eed1-109">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="1eed1-110">As seções a seguir descrevem como integrar o Lync 2013 com aplicativos de colaboração baseados na Internet e no servidor.</span><span class="sxs-lookup"><span data-stu-id="1eed1-110">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="1eed1-111">Integrando um aplicativo de colaboração de Internet-Based com o Lync 2013</span><span class="sxs-lookup"><span data-stu-id="1eed1-111">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="1eed1-112">Normalmente, as etapas envolvidas na integração de um aplicativo de colaboração de terceiros são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="1eed1-112">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="1eed1-113">Informações sobre o aplicativo são adicionadas ao registro.</span><span class="sxs-lookup"><span data-stu-id="1eed1-113">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="1eed1-114">O organizador entra no Lync 2013 e seleciona contatos para compartilhamento de dados e colaboração.</span><span class="sxs-lookup"><span data-stu-id="1eed1-114">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="1eed1-115">O organizador pode também já estar em uma conversa e decide adicionar conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="1eed1-115">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="1eed1-116">O Lync 2013 lê o registro, inicia o aplicativo de colaboração e, em seguida, envia uma mensagem SIP personalizada — um appINVITE — para os participantes selecionados.</span><span class="sxs-lookup"><span data-stu-id="1eed1-116">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="1eed1-117">Os participantes aceitam o convite e o aplicativo de colaboração é inicializado no computador de cada pessoa.</span><span class="sxs-lookup"><span data-stu-id="1eed1-117">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="1eed1-118">O Lync 2013 usa o registro para determinar qual aplicativo de colaboração usar e, em seguida, inicia esse aplicativo usando os parâmetros incluídos na mensagem appINVITE.</span><span class="sxs-lookup"><span data-stu-id="1eed1-118">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="1eed1-119">A tabela a seguir descreve as entradas do Registro necessárias para integrar um aplicativo de colaboração baseado na Internet com o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1eed1-119">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="1eed1-120">Essas entradas são colocadas no registro no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="1eed1-120">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="1eed1-121">HKEY \_ local \_ Machine \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ aplicativos \\ parâmetros</span><span class="sxs-lookup"><span data-stu-id="1eed1-121">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="1eed1-122">Entradas de Registro para um Aplicativo de Colaboração baseado em Internet</span><span class="sxs-lookup"><span data-stu-id="1eed1-122">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eed1-123">Nome</span><span class="sxs-lookup"><span data-stu-id="1eed1-123">Name</span></span></th>
<th><span data-ttu-id="1eed1-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="1eed1-124">Type</span></span></th>
<th><span data-ttu-id="1eed1-125">Dados</span><span class="sxs-lookup"><span data-stu-id="1eed1-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eed1-126">Nome</span><span class="sxs-lookup"><span data-stu-id="1eed1-126">Name</span></span></p></td>
<td><p><span data-ttu-id="1eed1-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-128">O nome do aplicativo para os menus do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1eed1-128">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eed1-129">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="1eed1-129">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="1eed1-130">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-130">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-131">Caminho de um ícone com 16 pixels x 16 pixels, BMP ou PNG.</span><span class="sxs-lookup"><span data-stu-id="1eed1-131">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eed1-132">Path</span><span class="sxs-lookup"><span data-stu-id="1eed1-132">Path</span></span></p></td>
<td><p><span data-ttu-id="1eed1-133">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-133">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-134">Caminho de participante para iniciar o aplicativo de colaboração on-line.</span><span class="sxs-lookup"><span data-stu-id="1eed1-134">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eed1-135">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="1eed1-135">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="1eed1-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-137">Caminho de organizador para iniciar o aplicativo de colaboração on-line.</span><span class="sxs-lookup"><span data-stu-id="1eed1-137">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="1eed1-138">Este caminho pode conter um ou mais parâmetros personalizados, como definidos na sub-chave Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="1eed1-138">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="1eed1-139">Por exemplo, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="1eed1-139">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eed1-140">SessionType</span><span class="sxs-lookup"><span data-stu-id="1eed1-140">SessionType</span></span></p></td>
<td><p><span data-ttu-id="1eed1-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="1eed1-141">DWORD</span></span></p></td>
<td><p><span data-ttu-id="1eed1-p106">0 = Sessão local. O aplicativo é iniciado no computador local.</span><span class="sxs-lookup"><span data-stu-id="1eed1-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="1eed1-144">1 = Sessão de dois participantes (padrão).</span><span class="sxs-lookup"><span data-stu-id="1eed1-144">1 = Two-party session (default).</span></span> <span data-ttu-id="1eed1-145">O Lync 2013 inicia o aplicativo localmente e, em seguida, envia uma notificação do sistema para o outro usuário.</span><span class="sxs-lookup"><span data-stu-id="1eed1-145">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="1eed1-146">O outro usuário clica na notificação e inicia o aplicativo especificado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="1eed1-146">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="1eed1-147">2 = Sessão de múltiplas partes.</span><span class="sxs-lookup"><span data-stu-id="1eed1-147">2 = Multiparty session.</span></span> <span data-ttu-id="1eed1-148">O Lync 2013 inicia o aplicativo localmente e envia notificações do sistema aos outros usuários, solicitando que eles iniciem o aplicativo especificado em seu próprio computador.</span><span class="sxs-lookup"><span data-stu-id="1eed1-148">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eed1-149">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="1eed1-149">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="1eed1-150">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-150">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-p109">Uma lista  de menus onde este comando aparecerá, separada por ponto e vírgula. Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="1eed1-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1eed1-153">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="1eed1-153">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="1eed1-154">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="1eed1-154">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="1eed1-155">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="1eed1-155">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="1eed1-156">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="1eed1-156">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="1eed1-157">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="1eed1-157">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="1eed1-158">Se ExtensibleMenu não estiver definido, os valores padrão de MainWindowRightClick e ConversationWindowActions são usados.</span><span class="sxs-lookup"><span data-stu-id="1eed1-158">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1eed1-159">A tabela a seguir descreve as entradas de registro para os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="1eed1-159">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="1eed1-160">Essas entradas são locais no HKEY \_ \_ User software user atual \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ apps \\ Parameters.</span><span class="sxs-lookup"><span data-stu-id="1eed1-160">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="1eed1-161">Entradas de Registro para um Aplicativo de Colaboração baseado em Internet</span><span class="sxs-lookup"><span data-stu-id="1eed1-161">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eed1-162">Nome</span><span class="sxs-lookup"><span data-stu-id="1eed1-162">Name</span></span></th>
<th><span data-ttu-id="1eed1-163">Tipo</span><span class="sxs-lookup"><span data-stu-id="1eed1-163">Type</span></span></th>
<th><span data-ttu-id="1eed1-164">Dados</span><span class="sxs-lookup"><span data-stu-id="1eed1-164">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eed1-165">Param1</span><span class="sxs-lookup"><span data-stu-id="1eed1-165">Param1</span></span></p></td>
<td><p><span data-ttu-id="1eed1-166">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-166">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-167">Usado no formato de token ( <code>%Parm1%</code> ) para adicionar valores específicos do usuário à chave do Registro OriginatorPath.</span><span class="sxs-lookup"><span data-stu-id="1eed1-167">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eed1-168">Param2</span><span class="sxs-lookup"><span data-stu-id="1eed1-168">Param2</span></span></p></td>
<td><p><span data-ttu-id="1eed1-169">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-169">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-170">Consulte Param1.</span><span class="sxs-lookup"><span data-stu-id="1eed1-170">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eed1-171">Param3</span><span class="sxs-lookup"><span data-stu-id="1eed1-171">Param3</span></span></p></td>
<td><p><span data-ttu-id="1eed1-172">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-172">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-173">Consulte Param1.</span><span class="sxs-lookup"><span data-stu-id="1eed1-173">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1eed1-174">As configurações de registro de exemplo a seguir integram o cliente de colaboração do ADatum com o Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="1eed1-174">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="1eed1-175">Integrando um aplicativo de colaboração de Server-Based com o Lync 2013</span><span class="sxs-lookup"><span data-stu-id="1eed1-175">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="1eed1-176">As configurações para adicionar comandos para iniciar um aplicativo de colaboração baseado em servidor no Lync 2013 são semelhantes às descritas na seção anterior, integrando um aplicativo de colaboração Internet-Based com o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1eed1-176">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="1eed1-177">No entanto, o OriginatorPath não é exigido e alguns valores são diferentes.</span><span class="sxs-lookup"><span data-stu-id="1eed1-177">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="1eed1-178">As entradas do registro são colocadas no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="1eed1-178">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="1eed1-179">HKEY \_ local \_ Machine \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ SessionManager \\ aplicativos \\ parâmetros</span><span class="sxs-lookup"><span data-stu-id="1eed1-179">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="1eed1-180">Entradas de Registro de um Aplicativo de Colaboração baseado em Servidor</span><span class="sxs-lookup"><span data-stu-id="1eed1-180">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eed1-181">Nome</span><span class="sxs-lookup"><span data-stu-id="1eed1-181">Name</span></span></th>
<th><span data-ttu-id="1eed1-182">Tipo</span><span class="sxs-lookup"><span data-stu-id="1eed1-182">Type</span></span></th>
<th><span data-ttu-id="1eed1-183">Dados</span><span class="sxs-lookup"><span data-stu-id="1eed1-183">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eed1-184">Nome</span><span class="sxs-lookup"><span data-stu-id="1eed1-184">Name</span></span></p></td>
<td><p><span data-ttu-id="1eed1-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-185">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-186">Nome do aplicativo conforme aparece no menu.</span><span class="sxs-lookup"><span data-stu-id="1eed1-186">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eed1-187">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="1eed1-187">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="1eed1-188">DWORD</span><span class="sxs-lookup"><span data-stu-id="1eed1-188">DWORD</span></span></p></td>
<td><p><span data-ttu-id="1eed1-189">Valor = 1.</span><span class="sxs-lookup"><span data-stu-id="1eed1-189">Value = 1.</span></span> <span data-ttu-id="1eed1-190">Define o tipo de aplicativo como protocolo.</span><span class="sxs-lookup"><span data-stu-id="1eed1-190">Sets the application type to protocol.</span></span> <span data-ttu-id="1eed1-191">Os outros valores possíveis não se aplicam neste caso.</span><span class="sxs-lookup"><span data-stu-id="1eed1-191">The other possible values do not apply in this case.</span></span> <span data-ttu-id="1eed1-192">Se não estiver presente, ApplicationType é definido como 0 (executável).</span><span class="sxs-lookup"><span data-stu-id="1eed1-192">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eed1-193">Path</span><span class="sxs-lookup"><span data-stu-id="1eed1-193">Path</span></span></p></td>
<td><p><span data-ttu-id="1eed1-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-194">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-195">Protocolo usado para iniciar o aplicativo de colaboração.</span><span class="sxs-lookup"><span data-stu-id="1eed1-195">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="1eed1-196">Para o Live Meeting 2007, o valor de Path é definido como <code>meet:%conf-uri%</code> .</span><span class="sxs-lookup"><span data-stu-id="1eed1-196">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eed1-197">SessionType</span><span class="sxs-lookup"><span data-stu-id="1eed1-197">SessionType</span></span></p></td>
<td><p><span data-ttu-id="1eed1-198">DWORD</span><span class="sxs-lookup"><span data-stu-id="1eed1-198">DWORD</span></span></p></td>
<td><p><span data-ttu-id="1eed1-p114">0 = Sessão local. O aplicativo é iniciado no computador local.</span><span class="sxs-lookup"><span data-stu-id="1eed1-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="1eed1-201">1 = Sessão de dois participantes (padrão).</span><span class="sxs-lookup"><span data-stu-id="1eed1-201">1 = Two-party session (default).</span></span> <span data-ttu-id="1eed1-202">O Lync 2013 inicia o aplicativo localmente e, em seguida, envia uma notificação do sistema para o outro usuário.</span><span class="sxs-lookup"><span data-stu-id="1eed1-202">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="1eed1-203">O outro usuário clica na notificação e inicia o aplicativo especificado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="1eed1-203">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="1eed1-204">2 = Sessão de múltiplas partes.</span><span class="sxs-lookup"><span data-stu-id="1eed1-204">2 = Multiparty session.</span></span> <span data-ttu-id="1eed1-205">O Lync 2013 inicia o aplicativo localmente e envia notificações do sistema aos outros usuários, solicitando que eles iniciem o aplicativo especificado em seus computadores.</span><span class="sxs-lookup"><span data-stu-id="1eed1-205">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eed1-206">MCUType</span><span class="sxs-lookup"><span data-stu-id="1eed1-206">MCUType</span></span></p></td>
<td><p><span data-ttu-id="1eed1-207">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-207">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-208">DATA = O tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="1eed1-208">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eed1-209">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="1eed1-209">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="1eed1-210">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1eed1-210">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="1eed1-211">Uma lista dos menus onde este comando será exibido, separados por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="1eed1-211">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="1eed1-212">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="1eed1-212">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1eed1-213">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="1eed1-213">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="1eed1-214">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="1eed1-214">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="1eed1-215">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="1eed1-215">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="1eed1-216">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="1eed1-216">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="1eed1-217">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="1eed1-217">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="1eed1-218">Se ExtensibleMenu não estiver definido, os valores padrão de MainWindowRightClick e ConversationWindowActions são usados.</span><span class="sxs-lookup"><span data-stu-id="1eed1-218">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1eed1-219">O exemplo a seguir adiciona comandos para iniciar o ADatum Collaboration Client de dentro do Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="1eed1-219">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

