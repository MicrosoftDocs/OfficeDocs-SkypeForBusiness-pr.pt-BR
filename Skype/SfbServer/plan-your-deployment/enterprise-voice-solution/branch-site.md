---
title: Tronco SIP de site de filial no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Saiba mais sobre tronco SIP em sites de filiais Skype for Business Server Enterprise Voice.
ms.openlocfilehash: b8c1c930bb2500ca9330b14cce7fd5b341db60a9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829895"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Tronco SIP de site de filial no Skype for Business Server
 
Saiba mais sobre tronco SIP em sites de filiais Skype for Business Server Enterprise Voice.
  
Em alguns casos, talvez seja necessário implementar troncos SIP distribuídos em sites de filial selecionados. Para determinar se um tronco SIP é necessário para um site de filial e para obter detalhes sobre as opções de topologia suportadas para implantar troncos SIP em sites de filial, consulte [Tronco SIP](sip-trunking.md)em Skype for Business Server .
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Análise de requisitos do tronco SIP do exemplo de site de filial

Ao decidir implantar um tronco SIP de site de filial, você precisa executar uma análise de custo específica do site. Por exemplo, uma empresa que tenha um site central em Redmond, Washington e um site de filial em Nova York, deve fazer uma análise para determinar se deve implementar um tronco SIP do site de Nova York para um provedor de serviços local.
  
Para determinar se um tronco SIP distribuído em Nova Iorque é uma opção com bom custo benefício, identifique quais números DID usarão o tronco SIP e analise o número de chamadas feitas de Nova Iorque para áreas diferentes de Redmond (425). Você pode ter a terminação DID para o site de filial no site central. Por exemplo, o site central de Redmond pode hospedar números DID para o site de filial de Nova York. Se o custo da implementação de um tronco SIP distribuído for menor do que o custo dessas chamadas, considere implementar um tronco SIP no site da filial de Nova York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Outros requisitos de tronco SIP do site de filial

A opção entre uma implantação de um tronco SIP em vez de um gateway tem base na diferença entre as cobranças de PSTN de longa distância de cada opção. Se você implantar um tronco SIP de site de filial, também precisará determinar seus requisitos de resiliência e largura de banda. Se o link entre seu site de filial e o site central for resiliente e tiver largura de banda suficiente, você poderá implantar um tronco SIP ou um gateway. Você não precisa implantar um Aparelho de Filial Desavivável no site da filial. Se o link entre seu site de filial e o site central não for resiliente, implante um Aparelho de Filial Persistente ou implante um Servidor de Filial Persistente com um gateway ou tronco SIP no site da filial. 
  

