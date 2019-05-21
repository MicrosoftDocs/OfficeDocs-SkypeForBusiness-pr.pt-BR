---
title: Remover servidores de Arquivamento e de Monitoramento herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se sua implantação herdada continha um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Skype for Business Server 2019, esses servidores podem ser removidos do ambiente herdado desde que todos os usuários tenham sido removidos de todos os pools herdados restantes. Você pode remover o servidor de arquivamento ou o servidor de monitoramento em qualquer sequência. O requisito chave é que todos os usuários foram removidos de todos os pools herdados restantes.
ms.openlocfilehash: 918e04bb42853f0203ae8a2a56db5e640985af99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301122"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Remover servidores de Arquivamento e de Monitoramento herdados

Se sua implantação herdada continha um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Skype for Business Server 2019, esses servidores podem ser removidos do ambiente herdado, contanto que todos os usuários tenham sido removidos de todos os pools herdados restantes. Você pode remover o servidor de arquivamento ou o servidor de monitoramento em qualquer sequência. O requisito chave é que todos os usuários foram removidos de todos os pools herdados restantes.
  
Você pode mover usuários para o Skype for Business Server 2019 seguindo os procedimentos descritos na [fase 4: mover os usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
Depois de confirmar que todos os usuários foram removidos de todos os grupos restantes, decommision o servidor e remova as funções. Um exemplo de data e mais relevante é "desinstalar o Microsoft Lync Server e remover funções de servidor", cujo download pode ser feito [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)em.
  

