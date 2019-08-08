---
title: Migrar a federação XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'As versões anteriores forneciam um gateway de protocolo de presença e mensagens extensível (XMPP) que poderia ser implantado como uma função de servidor separada para permitir a Federação em implantações do XMPP. A funcionalidade XMPP não está mais disponível & preterida no Skype for Business Server 2019. Se você quiser continuar com a funcionalidade do XMPP, isso pode ser avaliado em ambiente coexitence com versão herdada (Skype for Business Server 2015/Lync Server 2013). A funcionalidade XMPP é instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda herdado e o Gateway XMPP executado no servidor front-end herdado.'
ms.openlocfilehash: 0c7c3dbb9c7cda4f6825f66326422dced85a9c3c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237790"
---
# <a name="migrating-xmpp-federation"></a>Migrar a federação XMPP

As versões anteriores forneciam um gateway de protocolo de presença e mensagens extensível (XMPP) que poderia ser implantado como uma função de servidor separada para permitir a Federação em implantações do XMPP. A funcionalidade XMPP não está mais disponível e foi preterida no Skype for Business Server 2019. Se quiser continuar com a funcionalidade do XMPP, você pode fazer isso em um ambiente de coexistência com uma versão herdada (Skype for Business Server 2015 ou Lync Server 2013). A funcionalidade XMPP é instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda herdado e o Gateway XMPP executado no servidor front-end herdado. 
  
De uma perspectiva de migração, os usuários que desejam avaliar o recurso XMPP devem permanecer no servidor herdado e não devem ser movidos para um pool do Skype for Business Server 2019, mas continuar a usar o gateway herdado do XMPP. Isso só é possível quando o parceiro federado do XMPP está configurado no Skype for Business Server 2015 ou no Lync Server 2013. Você não deve migrar o servidor de borda herdado para o Skype for Business Server 2019 se quiser continuar a funcionalidade do XMPP. No entanto, você pode ter coexistência do servidor de borda herdado (com proxy XMPP) e do servidor de borda do Skype for Business 2019.
  

    

