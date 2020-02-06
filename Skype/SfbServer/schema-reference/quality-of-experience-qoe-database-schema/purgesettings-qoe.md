---
title: Tabela PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'A tabela PurgeSettings contém informações que especificam se (e quando) os registros de qualidade desatualizadas da qualidade da experiência serão automaticamente excluídos do banco de dados de QoE. Observe que as informações relacionadas à eliminação também podem ser obtidas dentro do Shell de gerenciamento do Skype for Business Server ao executar o seguinte comando:'
ms.openlocfilehash: dab1b2ffeab5882d0e459d7957b2817e780fc3a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807327"
---
# <a name="purgesettings-table-qoe"></a>Tabela PurgeSettings (QoE)
 
A tabela PurgeSettings contém informações que especificam se (e quando) os registros de qualidade desatualizadas da qualidade da experiência serão automaticamente excluídos do banco de dados de QoE. Observe que as informações relacionadas à eliminação também podem ser obtidas dentro do Shell de gerenciamento do Skype for Business Server ao executar o seguinte comando:
  
```PowerShell
Get-CsQoEConfiguration
```

Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo da coleção de configurações de limpeza de QoE.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Quando definido como true (1), o Microsoft Lync Server 2013 limpará periodicamente registros desatualizados do banco de dados de QoE. A limpeza ocorrerá a cada dia no Tomé especificado pela configuração PurgeHour. Se definido como falso (0), os registros não serão automaticamente limpos do banco de dados. O valor padrão é True.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Especifica a idade dos registros de QoE (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros de QoE anteriores a esse valor serão removidos do banco de dados. O valor padrão é 60 dias.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Especifica a hora local do dia em que a limpeza do banco de dados ocorrerá. O horário é especificado utilizando-se um relógio de 24 horas, onde 0 representa a meia-noite (00:00) e 23 representa 23 horas. Observe que você só pode especificar a hora do dia: é permitido um valor de 10 (indicando 10:00 AM), mas um valor de 10:30 de 10,5 (indicando 10:30 AM) não é permitido. O valor padrão é 1 (1:00 AM). Especifica a hora local do dia em que a limpeza do banco de dados ocorrerá. O horário é especificado utilizando-se um relógio de 24 horas, onde 0 representa a meia-noite (00:00) e 23 representa 23 horas. Observe que você só pode especificar a hora do dia: é permitido um valor de 10 (indicando 10:00 AM), mas um valor de 10:30 de 10,5 (indicando 10:30 AM) não é permitido. O valor padrão é 1 (1:00 AM).  <br/> |
   

