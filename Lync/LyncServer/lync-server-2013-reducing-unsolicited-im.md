---
title: 'Lync Server 2013: reduzindo mensagens instantâneas não solicitadas'
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
ms.openlocfilehash: 6e6b3b720e5c05051cd556af7d32e8293e95c315
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512008"
---
# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="58ea0-102">Reduzindo mensagens instantâneas não solicitadas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58ea0-102">Reducing unsolicited IM for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ea0-103">_**Última modificação do tópico:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="58ea0-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="58ea0-104">O aplicativo de filtro de IM inteligente ajuda a proteger sua implantação do Microsoft Lync Server 2013 contra os vírus mais comuns com menor degradação para a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="58ea0-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="58ea0-105">O  Filtro de IM Inteligente oferece o seguinte:</span><span class="sxs-lookup"><span data-stu-id="58ea0-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="58ea0-106">Filtragem avançada de URL</span><span class="sxs-lookup"><span data-stu-id="58ea0-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="58ea0-107">Filtragem avançada de transferência de arquivo</span><span class="sxs-lookup"><span data-stu-id="58ea0-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="58ea0-p102">Use o Filtro de IM Inteligente para configurar filtros para bloquear as mensagens instantâneas não solicitadas ou potencialmente prejudiciais de pontos de extremidade desconhecidos externos ao firewall corporativo. Os filtros são configurados especificando os critérios a ser usados para determinar o que deve ser bloqueado, como as mensagens instantâneas contendo hyperlinks e arquivos com extensões específicas.</span><span class="sxs-lookup"><span data-stu-id="58ea0-p102">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall. You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="58ea0-110">Antes de implantar o aplicativo inteligente de filtro de mensagens INSTANTÂNEAs, você deve entender como as opções de filtragem são aplicadas quando as mensagens são roteadas de um servidor do Lync Server 2013 para outro.</span><span class="sxs-lookup"><span data-stu-id="58ea0-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="58ea0-111">A forma como estas opções de filtragem são aplicadas é consistente, independentemente de se os servidores estão localizados em uma única organização ou entre fronteiras organizacionais.</span><span class="sxs-lookup"><span data-stu-id="58ea0-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="58ea0-112">Essa consistência se aplica à forma como o aviso personalizado e os textos de aviso são inseridos em mensagens e enviados através de servidores.</span><span class="sxs-lookup"><span data-stu-id="58ea0-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="58ea0-p104">A opção de filtragem recomendada é de permitir as mensagens instantâneas com hiperlinks, mas exigir que o Filtro de IM Inteligente desabilite o vínculo, inserindo um sublinhado antes dele. Se você escolher esta opção, existe a opção adicional de redigir um aviso aos usuários que aparece no início de cada mensagem instantânea que contém um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="58ea0-p104">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it. If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="58ea0-p105">Uma segunda opção de filtragem é permitir as mensagens instantâneas com hiperlinks não modificados. Se você escolher esta opção, existe a opção adicional (recomendada) de redigir um aviso aos usuários que é inserido em cada mensagem.</span><span class="sxs-lookup"><span data-stu-id="58ea0-p105">A second filtering option is to allow instant messages with unmodified hyperlinks. If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="58ea0-p106">Uma terceira opção é bloquear todas as mensagens instantâneas que contêm hiperlinks. Se você escolher essa opção, o servidor envia um aviso ao usuário. Você deve escrever este aviso.</span><span class="sxs-lookup"><span data-stu-id="58ea0-p106">A third option is to block all instant messages that contain hyperlinks. If you choose this option, the server sends a warning to the user. You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

