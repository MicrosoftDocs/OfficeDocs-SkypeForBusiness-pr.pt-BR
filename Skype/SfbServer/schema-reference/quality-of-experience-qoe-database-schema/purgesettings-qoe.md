---
title: Tabela PurgeSettings (QoE)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'A tabela PurgeSettings contém informações que especificam se (e quando) registros desatualizados do Quality of Experience serão excluídos automaticamente do banco de dados de QoE. Observe que informações relacionadas a limpeza também podem ser obtidas no dentro do Skype do Shell de gerenciamento do servidor de negócios, executando o seguinte comando:'
ms.openlocfilehash: b9aaa8b5fd988e1fb1476ec75077507b55aaf9d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873616"
---
# <a name="purgesettings-table-qoe"></a>Tabela PurgeSettings (QoE)
 
A tabela PurgeSettings contém informações que especificam se (e quando) registros desatualizados do Quality of Experience serão excluídos automaticamente do banco de dados de QoE. Observe que informações relacionadas a limpeza também podem ser obtidas no dentro do Skype do Shell de gerenciamento do servidor de negócios, executando o seguinte comando:
  
```
Get-CsQoEConfiguration
```

Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo da coleção de QoE de configurações de limpeza.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Quando definido como verdadeiro (1) o Microsoft Lync Server 2013 periodicamente limpar registros desatualizados do banco de dados de QoE. Limpeza ocorrerá cada dia em que o Tomé especificado pela definição PurgeHour. Se definido como False (0) registros, em seguida, não será removido automaticamente do banco de dados. O valor padrão é True.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Especifica a idade dos registros de QoE (em dias) que serão removidos do banco de dados: se limpeza estiver habilitada, os registros de QoE mais antigos do que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica a hora local do dia quando a limpeza do banco de dados entrarão em vigor. O horário é especificado utilizando-se um relógio de 24 horas, onde 0 representa a meia-noite (00:00) e 23 representa 23 horas. Observe que você pode especificar apenas a hora do dia: um valor de 10 (indicando a 10:00 AM) é permitido, mas o valor 10:30 do 10.5 (indicando 10:30 AM) não é permitido. O valor padrão é 1 (1:00 AM). Especifica a hora local do dia quando a limpeza do banco de dados entrarão em vigor. O horário é especificado utilizando-se um relógio de 24 horas, onde 0 representa a meia-noite (00:00) e 23 representa 23 horas. Observe que você pode especificar apenas a hora do dia: um valor de 10 (indicando a 10:00 AM) é permitido, mas o valor 10:30 do 10.5 (indicando 10:30 AM) não é permitido. O valor padrão é 1 (1:00 AM).  <br/> |
   

