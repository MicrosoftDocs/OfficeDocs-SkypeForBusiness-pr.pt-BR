---
title: 'Lync Server 2013: Iniciando o Lync de outro aplicativo'
description: 'Lync Server 2013: Iniciando o Lync de outro aplicativo.'
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
ms.openlocfilehash: fd64b8b9f335638b54a0bf6473b5d159c97a0e7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562697"
---
# <a name="starting-lync-from-another-application"></a><span data-ttu-id="97fe2-103">Iniciando o Lync de outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="97fe2-103">Starting Lync from another application</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97fe2-104">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="97fe2-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="97fe2-105">Você pode usar os parâmetros de linha de comando para iniciar rapidamente o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="97fe2-105">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="97fe2-106">Por exemplo, se um usuário clica em um número de telefone em outro aplicativo, o aplicativo pode iniciar uma instância do Lync 2013 e iniciar uma chamada para esse número.</span><span class="sxs-lookup"><span data-stu-id="97fe2-106">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="97fe2-107">O Lync 2013 também pode reconhecer uma lista delimitada por ponto-e-vírgula de nomes de contato para conferência de vários participantes.</span><span class="sxs-lookup"><span data-stu-id="97fe2-107">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="97fe2-108">Se o Lync 2013 estiver configurado para entrar automaticamente quando iniciado, a inicialização do Lync 2013 com os parâmetros de linha de comando abrirá a janela principal do Lync.</span><span class="sxs-lookup"><span data-stu-id="97fe2-108">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="97fe2-109">Se o Lync não estiver configurado para entrar automaticamente quando for iniciado, a janela será aberta.</span><span class="sxs-lookup"><span data-stu-id="97fe2-109">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="97fe2-110">A tabela a seguir mostra os parâmetros disponíveis.</span><span class="sxs-lookup"><span data-stu-id="97fe2-110">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="97fe2-111">Parâmetros de Command-Line do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="97fe2-111">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97fe2-112">Extensão</span><span class="sxs-lookup"><span data-stu-id="97fe2-112">Extension</span></span></th>
<th><span data-ttu-id="97fe2-113">Formato de dados</span><span class="sxs-lookup"><span data-stu-id="97fe2-113">Format of Data</span></span></th>
<th><span data-ttu-id="97fe2-114">Action</span><span class="sxs-lookup"><span data-stu-id="97fe2-114">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97fe2-115">Tel</span><span class="sxs-lookup"><span data-stu-id="97fe2-115">tel:</span></span></p></td>
<td><p><span data-ttu-id="97fe2-116">tel URI</span><span class="sxs-lookup"><span data-stu-id="97fe2-116">tel URI</span></span></p></td>
<td><p><span data-ttu-id="97fe2-117">Abre a janela de conversação para uma chamada de áudio mas não disca o número especificado.</span><span class="sxs-lookup"><span data-stu-id="97fe2-117">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97fe2-118">callto:</span><span class="sxs-lookup"><span data-stu-id="97fe2-118">callto:</span></span></p></td>
<td><p><span data-ttu-id="97fe2-119">tel:, sip:, ou tel URI digitável</span><span class="sxs-lookup"><span data-stu-id="97fe2-119">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="97fe2-120">Abre a janela de conversação para uma chamada de áudio mas não disca o número especificado.</span><span class="sxs-lookup"><span data-stu-id="97fe2-120">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97fe2-121">SIP</span><span class="sxs-lookup"><span data-stu-id="97fe2-121">sip:</span></span></p></td>
<td><p><span data-ttu-id="97fe2-122">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="97fe2-122">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="97fe2-123">Abre a janela de conversação com o URI (Uniform Resource Identifier) do SIP na lista de participantes.</span><span class="sxs-lookup"><span data-stu-id="97fe2-123">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97fe2-124">Sips:</span><span class="sxs-lookup"><span data-stu-id="97fe2-124">Sips:</span></span></p></td>
<td><p><span data-ttu-id="97fe2-125">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="97fe2-125">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="97fe2-126">Se o Lync 2013 estiver configurado para usar o protocolo TLS (Transport Layer Security), funcionará exatamente como SIP:.</span><span class="sxs-lookup"><span data-stu-id="97fe2-126">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="97fe2-127">Se o TLS não estiver sendo usado, uma caixa de diálogo será exibida informando ao usuário que um nível maior de segurança é necessário.</span><span class="sxs-lookup"><span data-stu-id="97fe2-127">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97fe2-128">fere</span><span class="sxs-lookup"><span data-stu-id="97fe2-128">conf:</span></span></p></td>
<td><p><span data-ttu-id="97fe2-129">URI do SIP da conferência para ingresso</span><span class="sxs-lookup"><span data-stu-id="97fe2-129">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="97fe2-p104">Quando o URI é self, ele cria uma instância do foco e exibe somente a lista de participantes. Caso contrário, ele exibe a lista de participantes, mas não envia INVITE.</span><span class="sxs-lookup"><span data-stu-id="97fe2-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97fe2-132">respectiva</span><span class="sxs-lookup"><span data-stu-id="97fe2-132">im:</span></span></p></td>
<td><p><span data-ttu-id="97fe2-133">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="97fe2-133">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="97fe2-134">Exibe uma janela de conversação de somente mensagens instantâneas com o URI do SIP.</span><span class="sxs-lookup"><span data-stu-id="97fe2-134">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="97fe2-135">Aceita vários URIs SIP especificados dentro de colchetes angulares ( &lt; &gt; ) sem nenhum separador.</span><span class="sxs-lookup"><span data-stu-id="97fe2-135">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="97fe2-136">A tabela a seguir fornece exemplos destes parâmetros de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="97fe2-136">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="97fe2-137">Exemplos de parâmetros de linha de comando</span><span class="sxs-lookup"><span data-stu-id="97fe2-137">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97fe2-138">Instância</span><span class="sxs-lookup"><span data-stu-id="97fe2-138">Instance</span></span></th>
<th><span data-ttu-id="97fe2-139">Resultados</span><span class="sxs-lookup"><span data-stu-id="97fe2-139">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97fe2-140">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="97fe2-140">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="97fe2-141">Abre uma exibição somente de telefone com +14255550101.</span><span class="sxs-lookup"><span data-stu-id="97fe2-141">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97fe2-142">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="97fe2-142">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="97fe2-143">Abre uma exibição somente de telefone com +14255550101.</span><span class="sxs-lookup"><span data-stu-id="97fe2-143">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97fe2-144">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="97fe2-144">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="97fe2-145">Abre uma exibição somente de telefone com kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="97fe2-145">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97fe2-146">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="97fe2-146">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="97fe2-147">Abre uma janela de conversação com kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="97fe2-147">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97fe2-148">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="97fe2-148">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="97fe2-149">Abre uma janela de conversa e exibe opções de ingresso no áudio da reunião.</span><span class="sxs-lookup"><span data-stu-id="97fe2-149">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

