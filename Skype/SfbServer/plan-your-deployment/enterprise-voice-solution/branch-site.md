---
title: Entroncamento do site de filial do SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Saiba mais sobre o entroncamento SIP em sites de filiais no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 158c1cff28ba0c21f5c995a1fe5b7dfdf2f9f150
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803251"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Entroncamento do site de filial do SIP no Skype for Business Server
 
Saiba mais sobre o entroncamento SIP em sites de filiais no Skype for Business Server Enterprise Voice.
  
Em alguns casos, talvez seja necessário implementar o entroncamento SIP distribuído em sites de filiais selecionados. Para determinar se um tronco SIP é necessário para um site de filial e para obter detalhes sobre as opções de topologia com suporte para a implantação de troncos SIP em sites de filiais, consulte [entroncamento SIP no Skype for Business Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Análise de requisitos do tronco SIP do exemplo de local de filial

Ao decidir implantar um tronco SIP de site de filial, você precisa executar uma análise de custo específica do site. Por exemplo, uma empresa que tem um site central em Redmond, Washington e um site de filiais em Nova York, deve fazer uma análise para determinar se deve implementar um tronco SIP do site de Nova York para um provedor de serviços local.
  
Para determinar se um tronco SIP distribuído em Nova Iorque é uma opção com bom custo benefício, identifique quais números DID usarão o tronco SIP e analise o número de chamadas feitas de Nova Iorque para áreas diferentes de Redmond (425). Você pode ter cancelamento para o site de filial no site central. Por exemplo, o site central Redmond pode hospedar números para o site da filial de Nova York. Se o custo da implementação de um tronco SIP distribuído for menor que o custo dessas chamadas, considere a implementação de um tronco SIP no site da filial de Nova York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Outros requisitos de tronco SIP do local de filial

A opção entre uma implantação de um tronco SIP em vez de um gateway tem base na diferença entre as cobranças de PSTN de longa distância de cada opção. Se você implantar um tronco SIP de site de filial, também precisará determinar os requisitos de resiliência e largura de banda. Se o link entre o site de sua filial e o site central for resistente e tiver largura de banda suficiente, você poderá implantar um tronco SIP ou um gateway. Você não precisa implantar um aparelho de ramificação sobreviventes no site da filial. Se o link entre seu site de filial e o site central não for resistente, implante um aparelho de ramificação sobreviventes ou implante um servidor de ramificação sobreviventes com um tronco de gateway ou SIP no site da filial. 
  

