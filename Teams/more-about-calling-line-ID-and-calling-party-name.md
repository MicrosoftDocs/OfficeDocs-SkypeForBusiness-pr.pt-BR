---
title: Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Saiba por que você precisa adicionar uma pessoa autorizada que possa fazer alterações na conta ao usar o assistente Novo Pedido de Portabilidade de Número Local.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255394"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="d5169-103">Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador</span><span class="sxs-lookup"><span data-stu-id="d5169-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="d5169-104">CallerID, como normalmente é conhecido, na verdade consiste em duas informações de identificação do usuário:</span><span class="sxs-lookup"><span data-stu-id="d5169-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="d5169-105">Um número de telefone (normalmente chamado de CLID ou ID de linha de chamada)</span><span class="sxs-lookup"><span data-stu-id="d5169-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="d5169-106">Nome da parte de chamada (normalmente conhecido como CNAM), que pode ter até 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d5169-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="d5169-107">Quando uma chamada é feita, a CLID (número de telefone) é roteada para a operadora do destino (também conhecida como operadora de término).</span><span class="sxs-lookup"><span data-stu-id="d5169-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="d5169-108">As informações do CNAM para a chamada podem ou não ser roteada com a chamada, pois isso depende de como o país implementou o CNAM (se for o caso).</span><span class="sxs-lookup"><span data-stu-id="d5169-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="d5169-109">A confiabilidade da entrega do CNAM com a chamada varia dependendo do país e das operadoras que lidam com a chamada como intermediário e/ou como operadora de terminação.</span><span class="sxs-lookup"><span data-stu-id="d5169-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="d5169-110">A transmissão CLID & CNAM é de responsabilidade da transportadora de terminação na medida em que a operadora de terminação deve dar suporte à funcionalidade CLID & CNAM, bem como fornecer registros atualizados para ambos os valores.</span><span class="sxs-lookup"><span data-stu-id="d5169-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="d5169-111">A Microsoft fornece valores CLID confiável ao originar chamadas, mas esses valores podem não ser mantidos intactos depois que passam por uma operadora intermediária ou pela operadora de terminação.</span><span class="sxs-lookup"><span data-stu-id="d5169-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="d5169-112">Infelizmente, caso o valor de CLID seja alterado, omitido ou truncado pela operadora intermediária ou de terminação, a Microsoft tem pouco a não recurso para corrigir esses problemas na rede telefônica pública.</span><span class="sxs-lookup"><span data-stu-id="d5169-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="d5169-113">Inconsistências no CNAM podem ser causadas por atrasos na atualização das informações do CNAM em bancos de dados autoritativos, como no caso dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="d5169-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="d5169-114">Em países em que não há um banco de dados autoritativo para CNAM, as práticas de operadoras individuais também podem causar problemas com as informações do CNAM que chegam intactas à chamada.</span><span class="sxs-lookup"><span data-stu-id="d5169-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="d5169-115">Atualmente, a Microsoft não dá suporte a informações provenientes do CNAM em países diferentes dos Estados Unidos."</span><span class="sxs-lookup"><span data-stu-id="d5169-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="d5169-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d5169-116">Related topics</span></span>


