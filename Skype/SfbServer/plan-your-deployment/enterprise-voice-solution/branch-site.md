---
title: Tronco Branch site SIP no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Saiba mais sobre o tronco SIP em sites de filial em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 333cb5f150efb431d4c7c43a0d78b601cb8ff268
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207080"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Tronco Branch site SIP no Skype para Business Server
 
Saiba mais sobre o tronco SIP em sites de filial em Skype para Business Server Enterprise Voice.
  
Em alguns casos, você precisará implementar o tronco SIP distribuído em sites de filiais selecionado. Para determinar se um SIP tronco é necessária para um site de filial e para obter detalhes sobre as opções de topologia suportadas para a implantação de troncos SIP nos sites de filiais, consulte o [tronco SIP no Skype para Business Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Análise de requisitos do tronco SIP do exemplo de local de filial

Quando você decide implantar um tronco SIP do site de filial, você precisará executar uma análise de custo específicas do site. Por exemplo, uma empresa que tenha um site central em Redmond, Washington e um site de filial em Nova York, deverá fazer uma análise para determinar se você implementar um tronco SIP do site Nova York a um provedor de serviço local.
  
Para determinar se um tronco SIP distribuído em Nova Iorque é uma opção com bom custo benefício, identifique quais números DID usarão o tronco SIP e analise o número de chamadas feitas de Nova Iorque para áreas diferentes de Redmond (425). Você pode ter DID terminação para o site da filial no site central. Por exemplo, o site central Redmond pode hospedar números DID para o site de filial de Nova York. Se o custo de implementar um tronco SIP distribuído for menor que o custo dessas chamadas, considere a implementação de um tronco SIP no site da filial de Nova York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Outros requisitos de tronco SIP do local de filial

A opção entre uma implantação de um tronco SIP em vez de um gateway tem base na diferença entre as cobranças de PSTN de longa distância de cada opção. Se você implantar um tronco SIP do site de filial, você também precisará determinar os requisitos de resiliência e largura de banda. Se o vínculo entre o seu site de filial e o site central é resiliente e tem a largura de banda suficiente, você pode implantar um tronco SIP ou um gateway. Você não precisará implantar um aparelho de filial persistente no site da filial. Se o vínculo entre o seu site de filial e o site central não for resiliente, implante um aparelho de filial persistente ou implantar um servidor de filial persistente com um gateway ou tronco SIP no site da filial. 
  

