---
title: Migrar vários sites e pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'O Skype for Business Server 2019 oferece suporte a implantações de vários locais e vários pools. O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações:'
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813439"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrar vários sites e pools

O Skype for Business Server 2019 oferece suporte a implantações de vários locais e vários pools. O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações: 
  
1. Depois de implantar um pool piloto do Skype for Business Server 2019, você precisa definir um subconjunto de usuários pilotos que serão movidos para o pool do Skype for Business Server 2019 e uma metodologia para validar a funcionalidade dos usuários. Por exemplo, depois de mover um usuário para o pool piloto, verifique se a política de conferência do usuário mudou para o Skype for Business Server 2019. 
    
2. Depois de implantar um servidor de borda no pool piloto, você precisa validar que os usuários externos podem se comunicar com o pool do Skype for Business Server 2019.

3. O chat persistente, o espelhamento do SQL e a funcionalidade do XMPP são preteridos no Skype for Business Server 2019 e não estão mais disponíveis como recursos do Skype for Business Server 2019, mas eles podem continuar em um ambiente de coexistência se eles foram implantados anteriormente em um ambiente herdado. Se quiser continuar a usar esses recursos, você deve planejar para continuar com um ambiente de coexistência em que determinados usuários permanecerão em pools herdados.
    
4. Depois de fazer a transição dos servidores de borda de rotas federadas para os servidores piloto do Skype for Business Server 2019, você precisa validar que os usuários federados podem se comunicar com o pool do Skype for Business Server 2019.
    
5. Depois de mover todos os usuários e objetos de contato que não sejam usuários, você precisa validar que o pool herdado está vazio.
    
6. Depois de verificar se o pool herdado está vazio, você pode desativar o pool. 
    
    Para obter detalhes sobre como desativar o pool herdado e os servidores, consulte [fase 8: descomissionar pools herdados](phase-8-decommission-legacy-pools.md).
    

