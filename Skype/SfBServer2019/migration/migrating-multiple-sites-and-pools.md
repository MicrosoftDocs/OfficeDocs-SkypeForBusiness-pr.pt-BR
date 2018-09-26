---
title: Migrando múltiplos sites e pools
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype para Business Server 2019 oferece suporte a implantações de vários locais e do pool de múltiplos. O processo de migração de vários pools para Skype for Business Server 2019 requer as seguintes considerações:'
ms.openlocfilehash: 9716df65acfde26c41001bbc252b746ea1bd5241
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028744"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrando múltiplos sites e pools

Skype para Business Server 2019 oferece suporte a implantações de vários locais e do pool de múltiplos. O processo de migração de vários pools para Skype for Business Server 2019 requer as seguintes considerações: 
  
1. Após implantar um Skype para Business Server 2019 o pool piloto, você precisará definir um subconjunto dos usuários piloto que serão movidas para o Skype para Business Server 2019 pool e uma metodologia para validar a funcionalidade dos usuários. Por exemplo, depois de mover um usuário para o pool piloto, verifique se que a política de conferência do usuário foi movido para Skype para Business Server 2019. 
    
2. Depois de implantar um servidor de borda no pool piloto, você precisará validar que os usuários externos podem se comunicar com o Skype para Business Server 2019 pool.

3. Chat persistente, espelhamento SQL e a funcionalidade XMPP são preteridos no Skype para Business Server 2019 e não está disponível como Skype para recursos de Business Server 2019, mas pode ser continuadas em um ambiente de coexistência se eles foram implantados anteriormente em um ambiente de legado. Se você deseja continuar a usar esses recursos, você deve planejar continuar com um ambiente de coexistência onde determinados usuários permanecerá em pools herdados.
    
4. Após a transição servidores das rotas federadas de borda para o piloto Skype para os servidores de borda de 2019 Business Server, você precisará validar que os usuários federados podem se comunicar com o Skype para Business Server 2019 pool.
    
5. Depois de mover todos os usuários e objetos de contato não usuários, você precisará validar que o pool herdado está vazio.
    
6. Depois de verificar se o pool herdado está vazio, você pode desativar o pool. 
    
    Para obter detalhes sobre como desativar o pool herdado herdado e servidores, consulte [fase 8: encerre os pools herdados](phase-8-decommission-legacy-pools.md).
    

