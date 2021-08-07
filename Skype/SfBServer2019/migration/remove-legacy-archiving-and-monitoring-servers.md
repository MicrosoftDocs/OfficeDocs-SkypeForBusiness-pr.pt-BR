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
description: Se sua implantação herdada contiver um Servidor de Arquivamento ou um Servidor de Monitoramento, depois de migrar para o Skype for Business Server 2019, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários tenham sido removidos de todos os pools herdados restantes. É possível remover o Servidor de Arquivamento ou o Monitoring Server em qualquer sequência. O requisito principal é que todos os usuários sejam removidos de quaisquer pools herdados restantes.
ms.openlocfilehash: 204c68a50585bae033149ea75077ab0801b0bcc4aecb642c52fa96442bfc42ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304713"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Remover servidores de Arquivamento e de Monitoramento herdados

Se sua implantação herdada contiver um Servidor de Arquivamento ou um Servidor de Monitoramento, depois de migrar para o Skype for Business Server 2019, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários tenham sido removidos de qualquer pool herdado restante. É possível remover o Servidor de Arquivamento ou o Monitoring Server em qualquer sequência. O requisito principal é que todos os usuários sejam removidos de quaisquer pools herdados restantes.
  
Você pode mover os usuários para Skype for Business Server 2019 seguindo os procedimentos descritos na Fase [4:](phase-4-move-test-users-to-the-pilot-pool.md)Mover usuários de teste para o pool piloto .
  
Depois de confirmar que todos os usuários foram removidos de qualquer pool restante, descommisione o servidor e remova funções. Um exemplo datado, mas relevante, é "Desinstalar o Microsoft Lync Server e Remover Funções de Servidor", que pode ser baixado em [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .
  

