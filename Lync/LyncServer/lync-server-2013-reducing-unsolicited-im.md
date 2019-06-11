---
title: 'Lync Server 2013: Reduzindo as IMs não solicitadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="dfa1b-102">Reduzindo as IMs não solicitadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfa1b-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfa1b-103">_**Tópico da última modificação:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="dfa1b-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="dfa1b-104">O aplicativo filtro de mensagens instantâneas inteligente ajuda a proteger a implantação do Microsoft Lync Server 2013 contra os vírus mais comuns com o mínimo de degradação para a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="dfa1b-105">O filtro de IM inteligente fornece o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dfa1b-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="dfa1b-106">Filtragem de URL aprimorada</span><span class="sxs-lookup"><span data-stu-id="dfa1b-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="dfa1b-107">Filtragem de transferência de arquivo aprimorada</span><span class="sxs-lookup"><span data-stu-id="dfa1b-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="dfa1b-108">Use o filtro de IM inteligente para configurar filtros para bloquear mensagens instantâneas não solicitadas ou perigosas de pontos de extremidade desconhecidos fora do firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="dfa1b-109">Você pode configurar filtros especificando os critérios a serem usados para determinar o que deve ser bloqueado, como mensagens instantâneas contendo hiperlinks e arquivos com extensões específicas.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="dfa1b-110">Antes de implantar o aplicativo inteligente de filtro de mensagem instantânea, você deve entender como as opções de filtragem são aplicadas quando as mensagens são roteadas de um servidor do Lync Server 2013 para outro.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="dfa1b-111">A maneira como essas opções de filtragem são consistentes é consistente, independentemente de os servidores estarem localizados em uma única organização ou entre fronteiras organizacionais.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="dfa1b-112">Essa consistência se aplica à maneira como o aviso personalizado e o texto de aviso são inseridos em mensagens e enviados entre servidores.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="dfa1b-113">A opção de filtragem recomendada é permitir mensagens de chat com hiperlinks, mas exigir o filtro de mensagem instantânea inteligente para desabilitar o link, inserindo um sublinhado antes dele.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="dfa1b-114">Se você escolher essa opção, terá a opção adicional de compor um aviso para os usuários que aparecem no início de cada mensagem instantânea que contém um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="dfa1b-115">Uma segunda opção de filtragem é permitir mensagens instantâneas com hiperlinks não modificados.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="dfa1b-116">Se você escolher essa opção, terá a opção adicional (recomendado) de compor um aviso para os usuários que são inseridos em cada mensagem.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="dfa1b-117">Uma terceira opção é bloquear todas as mensagens instantâneas que contenham hiperlinks.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="dfa1b-118">Se você escolher essa opção, o servidor enviará um aviso ao usuário.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="dfa1b-119">Você deve escrever este aviso.</span><span class="sxs-lookup"><span data-stu-id="dfa1b-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

