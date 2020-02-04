---
title: 'Lync Server 2013: Definindo regras de normalização'
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
ms.openlocfilehash: b75883d99d218d711e9d96de7ebfd7d360972a6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a>Definindo regras de normalização no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-04-22_

As regras de normalização do Lync Server 2013 usam expressões regulares do .NET Framework para traduzir números de telefone discados para o formato E. 164; em outras palavras, as regras de normalização recebem o número de telefone discado por um usuário e convertem esse número no formato usado internamente pelo Lync Server. Cada plano de discagem deve ter uma ou mais regras de normalização atribuídas.

Para obter detalhes sobre as regras de normalização, consulte [planos de discagem e regras de normalização no Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) na documentação de planejamento.

Para obter detalhes sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)em.

Você pode usar qualquer um dos seguintes métodos para definir ou editar uma regra de normalização:

  - Use a ferramenta **criar uma regra de normalização** para especificar valores para os dígitos iniciais, comprimento, dígitos a serem removidos e dígitos a serem adicionados e deixe o painel de controle do Lync Server gerar o padrão correspondente e a regra de tradução para você.

  - Grave expressões regulares manualmente para definir o padrão correspondente e a regra de tradução.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar ou modificar uma regra de normalização usando criar uma regra de normalização no Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

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

