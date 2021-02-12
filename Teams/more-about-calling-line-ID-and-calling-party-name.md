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
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador

CallerID, como normalmente é conhecido, na verdade consiste em duas informações de identificação do usuário:
    - Um número de telefone (normalmente chamado de CLID ou ID de linha de chamada) 
    - Nome da parte de chamada (normalmente conhecido como CNAM), que pode ter até 15 caracteres. 

Quando uma chamada é feita, a CLID (número de telefone) é roteada para a operadora do destino (também conhecida como operadora de término). As informações do CNAM para a chamada podem ou não ser roteada com a chamada, pois isso depende de como o país implementou o CNAM (se for o caso). A confiabilidade da entrega do CNAM com a chamada varia dependendo do país e das operadoras que lidam com a chamada como intermediário e/ou como operadora de terminação. 

A transmissão CLID & CNAM é de responsabilidade da transportadora de terminação na medida em que a operadora de terminação deve dar suporte à funcionalidade CLID & CNAM, bem como fornecer registros atualizados para ambos os valores. A Microsoft fornece valores CLID confiável ao originar chamadas, mas esses valores podem não ser mantidos intactos depois que passam por uma operadora intermediária ou pela operadora de terminação. Infelizmente, caso o valor de CLID seja alterado, omitido ou truncado pela operadora intermediária ou de terminação, a Microsoft tem pouco a não recurso para corrigir esses problemas na rede telefônica pública.

Inconsistências no CNAM podem ser causadas por atrasos na atualização das informações do CNAM em bancos de dados autoritativos, como no caso dos Estados Unidos. Em países em que não há um banco de dados autoritativo para CNAM, as práticas de operadoras individuais também podem causar problemas com as informações do CNAM que chegam intactas à chamada. Atualmente, a Microsoft não dá suporte a informações provenientes do CNAM em países diferentes dos Estados Unidos."

## <a name="related-topics"></a>Tópicos relacionados


