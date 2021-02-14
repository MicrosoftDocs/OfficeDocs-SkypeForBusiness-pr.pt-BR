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
description: 'O Skype for Business Server 2019 oferece suporte a implantações de vários sites e de vários pools. O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752653"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrar vários sites e pools

O Skype for Business Server 2019 oferece suporte a implantações de vários sites e de vários pools. O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações: 
  
1. Depois de implantar um pool piloto do Skype for Business Server 2019, você precisará definir um subconjunto de usuários piloto que serão movidos para o pool do Skype for Business Server 2019 e uma metodologia para validar a funcionalidade dos usuários. Por exemplo, depois de mover um usuário para o pool piloto, verifique se a política de conferência do usuário foi movida para o Skype for Business Server 2019. 
    
2. Depois de implantar um Servidor de Borda no pool piloto, você precisará validar se os usuários externos podem se comunicar com o pool do Skype for Business Server 2019.

3. As funcionalidades de Chat Persistente, Espelhamento SQL e XMPP foram preteridas no Skype for Business Server 2019 e não estão mais disponíveis como recursos do Skype for Business Server 2019, mas podem continuar em um ambiente de coexistência se foram implantadas anteriormente em um ambiente herdado. Se você quiser continuar usando esses recursos, planeje continuar com um ambiente de coexistência onde determinados usuários permanecerão em pools herdado.
    
4. Após a transição dos Servidores de Borda das rotas federadas para os Servidores de Borda do Skype for Business Server 2019 piloto, você precisa validar se os usuários federados podem se comunicar com o pool do Skype for Business Server 2019.
    
5. Depois de mover todos os objetos de contato de usuários e não usuários, você precisa validar se o pool herdado está vazio.
    
6. Depois de verificar se o pool herdado está vazio, você pode desativar o pool. 
    
    Para obter detalhes sobre como desativar o pool e servidores herdados, consulte a Fase [8: Desativar pools herdados.](phase-8-decommission-legacy-pools.md)
    

