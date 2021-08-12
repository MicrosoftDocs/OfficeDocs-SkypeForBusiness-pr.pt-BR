---
title: Planejar alta disponibilidade e recuperação de desastres Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade do Servidor Back-End, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e SQL cluster de failover.
ms.openlocfilehash: c210e5b5db5470ac275bfe845c0c7c6700bfa96c73187cebdcf2785f8e19d85b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286300"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planejar alta disponibilidade e recuperação de desastres Skype for Business Server
 
Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade do Servidor Back-End, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e SQL cluster de failover. 
  
Alta disponibilidade refere-se a garantir que Skype for Business Server serviços de segurança estão disponíveis mesmo que um ou mais servidores sejam baixados. A recuperação de desastres refere-se à manutenção dos serviços no caso de um desastre natural ou causado por humanos e à preservação do máximo de dados de antes do desastre possível.
  
Como nas versões anteriores do Lync Server, o principal recurso de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server é a redundância do servidor por meio do pool. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor. Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.
  
Skype for Business Server também fornece opções de recuperação de desastres para pools de Front-End. Você pode configurar dois pools em áreas geográficas diferentes para servir como backups uns para os outros. Em seguida, se você tiver um pool ou site inteiro abaixo, o pool de backup poderá continuar a fornecer serviço aos usuários em ambos os sites.
  
O Skype for Business Server também oferece suporte a quatro modos de alta disponibilidade para seus Servidores Back-End: espelhamento de SQL, Grupos de Disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn (FCI) e SQL cluster de failover.
  
> [!NOTE]
> SQL O espelhamento está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn (FCI) e SQL de clustering de failover são preferenciais com o Skype for Business Server 2019.

> [!NOTE]
> Os Grupos de Disponibilidade AlwaysOn não são suportados com Servidores de Chat Persistente. 
  
Esta seção explica esses recursos e também aborda quais etapas você pode tomar para alta disponibilidade e recuperação de desastres para algumas de suas outras funções de servidor. 
  
## <a name="see-also"></a>Confira também

[Alta disponibilidade e gerenciamento do Pool de Front End](high-availability.md)
  
[Recuperação de desastre de pool de front-end no Skype for Business Server](disaster-recovery.md)
  
[Experiência do usuário durante falha no pool Skype for Business Server](user-experience.md)
  
[Alta disponibilidade do Servidor Back-End no Skype for Business Server](back-end-server.md)
  
[Alta disponibilidade de compartilhamento de arquivos Skype for Business Server](file-sharing.md)
