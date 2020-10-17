---
title: 'Lync Server 2013: definindo regras de normalização'
description: 'Lync Server 2013: definindo regras de normalização.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a123e17b1d3256781ff34e4cade2b344ba8fe14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542037"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a>Definindo regras de normalização no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-04-22_

Lync Server 2013 as regras de normalização usam expressões regulares do .NET Framework para converter números de telefone discados em formato E. 164; em outras palavras, as regras de normalização levam o número de telefone discado por um usuário e convertem esse número no formato usado internamente pelo Lync Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.

Para obter detalhes sobre as regras de normalização, consulte [Dial Plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) na documentação de planejamento.

Para obter detalhes sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" em [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

É possível usar um dos seguintes métodos para definir ou editar uma regra de normalização:

  - Use a ferramenta **criar uma regra de normalização** para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e permitir que o painel de controle do Lync Server gere o padrão correspondente e a regra de conversão para você.

  - Escreva expressões regulares manualmente para definir o padrão de correspondência e a regra de conversão.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar ou modificar uma regra de normalização usando a criação de uma regra de normalização no Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Criar ou modificar uma regra de normalização manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

