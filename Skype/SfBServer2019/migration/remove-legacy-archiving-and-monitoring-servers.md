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
ms.localizationpriority: medium
description: Se sua implantação herdada contiver um Servidor de Arquivamento ou um Servidor de Monitoramento, depois de migrar para o Skype for Business Server 2019, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários tenham sido removidos de todos os pools herdados restantes. É possível remover o Servidor de Arquivamento ou o Monitoring Server em qualquer sequência. O requisito principal é que todos os usuários sejam removidos de quaisquer pools herdados restantes.
ms.openlocfilehash: 94ea83f767327d2c53cf6125a9c439753637e7dd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582095"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Remover servidores de Arquivamento e de Monitoramento herdados

Se sua implantação herdada contiver um Servidor de Arquivamento ou um Servidor de Monitoramento, depois de migrar para o Skype for Business Server 2019, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários tenham sido removidos de qualquer pool herdado restante. É possível remover o Servidor de Arquivamento ou o Monitoring Server em qualquer sequência. O requisito principal é que todos os usuários sejam removidos de quaisquer pools herdados restantes.
  
Você pode mover os usuários para Skype for Business Server 2019 seguindo os procedimentos descritos na Fase [4:](phase-4-move-test-users-to-the-pilot-pool.md)Mover usuários de teste para o pool piloto .
  
Depois de confirmar que todos os usuários foram removidos de qualquer pool restante, descommisione o servidor e remova funções. Um exemplo datado, mas relevante, é "Desinstalar o Microsoft Lync Server e Remover Funções de Servidor", que pode ser baixado em [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .
  

