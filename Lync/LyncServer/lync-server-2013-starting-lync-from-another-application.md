---
title: 'Lync Server 2013: Iniciando o Lync a partir de outro aplicativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dafb8295d3070cd9f38e8691e654146978156d45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="a437c-102">Iniciando o Lync a partir de outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="a437c-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a437c-103">_**Tópico da última modificação:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a437c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a437c-104">Você pode usar parâmetros de linha de comando para iniciar rapidamente o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a437c-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="a437c-105">Por exemplo, se um usuário clicar em um número de telefone em outro aplicativo, o aplicativo poderá iniciar uma instância do Lync 2013 e iniciar uma chamada para esse número.</span><span class="sxs-lookup"><span data-stu-id="a437c-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="a437c-106">O Lync 2013 também pode reconhecer uma lista delimitada por ponto-e-vírgula de nomes de contatos para conferência multiparte.</span><span class="sxs-lookup"><span data-stu-id="a437c-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="a437c-107">Se o Lync 2013 estiver configurado para entrar automaticamente quando iniciado, iniciar o Lync 2013 com parâmetros de linha de comando abrirá a janela principal do Lync.</span><span class="sxs-lookup"><span data-stu-id="a437c-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="a437c-108">Se o Lync não estiver configurado para entrar automaticamente quando iniciado, a janela de entrada será aberta.</span><span class="sxs-lookup"><span data-stu-id="a437c-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="a437c-109">A tabela a seguir mostra os parâmetros disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a437c-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="a437c-110">Parâmetros de linha de comando do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a437c-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a437c-111">Prorroga</span><span class="sxs-lookup"><span data-stu-id="a437c-111">Extension</span></span></th>
<th><span data-ttu-id="a437c-112">Formato dos dados</span><span class="sxs-lookup"><span data-stu-id="a437c-112">Format of Data</span></span></th>
<th><span data-ttu-id="a437c-113">Ação</span><span class="sxs-lookup"><span data-stu-id="a437c-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a437c-114">telefone</span><span class="sxs-lookup"><span data-stu-id="a437c-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="a437c-115">URI do Tel</span><span class="sxs-lookup"><span data-stu-id="a437c-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="a437c-116">Abre a janela de conversa para uma chamada de áudio, mas não disca o número especificado.</span><span class="sxs-lookup"><span data-stu-id="a437c-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a437c-117">callto</span><span class="sxs-lookup"><span data-stu-id="a437c-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="a437c-118">Tel:, SIP: ou URI de Tel digitado</span><span class="sxs-lookup"><span data-stu-id="a437c-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="a437c-119">Abre a janela de conversa para uma chamada de áudio, mas não disca o número especificado.</span><span class="sxs-lookup"><span data-stu-id="a437c-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a437c-120">SPI</span><span class="sxs-lookup"><span data-stu-id="a437c-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="a437c-121">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="a437c-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="a437c-122">Abre a janela de conversa com o URI (Uniform Resource Identifier) SIP especificado na lista de participantes.</span><span class="sxs-lookup"><span data-stu-id="a437c-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a437c-123">SIPS</span><span class="sxs-lookup"><span data-stu-id="a437c-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="a437c-124">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="a437c-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="a437c-125">Se o Lync 2013 estiver configurado para usar o protocolo TLS (Transport Layer Security), funciona exatamente como SIP:.</span><span class="sxs-lookup"><span data-stu-id="a437c-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="a437c-126">Se o TLS não estiver sendo usado, exibe uma caixa de diálogo informando ao usuário que um nível mais alto de segurança é necessário.</span><span class="sxs-lookup"><span data-stu-id="a437c-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a437c-127">Conferência</span><span class="sxs-lookup"><span data-stu-id="a437c-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="a437c-128">URI SIP da conferência para ingressar</span><span class="sxs-lookup"><span data-stu-id="a437c-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="a437c-129">Se URI for Self, instancia o foco e mostra o modo de exibição somente de lista.</span><span class="sxs-lookup"><span data-stu-id="a437c-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="a437c-130">Caso contrário, exibe o modo de exibição de lista, mas não envia convite.</span><span class="sxs-lookup"><span data-stu-id="a437c-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a437c-131">comunicar</span><span class="sxs-lookup"><span data-stu-id="a437c-131">im:</span></span></p></td>
<td><p><span data-ttu-id="a437c-132">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="a437c-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="a437c-133">Exibe uma janela de conversa somente de mensagens instantâneas (IM) com o URI SIP.</span><span class="sxs-lookup"><span data-stu-id="a437c-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="a437c-134">Aceita vários URIs SIP especificados dentro dos colchetes angulares (&lt;&gt;) sem qualquer separador.</span><span class="sxs-lookup"><span data-stu-id="a437c-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a437c-135">A tabela a seguir fornece exemplos desses parâmetros de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a437c-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="a437c-136">Exemplos de parâmetro de linha de comando</span><span class="sxs-lookup"><span data-stu-id="a437c-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a437c-137">Instância</span><span class="sxs-lookup"><span data-stu-id="a437c-137">Instance</span></span></th>
<th><span data-ttu-id="a437c-138">Resultados</span><span class="sxs-lookup"><span data-stu-id="a437c-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a437c-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="a437c-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="a437c-140">Abre um modo de exibição somente telefone com + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="a437c-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a437c-141">Callto: Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="a437c-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="a437c-142">Abre um modo de exibição somente telefone com + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="a437c-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a437c-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a437c-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="a437c-144">Abre uma exibição somente de telefone com o kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a437c-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a437c-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a437c-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="a437c-146">Abre uma janela de conversa com o kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a437c-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a437c-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="a437c-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="a437c-148">Abre uma janela de conversa e exibe as opções de ingresso no áudio da reunião.</span><span class="sxs-lookup"><span data-stu-id="a437c-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

