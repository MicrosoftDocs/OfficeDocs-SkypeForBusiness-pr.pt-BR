---
title: 'Lync Server 2013: Reduzindo as IMs não solicitadas'
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
ms.openlocfilehash: d0f8326d6fa9f85b202e0ea2dcbe3fed63a723aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Reduzindo as IMs não solicitadas para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-12-05_

O aplicativo filtro de mensagens instantâneas inteligente ajuda a proteger a implantação do Microsoft Lync Server 2013 contra os vírus mais comuns com o mínimo de degradação para a experiência do usuário. O filtro de IM inteligente fornece o seguinte:

  - Filtragem de URL aprimorada

  - Filtragem de transferência de arquivo aprimorada

Use o filtro de IM inteligente para configurar filtros para bloquear mensagens instantâneas não solicitadas ou perigosas de pontos de extremidade desconhecidos fora do firewall corporativo. Você pode configurar filtros especificando os critérios a serem usados para determinar o que deve ser bloqueado, como mensagens instantâneas contendo hiperlinks e arquivos com extensões específicas.

Antes de implantar o aplicativo inteligente de filtro de mensagem instantânea, você deve entender como as opções de filtragem são aplicadas quando as mensagens são roteadas de um servidor do Lync Server 2013 para outro. A maneira como essas opções de filtragem são consistentes é consistente, independentemente de os servidores estarem localizados em uma única organização ou entre fronteiras organizacionais. Essa consistência se aplica à maneira como o aviso personalizado e o texto de aviso são inseridos em mensagens e enviados entre servidores.

A opção de filtragem recomendada é permitir mensagens de chat com hiperlinks, mas exigir o filtro de mensagem instantânea inteligente para desabilitar o link, inserindo um sublinhado antes dele. Se você escolher essa opção, terá a opção adicional de compor um aviso para os usuários que aparecem no início de cada mensagem instantânea que contém um hiperlink.

Uma segunda opção de filtragem é permitir mensagens instantâneas com hiperlinks não modificados. Se você escolher essa opção, terá a opção adicional (recomendado) de compor um aviso para os usuários que são inseridos em cada mensagem.

Uma terceira opção é bloquear todas as mensagens instantâneas que contenham hiperlinks. Se você escolher essa opção, o servidor enviará um aviso ao usuário. Você deve escrever este aviso.

</div>

<span> </span>

</div>

</div>

</div>

