---
title: 'Lync Server 2013: Validando o roteamento e a normalização do número de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be8f09304ccf077eb24daf707e536e9c90f84dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="2778c-102">Validando a normalização de número de voz e encaminhamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2778c-102">Validating voice number normalization and routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2778c-103">_**Tópico da última modificação:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="2778c-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="2778c-104">A normalização e o roteamento do número corretos são muito importantes para o ambiente corporativo de voz funcional.</span><span class="sxs-lookup"><span data-stu-id="2778c-104">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="2778c-105">Especialmente durante as migrações do PBX (Private Branch Exchange) para o ambiente autônomo do Lync Server, uma das chaves para a migração bem-sucedida é revelar e documentar todas as regras de discagem existentes e criar regras de normalização adequadas, políticas de voz usos e rotas de telefone.</span><span class="sxs-lookup"><span data-stu-id="2778c-105">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="2778c-106">A validação da normalização do número e do roteamento é importante não apenas durante as migrações, mas também durante a operação normal e estável do sistema.</span><span class="sxs-lookup"><span data-stu-id="2778c-106">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="2778c-107">Recomendamos realizar essa validação diariamente usando o painel de controle do Lync Server, começando com o desenvolvimento de um conjunto robusto de casos de teste em relação ao conjunto atual de regras de normalização que foram publicadas nas configurações globais do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2778c-107">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="2778c-108">Estes casos de teste devem ser executados diariamente para realçar as alterações indesejadas que foram feitas e confirmadas no plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="2778c-108">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="2778c-109">O painel de controle do Lync Server também ajuda você a Visualizar, testar, alterar, arquivar e compartilhar informações de configuração sobre o roteamento de voz e alterar as regras de normalização do número da empresa, planos de discagem, política de voz e rotas.</span><span class="sxs-lookup"><span data-stu-id="2778c-109">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="2778c-110">Ele tem recursos adicionais para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2778c-110">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="2778c-111">Exportar e importar ou fazer backup de dados de roteamento de voz entre sistemas.</span><span class="sxs-lookup"><span data-stu-id="2778c-111">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="2778c-112">Testar alterações de configuração antes de carregá-las em um sistema dinâmico.</span><span class="sxs-lookup"><span data-stu-id="2778c-112">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="2778c-113">Criar e executar casos de teste de configuração para ajudar a garantir a usabilidade de dados de roteamento depois de fazer alterações nele, mas antes de confirmá-los as alterações em um sistema implantado.</span><span class="sxs-lookup"><span data-stu-id="2778c-113">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="2778c-114">Criar e alterar regras de normalização de número, perfis de localização, política de voz e dados de roteamento sem escrever as expressões regulares necessárias.</span><span class="sxs-lookup"><span data-stu-id="2778c-114">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="2778c-115">Analisando um perfil de local para compatibilidade com o Lync Server Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="2778c-115">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="2778c-116">Mais informações sobre testes de roteamento de voz podem ser encontradas em [testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="2778c-116">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2778c-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="2778c-117">See Also</span></span>


[<span data-ttu-id="2778c-118">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2778c-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

