---
title: Adicionar FQDN do Pool de aplicativos confiáveis
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir um nome de domínio totalmente qualificado do pool de aplicativos confiáveis (FQDN), especifique o seguinte:'
ms.openlocfilehash: c8241e5e037b4f7993c73e1a10982465ac14dcaf
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21067606"
---
# <a name="add-trusted-application-pool-fqdn"></a>Adicionar FQDN do Pool de aplicativos confiáveis
 
Para definir um nome de domínio totalmente qualificado do pool de aplicativos confiáveis (FQDN), especifique o seguinte:
  
Um FQDN do servidor ou pool de servidores que hospedará os aplicativos confiáveis.
  
Se você estiver implantando um pool de servidores para os aplicativos confiáveis do balanceamento de carga e alta disponibilidade, ou selecione o **pool de computador único** se você não precisa carga balanceamento ou alta disponibilidade, selecione **pool de vários computadores** .
  
> [!IMPORTANT]
> Um único servidor de aplicativos confiáveis não puder ser convertido para um pool de servidores mais tarde. Se você acha que talvez seja necessário um pool no futuro, você pode implantar um pool de servidores múltiplos que contém um único computador agora e adicionar servidores quando necessário. 
  
Para obter detalhes sobre pools de aplicativos confiáveis, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

