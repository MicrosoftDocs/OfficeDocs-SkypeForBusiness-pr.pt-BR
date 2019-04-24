---
title: Tabela PurgeSettings
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhe de chamada desatualizada serão excluídos automaticamente do banco de dados de CDR. Observe que informações relacionadas a limpeza também podem ser obtidas no dentro do Skype para Business Server 2015 executando o seguinte comando:'
ms.openlocfilehash: 10dd9c6969f84453c880de130222b3b9d71db77a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212835"
---
# <a name="purgesettings-table"></a>Tabela PurgeSettings
 
A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhe de chamada desatualizada serão excluídos automaticamente do banco de dados de CDR. Observe que informações relacionadas a limpeza também podem ser obtidas no dentro do Skype para Business Server 2015 executando o seguinte comando:
  
```
Get-CsCdrConfiguration
```

Os administradores devem tratar a tabela PurgeSettings como somente leitura: alterações para as configurações de limpeza de detalhes de chamada só devem ser feitas usando os cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) ou [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo da coleção de CDR configurações de limpeza.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Quando definido para verdadeiro (1) Skype para Business Server 2015 periodicamente descartará desatualizadas registros do banco de dados de CDR. Limpeza ocorrerá cada dia em que o Tomé especificado pela definição PurgeHour. Se definido como False (0) registros, em seguida, não será removido automaticamente do banco de dados. O valor padrão é True.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Especifica a idade dos registros de CDR (em dias) que serão removidos do banco de dados: se limpeza estiver habilitada, CDR registros mais antigos do que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Especifica a idade dos registros de relatório de erro (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, registros de relatório de erros mais antigos do que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica a hora local do dia quando a limpeza do banco de dados entrarão em vigor. O horário é especificado utilizando-se um relógio de 24 horas, onde 0 representa a meia-noite (00:00) e 23 representa 23 horas. Observe que você pode especificar apenas a hora do dia: um valor de 10 (indicando a 10:00 AM) é permitido, mas o valor 10:30 do 10.5 (indicando 10:30 AM) não é permitido. O valor padrão é 2 (2:00).  <br/> |
   

