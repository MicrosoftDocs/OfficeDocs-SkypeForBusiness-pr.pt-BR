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
ms.openlocfilehash: 8b4ad6f728f01f0cf9ef1aac6ed57ad22c7ff345
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Apresentação da ID chamada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Com o Lync Server 2010, o número de telefone do participante chamado (ou seja, o número de telefone chamado) pode ser convertido no formato E. 164 no formato de discagem local necessário para o par de troncos (ou seja, o gateway associado, o PBX (central privada de comutação telefônica) ou o tronco SIP). Para fazer isso, você deve definir uma ou mais regras de conversão para converter o URI de solicitação antes de roteá-lo para o par de tronco.

<div>


> [!IMPORTANT]  
> A capacidade de associar uma ou mais regras de conversão de uma configuração de tronco do Enterprise Voice se destina a ser usada como uma <EM>alternativa </EM> para configurar as regras de conversão no ponto de tronco. Não associe as regras de conversão de uma configuração de tronco Enterprise Voice se você tiver configurado regras de conversão no peer de tronco, porque as duas regras podem entrar em conflito.



</div>

Você pode usar um dos seguintes métodos para compilar ou modificar uma regra de conversão:

  - Use a ferramenta **criar uma regra de conversão** para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e permitir que o painel de controle do Lync Server gere o padrão correspondente e a regra de conversão para você.

  - Escreva expressões regulares manualmente para definir o padrão de correspondência e a regra de conversão.

<div>


> [!NOTE]  
> Para obter informações sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>em.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar ou modificar uma regra de conversão usando a ferramenta compilar uma regra de conversão no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Criar ou modificar uma regra de conversão manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Apresentação da ID de chamadas no Lync Server 2013](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

