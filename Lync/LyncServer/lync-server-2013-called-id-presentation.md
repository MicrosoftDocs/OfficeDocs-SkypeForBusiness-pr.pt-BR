---
title: 'Lync Server 2013: apresentação de ID chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bddaba994d5e0907200902deb8c818cca4199c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="142ad-102">Apresentação da ID chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="142ad-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="142ad-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="142ad-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="142ad-104">Com o Lync Server 2010, o número de telefone do participante chamado (ou seja, o número de telefone chamado) pode ser convertido no formato E. 164 no formato de discagem local necessário para o par de troncos (ou seja, o gateway associado, o PBX (central privada de comutação telefônica) ou o tronco SIP).</span><span class="sxs-lookup"><span data-stu-id="142ad-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="142ad-105">Para fazer isso, você deve definir uma ou mais regras de conversão para converter o URI de solicitação antes de roteá-lo para o par de tronco.</span><span class="sxs-lookup"><span data-stu-id="142ad-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="142ad-p102">A capacidade de associar uma ou mais regras de conversão de uma configuração de tronco do Enterprise Voice se destina a ser usada como uma <EM>alternativa </EM> para configurar as regras de conversão no ponto de tronco. Não associe as regras de conversão de uma configuração de tronco Enterprise Voice se você tiver configurado regras de conversão no peer de tronco, porque as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="142ad-p102">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer. Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="142ad-108">Você pode usar um dos seguintes métodos para compilar ou modificar uma regra de conversão:</span><span class="sxs-lookup"><span data-stu-id="142ad-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="142ad-109">Use a ferramenta **criar uma regra de conversão** para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e permitir que o painel de controle do Lync Server gere o padrão correspondente e a regra de conversão para você.</span><span class="sxs-lookup"><span data-stu-id="142ad-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="142ad-110">Escreva expressões regulares manualmente para definir o padrão de correspondência e a regra de conversão.</span><span class="sxs-lookup"><span data-stu-id="142ad-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="142ad-111">Para obter informações sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>em.</span><span class="sxs-lookup"><span data-stu-id="142ad-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="142ad-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="142ad-112">In This Section</span></span>

  - [<span data-ttu-id="142ad-113">Criar ou modificar uma regra de conversão usando a ferramenta compilar uma regra de conversão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="142ad-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="142ad-114">Criar ou modificar uma regra de conversão manualmente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="142ad-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="142ad-115">Confira Também</span><span class="sxs-lookup"><span data-stu-id="142ad-115">See Also</span></span>


[<span data-ttu-id="142ad-116">Apresentação da ID de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="142ad-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

