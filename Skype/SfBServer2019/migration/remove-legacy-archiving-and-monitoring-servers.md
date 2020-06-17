---
title: Remover servidores de Arquivamento e de Monitoramento herdados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se sua implantação herdada contiver um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Skype for Business Server 2019, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários tenham sido removidos de qualquer pool herdado remanescente. É possível remover o Servidor de Arquivamento ou o Monitoring Server em qualquer sequência. O requisito principal é que todos os usuários sejam removidos de quaisquer pools herdados restantes.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752163"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Remover servidores de Arquivamento e de Monitoramento herdados

Se sua implantação herdada contiver um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Skype for Business Server 2019, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários tenham sido removidos de qualquer pool herdado remanescente. É possível remover o Servidor de Arquivamento ou o Monitoring Server em qualquer sequência. O requisito principal é que todos os usuários sejam removidos de quaisquer pools herdados restantes.
  
Você pode mover usuários para o Skype for Business Server 2019 seguindo os procedimentos descritos na [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
Após confirmar que todos os usuários foram removidos de todos os pools restantes, decommision o servidor e remova as funções. Uma data de um exemplo, mas relevante, é "desinstalação do Microsoft Lync Server e remoção de funções de servidor", que podem ser baixadas em [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .
  

