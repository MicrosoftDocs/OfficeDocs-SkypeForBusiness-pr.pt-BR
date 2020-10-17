---
title: 'Lync Server 2013: validação de normalização de número de voz e roteamento'
description: 'Lync Server 2013: Validando o roteamento e normalização de número de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f28f679cbb991bdb90362eb61c9c7b68879791e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547137"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="5b32a-103">Validação da normalização de número de voz e roteamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b32a-103">Validating voice number normalization and routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b32a-104">_**Última modificação do tópico:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="5b32a-104">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="5b32a-105">A normalização e o roteamento do número corretos são muito importantes para o ambiente corporativo de voz funcional.</span><span class="sxs-lookup"><span data-stu-id="5b32a-105">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="5b32a-106">Especialmente durante migrações do PBX (Private Branch Exchange) para o ambiente do Lync Server autônomo, uma das chaves para a migração bem-sucedida é revelar e documentar todas as regras de discagem existentes e criar regras de normalização apropriadas, políticas de voz, usos e rotas de telefone.</span><span class="sxs-lookup"><span data-stu-id="5b32a-106">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="5b32a-107">A validação do número normalização e o roteamento é importante não apenas durante as migrações, mas também durante a operação estável normal do sistema.</span><span class="sxs-lookup"><span data-stu-id="5b32a-107">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="5b32a-108">Recomendamos realizar essa validação diariamente usando o painel de controle do Lync Server, começando com o desenvolvimento de um conjunto robusto de casos de teste em relação ao conjunto atual de regras de normalização publicadas nas configurações globais do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b32a-108">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="5b32a-109">Estes casos de teste devem ser executados diariamente para realçar quaisquer alterações indesejadas que foram feitas e confirmadas no plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="5b32a-109">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="5b32a-110">O painel de controle do Lync Server também ajuda você a Visualizar, testar, alterar, arquivar e compartilhar informações de configuração sobre o roteamento de voz e alterar as regras de normalização do número Enterprise Voice, planos de discagem, política de voz e rotas.</span><span class="sxs-lookup"><span data-stu-id="5b32a-110">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="5b32a-111">Ele tem recursos adicionais para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5b32a-111">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="5b32a-112">Exportação e importação ou backup de dados de roteamento de voz entre sistemas.</span><span class="sxs-lookup"><span data-stu-id="5b32a-112">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="5b32a-113">Testar as alterações de configuração antes de carregá-las em um sistema ativo.</span><span class="sxs-lookup"><span data-stu-id="5b32a-113">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="5b32a-114">Criar e executar casos de teste de configuração para ajudar a garantir a usabilidade dos dados de roteamento depois que você fizer alterações nele, mas antes de confirmar as alterações em um sistema implantado.</span><span class="sxs-lookup"><span data-stu-id="5b32a-114">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="5b32a-115">Criar e alterar as regras de normalização de número, perfis de local, política de voz e dados de roteamento sem gravar as expressões regulares necessárias.</span><span class="sxs-lookup"><span data-stu-id="5b32a-115">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="5b32a-116">Análise de um perfil de local para compatibilidade com o Lync Server Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="5b32a-116">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="5b32a-117">É possível encontrar mais informações sobre testes de roteamento de voz no [Test Voice Routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="5b32a-117">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5b32a-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="5b32a-118">See Also</span></span>


[<span data-ttu-id="5b32a-119">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b32a-119">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

