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
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador

CallerID consiste em duas informações voltadas para o usuário:

- Um número de telefone (geralmente chamado de CLID ou ID de linha de chamada).

- Nome da parte de chamada (normalmente conhecido como CNAM). 

Quando uma chamada é feita, o CLID (número de telefone) é roteado para a operadora do destino (também conhecida como operadora de término). As informações do CNAM para a chamada podem ou não ser roteada com a chamada porque essas informações dependem de como o país implementou o CNAM (se for o caso). A confiabilidade da entrega do CNAM com a chamada varia dependendo do país e das operadoras que lidam com a chamada— como intermediário ou como uma operadora de terminação. 

A & CLID é de responsabilidade da operadora de terminação. A operadora de terminação deve oferecer suporte & clid para a funcionalidade CNAM, bem como fornecer registros atualizados para ambos os valores. A Microsoft fornece valores CLID confiável ao originar chamadas, mas esses valores podem não ser mantidos intactos depois de passarem por uma operadora intermediária ou pela operadora de terminação. Se o valor CLID for alterado, omitido ou truncado pela operadora intermediária ou finalização, a Microsoft terá pouco ou nenhum recurso para corrigir esses problemas na rede telefônica pública.

Inconsistências no CNAM podem ser causadas quando as operadoras intermediárias ou terminantes atrasam a atualização das informações cnam em bancos de dados autoritativos, como no caso dos Estados Unidos. Em países onde não há bancos de dados autoritativos para CNAM, as práticas de operadoras individuais também podem causar problemas com as informações cnam que chegam intactas com a chamada. No momento, a Microsoft não dá suporte à origem de informações cnam em países diferentes dos Estados Unidos.

## <a name="related-topics"></a>Tópicos relacionados


