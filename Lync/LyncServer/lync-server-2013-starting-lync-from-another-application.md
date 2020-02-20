---
title: 'Lync Server 2013: Iniciando o Lync de outro aplicativo'
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
ms.openlocfilehash: 75e7a48645301b6c822eed52ea31e6d4b46019bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="e83f8-102">Iniciando o Lync de outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="e83f8-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e83f8-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e83f8-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e83f8-104">Você pode usar os parâmetros de linha de comando para iniciar rapidamente o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e83f8-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="e83f8-105">Por exemplo, se um usuário clica em um número de telefone em outro aplicativo, o aplicativo pode iniciar uma instância do Lync 2013 e iniciar uma chamada para esse número.</span><span class="sxs-lookup"><span data-stu-id="e83f8-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="e83f8-106">O Lync 2013 também pode reconhecer uma lista delimitada por ponto-e-vírgula de nomes de contato para conferência de vários participantes.</span><span class="sxs-lookup"><span data-stu-id="e83f8-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="e83f8-107">Se o Lync 2013 estiver configurado para entrar automaticamente quando iniciado, a inicialização do Lync 2013 com os parâmetros de linha de comando abrirá a janela principal do Lync.</span><span class="sxs-lookup"><span data-stu-id="e83f8-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="e83f8-108">Se o Lync não estiver configurado para entrar automaticamente quando for iniciado, a janela será aberta.</span><span class="sxs-lookup"><span data-stu-id="e83f8-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="e83f8-109">A tabela a seguir mostra os parâmetros disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e83f8-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="e83f8-110">Parâmetros de linha de comando do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e83f8-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e83f8-111">Extensão</span><span class="sxs-lookup"><span data-stu-id="e83f8-111">Extension</span></span></th>
<th><span data-ttu-id="e83f8-112">Formato de dados</span><span class="sxs-lookup"><span data-stu-id="e83f8-112">Format of Data</span></span></th>
<th><span data-ttu-id="e83f8-113">Action</span><span class="sxs-lookup"><span data-stu-id="e83f8-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e83f8-114">Tel</span><span class="sxs-lookup"><span data-stu-id="e83f8-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="e83f8-115">tel URI</span><span class="sxs-lookup"><span data-stu-id="e83f8-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="e83f8-116">Abre a janela de conversação para uma chamada de áudio mas não disca o número especificado.</span><span class="sxs-lookup"><span data-stu-id="e83f8-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e83f8-117">callto:</span><span class="sxs-lookup"><span data-stu-id="e83f8-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="e83f8-118">tel:, sip:, ou tel URI digitável</span><span class="sxs-lookup"><span data-stu-id="e83f8-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="e83f8-119">Abre a janela de conversação para uma chamada de áudio mas não disca o número especificado.</span><span class="sxs-lookup"><span data-stu-id="e83f8-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e83f8-120">SIP</span><span class="sxs-lookup"><span data-stu-id="e83f8-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="e83f8-121">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="e83f8-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="e83f8-122">Abre a janela de conversação com o URI (Uniform Resource Identifier) do SIP na lista de participantes.</span><span class="sxs-lookup"><span data-stu-id="e83f8-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e83f8-123">Sips:</span><span class="sxs-lookup"><span data-stu-id="e83f8-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="e83f8-124">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="e83f8-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="e83f8-125">Se o Lync 2013 estiver configurado para usar o protocolo TLS (Transport Layer Security), funcionará exatamente como SIP:.</span><span class="sxs-lookup"><span data-stu-id="e83f8-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="e83f8-126">Se o TLS não estiver sendo usado, uma caixa de diálogo será exibida informando ao usuário que um nível maior de segurança é necessário.</span><span class="sxs-lookup"><span data-stu-id="e83f8-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e83f8-127">fere</span><span class="sxs-lookup"><span data-stu-id="e83f8-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="e83f8-128">URI do SIP da conferência para ingresso</span><span class="sxs-lookup"><span data-stu-id="e83f8-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="e83f8-p104">Quando o URI é self, ele cria uma instância do foco e exibe somente a lista de participantes. Caso contrário, ele exibe a lista de participantes, mas não envia INVITE.</span><span class="sxs-lookup"><span data-stu-id="e83f8-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e83f8-131">respectiva</span><span class="sxs-lookup"><span data-stu-id="e83f8-131">im:</span></span></p></td>
<td><p><span data-ttu-id="e83f8-132">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="e83f8-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="e83f8-133">Exibe uma janela de conversação de somente mensagens instantâneas com o URI do SIP.</span><span class="sxs-lookup"><span data-stu-id="e83f8-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="e83f8-134">Aceita vários URIs SIP especificados dentro de colchetes angulares (&lt;&gt;) sem nenhum separador.</span><span class="sxs-lookup"><span data-stu-id="e83f8-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e83f8-135">A tabela a seguir fornece exemplos destes parâmetros de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="e83f8-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="e83f8-136">Exemplos de parâmetros de linha de comando</span><span class="sxs-lookup"><span data-stu-id="e83f8-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e83f8-137">Instância</span><span class="sxs-lookup"><span data-stu-id="e83f8-137">Instance</span></span></th>
<th><span data-ttu-id="e83f8-138">Resultados</span><span class="sxs-lookup"><span data-stu-id="e83f8-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e83f8-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="e83f8-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="e83f8-140">Abre uma exibição somente de telefone com +14255550101.</span><span class="sxs-lookup"><span data-stu-id="e83f8-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e83f8-141">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="e83f8-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="e83f8-142">Abre uma exibição somente de telefone com +14255550101.</span><span class="sxs-lookup"><span data-stu-id="e83f8-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e83f8-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e83f8-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="e83f8-144">Abre uma exibição somente de telefone com kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e83f8-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e83f8-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e83f8-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="e83f8-146">Abre uma janela de conversação com kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e83f8-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e83f8-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="e83f8-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="e83f8-148">Abre uma janela de conversa e exibe opções de ingresso no áudio da reunião.</span><span class="sxs-lookup"><span data-stu-id="e83f8-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

