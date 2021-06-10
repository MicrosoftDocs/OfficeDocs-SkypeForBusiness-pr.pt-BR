---
title: Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: Saiba mais sobre a ID da Linha de Chamada e o Nome da Parte de Chamada.
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308310"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="2b66b-103">Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador</span><span class="sxs-lookup"><span data-stu-id="2b66b-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="2b66b-104">CallerID consiste em duas informações voltadas para o usuário:</span><span class="sxs-lookup"><span data-stu-id="2b66b-104">CallerID consists of two user-facing pieces of information:</span></span>

- <span data-ttu-id="2b66b-105">Um número de telefone (geralmente chamado de CLID ou ID de linha de chamada).</span><span class="sxs-lookup"><span data-stu-id="2b66b-105">A phone number (typically referred to as CLID or calling line ID).</span></span>

- <span data-ttu-id="2b66b-106">Nome da parte de chamada (normalmente conhecido como CNAM).</span><span class="sxs-lookup"><span data-stu-id="2b66b-106">Calling party name (typically referred to as CNAM).</span></span> 

<span data-ttu-id="2b66b-107">Quando uma chamada é feita, o CLID (número de telefone) é roteado para a operadora do destino (também conhecida como operadora de término).</span><span class="sxs-lookup"><span data-stu-id="2b66b-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="2b66b-108">As informações do CNAM para a chamada podem ou não ser roteada com a chamada porque essas informações dependem de como o país implementou o CNAM (se for o caso).</span><span class="sxs-lookup"><span data-stu-id="2b66b-108">The CNAM information for the call may or may not be routed with the call because as this information depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="2b66b-109">A confiabilidade da entrega do CNAM com a chamada varia dependendo do país e das operadoras que lidam com a chamada— como intermediário ou como uma operadora de terminação.</span><span class="sxs-lookup"><span data-stu-id="2b66b-109">The reliability of CNAM delivery with the call varies depending on the country and carriers that handle the call--either as an intermediary or a terminating carrier.</span></span> 

<span data-ttu-id="2b66b-110">A & CLID é de responsabilidade da operadora de terminação.</span><span class="sxs-lookup"><span data-stu-id="2b66b-110">CLID & CNAM transmission is the responsibility of the terminating carrier.</span></span> <span data-ttu-id="2b66b-111">A operadora de terminação deve oferecer suporte & clid para a funcionalidade CNAM, bem como fornecer registros atualizados para ambos os valores.</span><span class="sxs-lookup"><span data-stu-id="2b66b-111">The terminating carrier must support CLID & CNAM functionality as well as provide up-to-date records for both values.</span></span> <span data-ttu-id="2b66b-112">A Microsoft fornece valores CLID confiável ao originar chamadas, mas esses valores podem não ser mantidos intactos depois de passarem por uma operadora intermediária ou pela operadora de terminação.</span><span class="sxs-lookup"><span data-stu-id="2b66b-112">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="2b66b-113">Se o valor CLID for alterado, omitido ou truncado pela operadora intermediária ou finalização, a Microsoft terá pouco ou nenhum recurso para corrigir esses problemas na rede telefônica pública.</span><span class="sxs-lookup"><span data-stu-id="2b66b-113">If the CLID value is changed, omitted, or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="2b66b-114">Inconsistências no CNAM podem ser causadas quando as operadoras intermediárias ou terminantes atrasam a atualização das informações cnam em bancos de dados autoritativos, como no caso dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2b66b-114">Inconsistencies in CNAM can be caused when the intermediate or terminating carriers delay refreshing the CNAM information in authoritative databases--as in the case of the United States.</span></span> <span data-ttu-id="2b66b-115">Em países onde não há bancos de dados autoritativos para CNAM, as práticas de operadoras individuais também podem causar problemas com as informações cnam que chegam intactas com a chamada.</span><span class="sxs-lookup"><span data-stu-id="2b66b-115">In countries where there are no authoritative databases for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="2b66b-116">No momento, a Microsoft não dá suporte à origem de informações cnam em países diferentes dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2b66b-116">Microsoft currently does not support originating CNAM information in countries other than the United States.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2b66b-117">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2b66b-117">Related topics</span></span>


