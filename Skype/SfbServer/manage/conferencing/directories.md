---
title: Criar diretórios de conferência no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumo: Saiba como criar diretórios de conferência no Skype para Business Server 2015.'
ms.openlocfilehash: aa261dbe92507fad2721f57d743be57bea89de2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="create-conference-directories-in-skype-for-business-server-2015"></a>Criar diretórios de conferência no Skype for Business Server 2015
 
**Resumo:** Aprenda a criar diretórios de conferência no Skype para Business Server 2015.
  
Diretórios de conferência mantêm um mapeamento entre o ID de reunião alfanuméricos que um participante usa para ingressar em uma conferência ao usar o Skype para negócios e a ID de conferência apenas numérica que um participante de conferência discada usa para ingressar na conferência. 
  
## <a name="create-a-conference-directory"></a>Criar um diretório de conferência

Criar vários diretórios de conferência garantirá que os IDs de conferência sejam curtos até que uma quantidade significativa de conferências seja criada. 
  
Em uma organização com um número comum de conferências por usuário, recomendamos criar um diretório de conferência para cada 999 usuários no pool. Usando essa diretriz, os IDs podem ser geralmente mantidos pequenos. No entanto, assim que o número de diretórios de conferência (em todos os pools) ultrapassar 9, o tamanho do ID de conferência aumentará para suportar conferências adicionais.
  
O formato de um ID de conferência é como segue: 
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

```

Para criar um novo diretório de conferência, use o cmdlet **New-CsConferenceDirectory**. Por exemplo, o seguinte cria um diretório de conferência com a identidade 42, hospedado no pool atl-cs-001.litwareinc.com:
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

```

Para obter mais informações, consulte [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

