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
ms.openlocfilehash: 8dc22438a688239618fc7a73cf3aa30ec614568d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="32c23-102">Apresentação de ID chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c23-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32c23-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="32c23-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="32c23-104">Com o Lync Server 2010, o número de telefone da pessoa chamada (ou seja, o número de telefone chamado) pode ser traduzido do formato E. 164 para o formato de discagem local necessário para o tronco de tronco (ou seja, o gateway associado, a troca de ramificação privada (PBX) ou o tronco SIP).</span><span class="sxs-lookup"><span data-stu-id="32c23-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="32c23-105">Para fazer isso, você deve definir uma ou mais regras de conversão para converter a URI de Solicitação antes de roteá-la para o ponto de tronco.</span><span class="sxs-lookup"><span data-stu-id="32c23-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="32c23-106">A capacidade de associar uma ou mais regras de tradução a uma configuração de tronco Enterprise Voice deve ser usada como uma <EM>alternativa</EM> para configurar regras de tradução no par de troncos.</span><span class="sxs-lookup"><span data-stu-id="32c23-106">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="32c23-107">Não associe as regras de tradução a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de tradução no par de tronco porque as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="32c23-107">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="32c23-108">Você pode usar qualquer um dos seguintes métodos para criar ou modificar uma regra de Tradução:</span><span class="sxs-lookup"><span data-stu-id="32c23-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="32c23-109">Use a ferramenta **criar uma regra de tradução** para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e deixe o painel de controle do Lync Server gerar o padrão correspondente e a regra de tradução para você.</span><span class="sxs-lookup"><span data-stu-id="32c23-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="32c23-110">Grave expressões regulares manualmente para definir o padrão correspondente e a regra de tradução.</span><span class="sxs-lookup"><span data-stu-id="32c23-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32c23-111">Para obter informações sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>em.</span><span class="sxs-lookup"><span data-stu-id="32c23-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="32c23-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="32c23-112">In This Section</span></span>

  - [<span data-ttu-id="32c23-113">Criar ou modificar uma regra de tradução usando a ferramenta construir uma regra de tradução no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c23-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="32c23-114">Criar ou modificar uma regra de tradução manualmente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c23-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32c23-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="32c23-115">See Also</span></span>


[<span data-ttu-id="32c23-116">Apresentação da identificação de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c23-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

