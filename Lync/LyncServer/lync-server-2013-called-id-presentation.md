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

# <a name="called-id-presentation-in-lync-server-2013"></a>Apresentação de ID chamada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Com o Lync Server 2010, o número de telefone da pessoa chamada (ou seja, o número de telefone chamado) pode ser traduzido do formato E. 164 para o formato de discagem local necessário para o tronco de tronco (ou seja, o gateway associado, a troca de ramificação privada (PBX) ou o tronco SIP). Para fazer isso, você deve definir uma ou mais regras de conversão para converter a URI de Solicitação antes de roteá-la para o ponto de tronco.

<div>


> [!IMPORTANT]  
> A capacidade de associar uma ou mais regras de tradução a uma configuração de tronco Enterprise Voice deve ser usada como uma <EM>alternativa</EM> para configurar regras de tradução no par de troncos. Não associe as regras de tradução a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de tradução no par de tronco porque as duas regras podem entrar em conflito.



</div>

Você pode usar qualquer um dos seguintes métodos para criar ou modificar uma regra de Tradução:

  - Use a ferramenta **criar uma regra de tradução** para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e deixe o painel de controle do Lync Server gerar o padrão correspondente e a regra de tradução para você.

  - Grave expressões regulares manualmente para definir o padrão correspondente e a regra de tradução.

<div>


> [!NOTE]  
> Para obter informações sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>em.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar ou modificar uma regra de tradução usando a ferramenta construir uma regra de tradução no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Criar ou modificar uma regra de tradução manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Apresentação da identificação de chamadas no Lync Server 2013](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

