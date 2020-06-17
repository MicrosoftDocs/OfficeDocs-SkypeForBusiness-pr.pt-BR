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
description: 'O Skype for Business Server 2019 oferece suporte a implantações de vários locais e vários pools. O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752653"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrar vários sites e pools

O Skype for Business Server 2019 oferece suporte a implantações de vários locais e vários pools. O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações: 
  
1. Depois de implantar um pool piloto do Skype for Business Server 2019, você precisa definir um subconjunto de usuários piloto que serão movidos para o pool do Skype for Business Server 2019 e uma metodologia para validar a funcionalidade dos usuários. Por exemplo, depois de mover um usuário para o pool piloto, verifique se a política de conferência do usuário foi movida para o Skype for Business Server 2019. 
    
2. Após implantar um servidor de borda no pool piloto, você precisará validar que os usuários externos podem se comunicar com o pool do Skype for Business Server 2019.

3. O chat persistente, o espelhamento do SQL e a funcionalidade do XMPP são preteridos no Skype for Business Server 2019 e não estão mais disponíveis como recursos do Skype for Business Server 2019, mas podem ser continuados em um ambiente de coexistência, caso tenham sido implantados anteriormente em um ambiente herdado. Se quiser continuar usando esses recursos, você deve planejar para continuar com um ambiente de coexistência onde determinados usuários permanecerão em pools herdados.
    
4. Após a transição dos servidores de borda de rotas federadas para os servidores de borda do Skype for Business Server 2019 piloto, você precisará validar que os usuários federados podem se comunicar com o pool do Skype for Business Server 2019.
    
5. Após mover todos os objetos de contato de usuários e não usuários, é necessário validar que o pool herdado está vazio.
    
6. Depois de verificar se o pool herdado está vazio, é possível desativar o pool. 
    
    Para obter detalhes sobre como desativar o pool herdado e servidores, consulte [fase 8: encerrar pools herdados](phase-8-decommission-legacy-pools.md).
    

