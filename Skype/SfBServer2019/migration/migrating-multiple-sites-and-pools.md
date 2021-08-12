---
title: Migrar vários sites e pools
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
description: 'Skype for Business Server 2019 oferece suporte a implantações de vários sites e vários pools. O processo de migração de vários pools para Skype for Business Server 2019 requer as seguintes considerações:'
ms.openlocfilehash: 445c519fd9a470002258ff50c14ebac7328979acc667c60a77b15a503ec3f3fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303435"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrar vários sites e pools

Skype for Business Server 2019 oferece suporte a implantações de vários sites e vários pools. O processo de migração de vários pools para Skype for Business Server 2019 requer as seguintes considerações: 
  
1. Depois de implantar um pool piloto do Skype for Business Server 2019, você precisa definir um subconjunto de usuários piloto que serão movidos para o pool do Skype for Business Server 2019 e uma metodologia para validar a funcionalidade dos usuários. Por exemplo, depois de mover um usuário para o pool piloto, verifique se a política de conferência do usuário foi movida para Skype for Business Server 2019. 
    
2. Depois de implantar um Servidor de Borda no pool piloto, você precisa validar que os usuários externos podem se comunicar com o pool Skype for Business Server 2019.

3. A funcionalidade de Chat Persistente, espelhamento de SQL e XMPP é preterida no Skype for Business Server 2019 e não está mais disponível como recursos do Skype for Business Server 2019, mas podem continuar em um ambiente de coexistência se eles foram implantados anteriormente em um ambiente herdado. Se quiser continuar usando esses recursos, planeje continuar com um ambiente de coexistência onde determinados usuários permanecerão em pools herdado.
    
4. Depois de fazer a transição dos Servidores de Borda das rotas federadas para os Servidores de Borda piloto Skype for Business Server 2019, você precisa validar que os usuários federados podem se comunicar com o pool Skype for Business Server 2019.
    
5. Depois de mover todos os usuários e objetos de contato não usuários, você precisa validar se o pool herdado está vazio.
    
6. Depois de verificar se o pool herdado está vazio, você pode desativar o pool. 
    
    Para obter detalhes sobre como desativar o pool e servidores herdados, consulte [Fase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).
    

