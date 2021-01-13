---
title: Tabela PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'A tabela PurgeSettings contém informações que especificam se (e quando) os registros de qualidade de experiência defasados serão excluídos automaticamente do banco de dados de QoE. Observe que as informações relacionadas à purga também podem ser obtidas de dentro do Shell de Gerenciamento do Skype for Business Server executando o seguinte comando:'
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815801"
---
# <a name="purgesettings-table-qoe"></a>Tabela PurgeSettings (QoE)
 
A tabela PurgeSettings contém informações que especificam se (e quando) os registros de qualidade de experiência defasados serão excluídos automaticamente do banco de dados de QoE. Observe que as informações relacionadas à purga também podem ser obtidas de dentro do Shell de Gerenciamento do Skype for Business Server executando o seguinte comando:
  
```PowerShell
Get-CsQoEConfiguration
```

Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primário  <br/> |Identificador exclusivo do conjunto de configurações de limpeza de QoE.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Quando seu valor for definido com True (1), o Microsoft Lync Server 2013 limpará periodicamente os registros desatualizados do banco de dados de QoE. A limpeza ocorrerá todos os dias na hora especificada pela configuração PurgeHour. Se definido como Falso (0), os registros não serão limpados automaticamente do banco de dados. O valor padrão é verdadeiro.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Especifica a idade dos registros de QoE (em dias) que serão limpados do banco de dados: se a limpeza estiver ativada, os registros de QoE mais antigos que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica a hora local do dia em que a limpeza ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 1 (1:00). Especifica a hora local do dia em que a limpeza do banco de dados ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 1 (1:00).  <br/> |
   

