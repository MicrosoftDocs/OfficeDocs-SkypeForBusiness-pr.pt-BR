---
title: Tabela PurgeSettings
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhes de chamada desatualizados serão automaticamente excluídos do banco de dados cdr. Observe que as informações relacionadas à purga também podem ser obtidas de dentro do Skype for Business Server 2015 executando o seguinte comando:'
ms.openlocfilehash: c90c36dc91eaaac6fe38c6eea8e2a5617264e200
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823161"
---
# <a name="purgesettings-table"></a>Tabela PurgeSettings
 
A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhes de chamada desatualizados serão automaticamente excluídos do banco de dados cdr. Observe que as informações relacionadas à purga também podem ser obtidas de dentro do Skype for Business Server 2015 executando o seguinte comando:
  
```PowerShell
Get-CsCdrConfiguration
```

Os administradores devem tratar a tabela PurgeSettings como somente leitura: as alterações nas configurações de limpeza de detalhes das chamada só devem ser feitas usando os cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) ou [Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Primário  <br/> |Identificador exclusivo da coleção de configurações de limpeza de CDR.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Quando seu valor for definido com True (1), o Skype for Business Server 2015 limpará periodicamente os registros desatualizados do banco de dados de CDR. A limpeza ocorrerá todos os dias na hora especificada pela configuração PurgeHour. Se definido como Falso (0), os registros não serão limpados automaticamente do banco de dados. O valor padrão é verdadeiro.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Especifica a idade dos registros CDR (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros CDR mais antigos do que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Especifica a idade dos registros de relatório de erros (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros de relatório de erros anteriores a esse valor serão removidos do banco de dados. O valor padrão é 60 dias.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica a hora local do dia em que a limpeza ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 2 (2:00).  <br/> |
   

