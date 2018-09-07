---
title: Mais informações sobre a Identificação de linha da chamada e o nome do chamador
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Saiba por que você precisa adicionar uma pessoa autorizada que pode fazer alterações à conta quando você usar o Assistente de nova ordem de porta do número Local.
ms.openlocfilehash: 846abfd5b6973a02ad1a7388b45a79ec709695a0
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23865273"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="1e06b-103">Mais informações sobre a Identificação de linha da chamada e o nome do chamador</span><span class="sxs-lookup"><span data-stu-id="1e06b-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="1e06b-104">ID do chamador, conforme ele é normalmente denominado, realmente consiste de duas voltados para o usuário identificáveis partes das informações:</span><span class="sxs-lookup"><span data-stu-id="1e06b-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="1e06b-105">Um número de telefone (geralmente conhecido como CLID ou chamada de ID de linha)</span><span class="sxs-lookup"><span data-stu-id="1e06b-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="1e06b-106">Chamar o nome do participante (geralmente conhecido como CNAM) que pode ser até 15 caracteres de comprimento.</span><span class="sxs-lookup"><span data-stu-id="1e06b-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="1e06b-107">Quando uma chamada for feita, a CLID (número de telefone) é encaminhado para operadora do destino (também conhecida como a operadora terminação).</span><span class="sxs-lookup"><span data-stu-id="1e06b-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="1e06b-108">As informações CNAM para a chamada podem ou não poderão ser roteadas com a chamada conforme isso depende de como o país implementou CNAM (se nisso).</span><span class="sxs-lookup"><span data-stu-id="1e06b-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="1e06b-109">A confiabilidade de entrega CNAM com a chamada varia dependendo do país e operadoras que lidam com a chamada como um intermediário e/ou uma operadora de telefonia de encerramento.</span><span class="sxs-lookup"><span data-stu-id="1e06b-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="1e06b-110">Transmissão CLID & CNAM é responsabilidade da transportadora terminação na medida a operadora terminação deve oferecer suporte à funcionalidade CLID & CNAM bem como fornecer registros atualizados para os dois valores.</span><span class="sxs-lookup"><span data-stu-id="1e06b-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="1e06b-111">A Microsoft fornece valores CLID confiável ao originar chamadas, mas esses valores podem não ser mantidos intactos depois que eles passam por uma operadora intermediária ou a operadora de encerramento.</span><span class="sxs-lookup"><span data-stu-id="1e06b-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="1e06b-112">Infelizmente, no caso do valor CLID for alterado, omitido ou truncado pela transportadora intermediária ou encerramento, a Microsoft não tem pouco ou nenhum recursos correção desses problemas na rede telefônica pública.</span><span class="sxs-lookup"><span data-stu-id="1e06b-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="1e06b-113">Inconsistências no CNAM podem ser causadas por atrasos na intermediários ou encerramento operadoras atualizando info CNAM nos bancos de dados autoritativos, como no caso dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="1e06b-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="1e06b-114">Em países onde não há nenhum banco de dados autoritativo para CNAM, práticas de operadora individuais também podem causar problemas com informações de CNAM que chegam intacto com a chamada.</span><span class="sxs-lookup"><span data-stu-id="1e06b-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="1e06b-115">Microsoft atualmente não suporta informações do originador CNAM fora dos Estados Unidos países."</span><span class="sxs-lookup"><span data-stu-id="1e06b-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e06b-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1e06b-116">Related topics</span></span>


