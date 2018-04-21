---
title: Mais informações sobre como chamar o ID de linha e chamar o nome do participante
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: deb4320617d1840f2a237776ed0c4dc584fc2964
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Mais informações sobre como chamar o ID de linha e chamar o nome do participante

ID do chamador, como ele geralmente conhecidas, realmente consiste de duas voltados para o usuário identificáveis partes das informações:
    - Um número de telefone (geralmente conhecido como CLID ou chamada de ID de linha) 
    - Chamar o nome do participante (geralmente conhecido como CNAM) que pode ser até 15 caracteres de comprimento. 

Quando uma chamada for feita, a CLID (número de telefone) é encaminhado para operadora do destino (também conhecido como terminação operadora). As informações CNAM para a chamada podem ou não poderão ser roteadas com a chamada conforme isso depende de como o país implementou CNAM (se nisso). A confiabilidade de entrega CNAM com a chamada varia dependendo do país e operadoras que lidam com a chamada como um intermediário e/ou uma operadora de telefonia de encerramento. 

Transmissão CLID & CNAM é responsabilidade da transportadora terminação na medida a operadora terminação deve oferecer suporte à funcionalidade CLID & CNAM assim como fornecer registros atualizados dos dois valores. A Microsoft fornece valores CLID confiável ao originar chamadas, mas esses valores podem não ser mantidos intactos depois que eles passam por uma operadora intermediária ou a operadora de encerramento. Infelizmente, no caso do valor CLID for alterado, omitido ou truncado pela transportadora intermediária ou encerramento, a Microsoft não tem pouco ou nenhum recursos correção desses problemas na rede telefônica pública.

Inconsistências no CNAM podem ser causadas por atrasos na intermediários ou encerramento operadoras atualizando info CNAM nos bancos de dados autoritativos, como Estados Unidos. Em países onde não há nenhum banco de dados autoritativo para CNAM, práticas de operadora individuais também podem causar problemas com informações de CNAM que chegam intacto com a chamada. Microsoft atualmente não suporta informações do originador CNAM fora dos Estados Unidos países."

## <a name="related-topics"></a>Tópicos relacionados


