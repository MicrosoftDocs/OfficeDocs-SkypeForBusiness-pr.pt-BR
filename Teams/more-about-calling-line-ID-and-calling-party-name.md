---
title: Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador
ms.author: tonysmit
author: tonysmit
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
- NOCSH
ms.custom:
- Calling Plans
description: Saiba por que você precisa adicionar uma pessoa autorizada que pode fazer alterações na conta quando você usa o assistente de nova ordem de número local.
ms.openlocfilehash: a687bc1aca8a47b349415d4a0cc2dc9f61f81884
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708797"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Mais informações sobre a Identificação da Linha de Chamada e o Nome do Chamador

A identificação de chamada, como normalmente é referida, consiste, na verdade, de duas informações identificáveis pelo usuário:
    - Um número de telefone (geralmente chamado de identificação de linha de chamada ou de CLID) 
    - Nome do participante da chamada (geralmente chamado de CNAM), que pode ter até 15 caracteres de comprimento. 

Quando uma chamada é feita, a CLID (número de telefone) é roteada para a portadora do destino (também conhecida como a operadora de terminação). As informações CNAM da chamada podem ou não ser roteadas com a chamada, pois isso depende de como o país implementou CNAM (se houver). A confiabilidade da entrega do CNAM com a chamada varia de acordo com o país e as operadoras que manipulam a chamada como um intermediário e/ou uma operadora de terminação. 

A CNAM a transmissão do & CLID não é responsável pela concessionária da operadora de terminação, pois a operadora de terminação deve dar suporte à funcionalidade CLID & CNAM, além de fornecer registros atualizados para ambos os valores. A Microsoft fornece valores de CLID de forma confiável ao fazer chamadas, mas esses valores podem não ser mantidos intactos quando passam por uma operadora de telefonia ou de terminação. Infelizmente, no caso de o valor de CLID ser alterado, omitido ou truncado pelo intermediário ou pela operadora de terminação, a Microsoft tem pouco ou nenhum recurso para corrigir tais problemas na rede telefônica pública.

As inconsistências no CNAM podem ser causadas por atrasos em transportadoras intermediárias ou de terminação atualizando as informações de CNAM em bancos de dados autoritativos, como no caso dos Estados Unidos. Em países onde não há banco de dados autoritativo para CNAM, as práticas individuais da operadora também podem causar problemas com as informações do CNAM que chegam em tact com a chamada. Atualmente, a Microsoft não oferece suporte a informações de CNAM de origem em países que não sejam os Estados Unidos. "

## <a name="related-topics"></a>Tópicos relacionados


