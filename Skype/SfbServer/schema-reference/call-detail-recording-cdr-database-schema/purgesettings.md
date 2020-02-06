---
title: Tabela PurgeSettings
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhes de chamadas desatualizados serão automaticamente excluídos do banco de dados CDR. Observe que as informações relacionadas à eliminação também podem ser obtidas no Skype for Business Server 2015 executando o seguinte comando:'
ms.openlocfilehash: 81e702a4d62b4c85fb849a768c97428719ddc391
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814959"
---
# <a name="purgesettings-table"></a>Tabela PurgeSettings
 
A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhes de chamadas desatualizados serão automaticamente excluídos do banco de dados CDR. Observe que as informações relacionadas à eliminação também podem ser obtidas no Skype for Business Server 2015 executando o seguinte comando:
  
```PowerShell
Get-CsCdrConfiguration
```

Os administradores devem tratar a tabela PurgeSettings como somente leitura: as alterações nas configurações de limpeza de detalhes da chamada devem ser feitas somente usando cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) ou [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**%** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo da coleção de configurações de limpeza de CDR.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Quando definida como true (1), o Skype for Business Server 2015 limpará periodicamente registros desatualizados do banco de dados CDR. A limpeza ocorrerá a cada dia no Tomé especificado pela configuração PurgeHour. Se definido como falso (0), os registros não serão automaticamente limpos do banco de dados. O valor padrão é True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Especifica a idade dos registros CDR (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros CDR mais antigos do que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Especifica a idade dos registros de relatório de tempo (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros de relatório de erros anteriores a esse valor serão removidos do banco de dados. O valor padrão é 60 dias.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica a hora local do dia em que a limpeza do banco de dados ocorrerá. O horário é especificado utilizando-se um relógio de 24 horas, onde 0 representa a meia-noite (00:00) e 23 representa 23 horas. Observe que você só pode especificar a hora do dia: é permitido um valor de 10 (indicando 10:00 AM), mas um valor de 10:30 de 10,5 (indicando 10:30 AM) não é permitido. O valor padrão é 2 (2:00).  <br/> |
   

