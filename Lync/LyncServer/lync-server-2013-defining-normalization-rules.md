---
title: 'Lync Server 2013: Definindo regras de normalização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9406e4fa7445242ae3f112ebfb772713d9d2219c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="731e5-102">Definindo regras de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="731e5-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="731e5-103">_**Tópico da última modificação:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="731e5-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="731e5-104">As regras de normalização do Lync Server 2013 usam expressões regulares do .NET Framework para traduzir números de telefone discados para o formato E. 164; em outras palavras, as regras de normalização recebem o número de telefone discado por um usuário e convertem esse número no formato usado internamente pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="731e5-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="731e5-105">Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.</span><span class="sxs-lookup"><span data-stu-id="731e5-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="731e5-106">Para obter detalhes sobre as regras de normalização, consulte [planos de discagem e regras de normalização no Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="731e5-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="731e5-107">Para obter detalhes sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)em.</span><span class="sxs-lookup"><span data-stu-id="731e5-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="731e5-108">Você pode usar qualquer um dos seguintes métodos para definir ou editar uma regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="731e5-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="731e5-109">Use a ferramenta **criar uma regra** de normalização para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e deixe o painel de controle do Lync Server gerar o padrão correspondente e a regra de tradução para você.</span><span class="sxs-lookup"><span data-stu-id="731e5-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="731e5-110">Grave expressões regulares manualmente para definir o padrão correspondente e a regra de tradução.</span><span class="sxs-lookup"><span data-stu-id="731e5-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="731e5-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="731e5-111">In This Section</span></span>

  - [<span data-ttu-id="731e5-112">Criar ou modificar uma regra de normalização usando criar uma regra de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="731e5-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="731e5-113">Criar ou modificar uma regra de normalização manualmente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="731e5-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="731e5-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="731e5-114">See Also</span></span>


[<span data-ttu-id="731e5-115">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="731e5-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="731e5-116">Modificar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="731e5-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

