---
title: Expansor de Configurações de Rota de Federação
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Para definir uma atribuição de rota de federação de local, primeiro você deve habilitar a federação no Servidor de Borda ou no pool de Servidores de Borda. Se a federação não estiver habilitada no Servidor de Borda ou no pool, significa que as configurações de atribuição de rota de federação para o local não estarão disponíveis para modificação.
ms.openlocfilehash: 2cf088fbb95f6d4d7ed563313c332d5a9dd47dd4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833637"
---
# <a name="federation-route-settings-expander"></a>Expansor de Configurações de Rota de Federação
 
Para definir uma atribuição de rota de federação de local, primeiro você deve habilitar a federação no Servidor de Borda ou no pool de Servidores de Borda. Se a federação não estiver habilitada no Servidor de Borda ou no pool, significa que as configurações de atribuição de rota de federação para o local não estarão disponíveis para modificação.

Se a configuração de federação no Servidor de Borda ou pool tiver sido configurada, você poderá configurar as seguintes opções: 
  
- **Permitir atribuições de rota de federação para todos os sites** Essa configuração afetará todos os sites. Assegure-se de que a definição que você está configurando neste site é apropriada para todos os sites.
    
- **Habilitar federação SIP** Selecione essa opção para habilitar uma rota de federação SIP e selecione um diretor ou pool de Borda como a rota de federação.
    
- **Habilitar federação XMPP** Selecione essa opção para habilitar uma rota de federação XMPP e selecione um diretor ou pool de Borda como rota de federação.
- 
  > [!NOTE]
  > Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não são mais suportados no Skype for Business Server 2019. Consulte [Migrando federação XMPP](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.
    

