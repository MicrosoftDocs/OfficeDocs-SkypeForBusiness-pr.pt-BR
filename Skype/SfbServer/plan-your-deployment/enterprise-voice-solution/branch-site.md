---
title: Tronco SIP do site de filial no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Saiba mais sobre o tronco SIP em sites de filial no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813711"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Tronco SIP do site de filial no Skype for Business Server
 
Saiba mais sobre o tronco SIP em sites de filial no Skype for Business Server Enterprise Voice.
  
Em alguns casos, talvez seja necessário implementar o tronco SIP distribuído em sites de filial selecionados. Para determinar se um tronco SIP é necessário para um site de filial e para obter detalhes sobre as opções de topologia com suporte para implantar troncos SIP em sites de filial, consulte tronco SIP no [Skype for Business Server.](sip-trunking.md)
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Análise de requisitos do tronco SIP do exemplo de site de filial

Ao decidir implantar um tronco SIP do site de filial, você precisa executar uma análise de custo específica do site. Por exemplo, uma empresa que tenha um site central em Redmond, Washington e um site de filial em Nova York, deve fazer uma análise para determinar se deve implementar um tronco SIP do site de Nova York para um provedor de serviços local.
  
Para determinar se um tronco SIP distribuído em Nova Iorque é uma opção com bom custo benefício, identifique quais números DID usarão o tronco SIP e analise o número de chamadas feitas de Nova Iorque para áreas diferentes de Redmond (425). Você pode ter a terminação DID para o site de filial no site central. Por exemplo, o site central redmond pode hospedar números DID para o site de filial de Nova York. Se o custo da implementação de um tronco SIP distribuído for menor do que o custo dessas chamadas, considere a implementação de um tronco SIP no site de filial de Nova York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Outros requisitos de tronco SIP do site de filial

A opção entre uma implantação de um tronco SIP em vez de um gateway tem base na diferença entre as cobranças de PSTN de longa distância de cada opção. Se você implantar um tronco SIP do site de filial, também precisará determinar seus requisitos de resiliência e largura de banda. Se o link entre o site de filial e o site central for resiliente e tiver largura de banda suficiente, você poderá implantar um tronco SIP ou um gateway. Não é necessário implantar um Aparelho de FilialVivível no site de filial. Se o link entre o site de filial e o site central não for resiliente, implante um Aparelho de Filial Persistente ou implante um Servidor de Filial Persistente com um gateway ou tronco SIP no site de filial. 
  

