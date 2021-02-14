---
title: Tipo de regra de conversão uma expressão regular
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: No campo Corresponder a este padrão, especifique o padrão que será usado para corresponder os números a serem convertidos. No campo Regra de conversão, especifique o padrão para o formato dos números convertidos. Por exemplo, se você inserir ^ (\d \d+)$ no campo Corresponder este padrão e 011$1 no campo de regra de conversão, a regra traduzirá \+ {9} +441235551010 para 011441235551010.
ms.openlocfilehash: badbc5a34325e6bc2b5bef7e67ae39a4c8f02dc7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818851"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="2b9c4-105">Regra de Conversão: Digite uma Expressão Regular</span><span class="sxs-lookup"><span data-stu-id="2b9c4-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="2b9c4-106">No campo **Corresponder a este padrão**, especifique o padrão que será usado para corresponder os números a serem convertidos.</span><span class="sxs-lookup"><span data-stu-id="2b9c4-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="2b9c4-107">No campo **Regra de conversão**, especifique o padrão para o formato dos números convertidos.</span><span class="sxs-lookup"><span data-stu-id="2b9c4-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="2b9c4-108">Por exemplo, se você inserir ^ (\d \d+)$ no campo Corresponder este padrão e 011$1 no campo de regra de conversão, a regra traduzirá \+ {9} +441235551010 para 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="2b9c4-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="2b9c4-109">Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o Painel de Controle do Skype for Business Server, consulte [Gerenciar o Skype for Business Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="2b9c4-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

