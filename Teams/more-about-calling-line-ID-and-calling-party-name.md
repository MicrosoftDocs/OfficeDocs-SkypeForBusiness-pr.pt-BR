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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Saiba por que você precisa adicionar uma pessoa autorizada que pode fazer alterações na conta quando você usa o assistente de nova ordem de número local.
ms.openlocfilehash: e77176b978cb33df2bc4efebae11fb218c3932a5
ms.sourcegitcommit: 4bb900228cc55e0cbbce8c5b74b7de8df5a2288f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "34415743"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="65742-103">Mais informações sobre a Identificação de linha da chamada e o nome do chamador</span><span class="sxs-lookup"><span data-stu-id="65742-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="65742-104">A identificação de chamada, como normalmente é referida, consiste, na verdade, de duas informações identificáveis pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="65742-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="65742-105">Um número de telefone (geralmente chamado de identificação de linha de chamada ou de CLID)</span><span class="sxs-lookup"><span data-stu-id="65742-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="65742-106">Nome do participante da chamada (geralmente chamado de CNAM), que pode ter até 15 caracteres de comprimento.</span><span class="sxs-lookup"><span data-stu-id="65742-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="65742-107">Quando uma chamada é feita, a CLID (número de telefone) é roteada para a portadora do destino (também conhecida como a operadora de terminação).</span><span class="sxs-lookup"><span data-stu-id="65742-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="65742-108">As informações CNAM da chamada podem ou não ser roteadas com a chamada, pois isso depende de como o país implementou CNAM (se houver).</span><span class="sxs-lookup"><span data-stu-id="65742-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="65742-109">A confiabilidade da entrega do CNAM com a chamada varia de acordo com o país e as operadoras que manipulam a chamada como um intermediário e/ou uma operadora de terminação.</span><span class="sxs-lookup"><span data-stu-id="65742-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="65742-110">A & de CNAM de CLID de CLID é a responsabilidade do responsável pela operadora de terminação, pois a operadora de terminação deve dar suporte à funcionalidade CLID & CNAM, além de fornecer registros atualizados para ambos os valores.</span><span class="sxs-lookup"><span data-stu-id="65742-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="65742-111">A Microsoft fornece valores de CLID de forma confiável ao fazer chamadas, mas esses valores podem não ser mantidos intactos quando passam por uma operadora de telefonia ou de terminação.</span><span class="sxs-lookup"><span data-stu-id="65742-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="65742-112">Infelizmente, no caso de o valor de CLID ser alterado, omitido ou truncado pelo intermediário ou pela operadora de terminação, a Microsoft tem pouco ou nenhum recurso para corrigir tais problemas na rede telefônica pública.</span><span class="sxs-lookup"><span data-stu-id="65742-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="65742-113">As inconsistências no CNAM podem ser causadas por atrasos em transportadoras intermediárias ou de terminação atualizando as informações de CNAM em bancos de dados autoritativos, como no caso dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="65742-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="65742-114">Em países onde não há banco de dados autoritativo para CNAM, as práticas individuais da operadora também podem causar problemas com as informações do CNAM que chegam em tact com a chamada.</span><span class="sxs-lookup"><span data-stu-id="65742-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="65742-115">Atualmente, a Microsoft não oferece suporte a informações de CNAM de origem em países que não sejam os Estados Unidos. "</span><span class="sxs-lookup"><span data-stu-id="65742-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="65742-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="65742-116">Related topics</span></span>


