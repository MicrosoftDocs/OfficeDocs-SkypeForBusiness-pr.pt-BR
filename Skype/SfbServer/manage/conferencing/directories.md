---
title: Criar diretórios de conferência em Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumo: saiba como criar diretórios de conferência em Skype for Business Server.'
---

# <a name="create-conference-directories-in-skype-for-business-server"></a>Criar diretórios de conferência em Skype for Business Server
 
**Resumo:** Saiba como criar diretórios de conferência em Skype for Business Server.
  
Os diretórios de conferência mantêm um mapeamento entre a ID de reunião alfanumérico que um participante usa para ingressar em uma conferência ao usar Skype for Business e a ID de conferência somente numérica que um participante de conferência discada usa para ingressar na conferência. 
  
## <a name="create-a-conference-directory"></a>Criar um diretório de conferência

A criação de vários diretórios de conferência garantirá que as IDs de conferência permaneçam curtas até que uma quantidade significativa de conferências tenha sido criada. 
  
Em uma organização com um número típico de conferências por usuário, recomendamos que você crie um diretório de conferência para cada 999 usuários no pool. Usando essa diretriz, as IDs de conferência geralmente podem ser mantidas pequenas. No entanto, quando o número de diretórios de conferência (entre os pools) exceder 9, o tamanho da ID da Conferência aumentará para dar suporte a conferências adicionais.
  
O formato de uma ID de conferência é o seguinte: 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Para criar um diretório de conferência, use o cmdlet **New-CsConferenceDirectory** . Por exemplo, o seguinte comando cria um diretório de conferência com a identidade 42, hospedado no pool atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Para obter mais informações, [consulte New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
