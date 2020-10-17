---
title: 'Lync Server 2013: reduzindo mensagens instantâneas não solicitadas'
description: 'Lync Server 2013: reduzindo mensagens instantâneas não solicitadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 294c53a6b82b4dc345fbb9afcf9983d5bd35893a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559107"
---
# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Reduzindo mensagens instantâneas não solicitadas para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-12-05_

O aplicativo de filtro de IM inteligente ajuda a proteger sua implantação do Microsoft Lync Server 2013 contra os vírus mais comuns com menor degradação para a experiência do usuário. O  Filtro de IM Inteligente oferece o seguinte:

  - Filtragem avançada de URL

  - Filtragem avançada de transferência de arquivo

Use o Filtro de IM Inteligente para configurar filtros para bloquear as mensagens instantâneas não solicitadas ou potencialmente prejudiciais de pontos de extremidade desconhecidos externos ao firewall corporativo. Os filtros são configurados especificando os critérios a ser usados para determinar o que deve ser bloqueado, como as mensagens instantâneas contendo hyperlinks e arquivos com extensões específicas.

Antes de implantar o aplicativo inteligente de filtro de mensagens INSTANTÂNEAs, você deve entender como as opções de filtragem são aplicadas quando as mensagens são roteadas de um servidor do Lync Server 2013 para outro. A forma como estas opções de filtragem são aplicadas é consistente, independentemente de se os servidores estão localizados em uma única organização ou entre fronteiras organizacionais. Essa consistência se aplica à forma como o aviso personalizado e os textos de aviso são inseridos em mensagens e enviados através de servidores.

A opção de filtragem recomendada é de permitir as mensagens instantâneas com hiperlinks, mas exigir que o Filtro de IM Inteligente desabilite o vínculo, inserindo um sublinhado antes dele. Se você escolher esta opção, existe a opção adicional de redigir um aviso aos usuários que aparece no início de cada mensagem instantânea que contém um hiperlink.

Uma segunda opção de filtragem é permitir as mensagens instantâneas com hiperlinks não modificados. Se você escolher esta opção, existe a opção adicional (recomendada) de redigir um aviso aos usuários que é inserido em cada mensagem.

Uma terceira opção é bloquear todas as mensagens instantâneas que contêm hiperlinks. Se você escolher essa opção, o servidor envia um aviso ao usuário. Você deve escrever este aviso.

</div>

<span> </span>

</div>

</div>

</div>

