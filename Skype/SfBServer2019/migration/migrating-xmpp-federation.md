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
description: 'As versões anteriores proporcionam um gateway XMPP (extensible messaging and presence protocol) que poderia ser implantado como uma função de servidor separada para permitir a federação com implantações XMPP. A funcionalidade XMPP não está mais disponível & foi preterida no Skype for Business Server 2019. Se você quiser continuar com a funcionalidade XMPP, isso pode ser uma ferramenta no ambiente de coexitência com a versão herdada (Skype for Business Server 2015/ Lync Server 2013). A funcionalidade XMPP é instalada em duas partes: como um proxy XMPP executado no Servidor de Borda herdado e o Gateway XMPP que é executado no Servidor Front End herdado.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752643"
---
# <a name="migrating-xmpp-federation"></a>Migrar a federação XMPP

As versões anteriores proporcionam um gateway XMPP (extensible messaging and presence protocol) que poderia ser implantado como uma função de servidor separada para permitir a federação com implantações XMPP. A funcionalidade XMPP não está mais disponível e foi preterida no Skype for Business Server 2019. Se você quiser continuar com a funcionalidade XMPP, poderá fazer isso em um ambiente de coexistência com uma versão herdada (Skype for Business Server 2015 ou Lync Server 2013). A funcionalidade XMPP é instalada em duas partes: como um proxy XMPP executado no Servidor de Borda herdado e o Gateway XMPP que é executado no Servidor Front End herdado. 
  
A partir de uma perspectiva de migração, os usuários que querem utilizar o recurso XMPP devem permanecer no servidor herdada e não devem ser movidos para um pool do Skype for Business Server 2019, mas continuar a usar o gateway XMPP herdada. Isso só é possível quando o parceiro federado XMPP está configurado no Skype for Business Server 2015 ou no Lync Server 2013. Você não deve migrar o Servidor de Borda herdado para o Skype for Business Server 2019 se quiser continuar com a funcionalidade XMPP. No entanto, você pode ter coexistência do Servidor de Borda herdada (com Proxy XMPP) e do Servidor de Borda do Skype for Business 2019.
  

    

