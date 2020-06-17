---
title: Migrar a federação XMPP
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
description: 'As versões anteriores forneciam um Gateway XMPP (Extensible Messaging and Presence Protocol) que poderia ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP. A funcionalidade do XMPP não está mais disponível & preterida no Skype for Business Server 2019. Se você deseja continuar com a funcionalidade do XMPP, que pode ser avaliada no ambiente do coexitence com a versão legada (Skype for Business Server 2015/Lync Server 2013). A funcionalidade do XMPP está instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda herdado e o gateway do XMPP que é executado no servidor de front-end herdado.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752643"
---
# <a name="migrating-xmpp-federation"></a>Migrar a federação XMPP

As versões anteriores forneciam um Gateway XMPP (Extensible Messaging and Presence Protocol) que poderia ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP. A funcionalidade do XMPP não está mais disponível e foi preterida no Skype for Business Server 2019. Se quiser continuar com a funcionalidade do XMPP, você pode fazer isso em um ambiente de coexistência com uma versão herdada (Skype for Business Server 2015 ou Lync Server 2013). A funcionalidade do XMPP está instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda herdado e o gateway do XMPP que é executado no servidor de front-end herdado. 
  
De uma perspectiva de migração, os usuários que desejam passar o recurso XMPP devem permanecer no servidor herdado e não devem ser movidos para um pool do Skype for Business Server 2019, mas continuar a usar o Gateway XMPP herdado. Isso só é possível quando o parceiro federado do XMPP está configurado no Skype for Business Server 2015 ou no Lync Server 2013. Você não deve migrar o servidor de borda herdado para o Skype for Business Server 2019 se quiser continuar com a funcionalidade do XMPP. No entanto, você pode ter coexistência do servidor de borda herdado (com o proxy do XMPP) e do servidor de borda do Skype for Business 2019.
  

    

