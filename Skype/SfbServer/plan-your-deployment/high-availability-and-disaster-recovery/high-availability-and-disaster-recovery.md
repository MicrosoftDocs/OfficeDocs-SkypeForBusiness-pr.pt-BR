---
title: Planejar alta disponibilidade e recuperação de desastre no Skype for Business Server
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
description: 'O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastre com emparelhamento de pool e vários modos de alta disponibilidade do Servidor #A0, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover sql.'
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802811"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planejar alta disponibilidade e recuperação de desastre no Skype for Business Server
 
O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastre com emparelhamento de pool e vários modos de alta disponibilidade do Servidor #A0, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover sql. 
  
Alta disponibilidade refere-se a garantir que os serviços do Skype for Business Server estão disponíveis mesmo que um ou mais servidores caiam. A recuperação de desastre refere-se a manter os serviços em caso de desastre natural ou causado por humanos e preservar o máximo de dados de antes do desastre possível.
  
Como nas versões anteriores do Lync Server, o principal recurso de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server é a redundância de servidor via pooling. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor. Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.
  
O Skype for Business Server também fornece opções de recuperação de desastre para pools de Front-End. Você pode configurar dois pools em áreas geográficas diferentes para servirem como backups um do outro. Em seguida, se você tiver um pool ou site inteiro para baixo, o pool de backup pode continuar a fornecer serviço aos usuários em ambos os sites.
  
O Skype for Business Server também oferece suporte a quatro modos de alta disponibilidade para seus Servidores #A0: espelhamento SQL, Grupos de Disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn (FCI) e clustering de failover sql.
  
> [!NOTE]
> O espelhamento sql está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e métodos de cluster de failover SQL são preferenciais com o Skype for Business Server 2019.

> [!NOTE]
> Os Grupos de Disponibilidade AlwaysOn não são suportados com Servidores de Chat Persistente. 
  
Esta seção explica esses recursos e também aborda quais etapas você pode seguir para alta disponibilidade e recuperação de desastres para algumas de suas outras funções de servidor. 
  
## <a name="see-also"></a>Confira também

[Alta disponibilidade e gerenciamento do Pool de Front-End](high-availability.md)
  
[Recuperação de desastre do pool de front-end no Skype for Business Server](disaster-recovery.md)
  
[Experiência do usuário durante falha do pool no Skype for Business Server](user-experience.md)
  
[Alta disponibilidade do Servidor back-end no Skype for Business Server](back-end-server.md)
  
[Alta disponibilidade de compartilhamento de arquivos no Skype for Business Server](file-sharing.md)
