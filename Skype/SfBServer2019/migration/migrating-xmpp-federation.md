---
title: Migração da federação XMPP
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Versões anteriores forneciam um gateway de protocolo XMPP extensível para mensagens e presença que poderia ser implantado como uma função de servidor separadas para permitir a federação com implantações de XMPP. A funcionalidade XMPP não está mais disponível & preteridos no Skype para Business Server 2019. Se você deseja continuar com a funcionalidade XMPP, que pode ser avaliado no ambiente coexitence com a versão herdada (Skype para Business Server 2015 / Lync Server 2013). Funcionalidade XMPP está instalada em duas partes: como um XMPP proxy que é executado no antigo servidor de borda e o Gateway XMPP que é executado no servidor Front-End herdado.'
ms.openlocfilehash: d8db32bd823e4a0c15fa373f89ee930d2cd8d98c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029864"
---
# <a name="migrating-xmpp-federation"></a>Migração da federação XMPP

Versões anteriores forneciam um gateway de protocolo XMPP extensível para mensagens e presença que poderia ser implantado como uma função de servidor separadas para permitir a federação com implantações de XMPP. A funcionalidade XMPP não está mais disponível e foi preterida no Skype para Business Server 2019. Se você deseja continuar com a funcionalidade XMPP, você pode fazer isso em um ambiente de coexistência com uma versão herdada (Skype para Business Server 2015 ou o Lync Server 2013). Funcionalidade XMPP está instalada em duas partes: como um XMPP proxy que é executado no antigo servidor de borda e o Gateway XMPP que é executado no servidor Front-End herdado. 
  
De uma perspectiva de migração, os usuários que desejam avaliar o recurso XMPP devem permanecer em servidor herdado e não devem ser movidos para um Skype para Business Server 2019 pool, mas continuam a usar o gateway XMPP herdado. Isso é possível somente quando o parceiro federado XMPP está configurado no Skype para Business Server 2015 ou o Lync Server 2013. Você não deve migrar o servidor de borda herdado para Skype para Business Server 2019 se você deseja continuar com a funcionalidade XMPP. No entanto, você pode ter coexistência do servidor de borda herdado (com o Proxy XMPP) e o Skype para servidor de borda de 2019 de negócios.
  

    

