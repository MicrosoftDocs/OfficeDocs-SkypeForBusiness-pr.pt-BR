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
ms.localizationpriority: medium
description: 'As versões anteriores forneceam um gateway XMPP (protocolo XMPP) extensível que poderia ser implantado como uma função de servidor separada para permitir a federação com implantações XMPP. A funcionalidade XMPP não está mais disponível & preterida no Skype for Business Server 2019. Se você quiser continuar com a funcionalidade XMPP, isso pode ser aproveitado em ambiente de coexitência com a versão herdada (Skype for Business Server 2015/ Lync Server 2013). A funcionalidade XMPP é instalada em duas partes: como um proxy XMPP executado no Servidor de Borda herdado e o Gateway XMPP que é executado no Servidor Front-End herdado.'
ms.openlocfilehash: a0c3eeaa6218c6e3b3726f755adcca6083a9ac3f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580125"
---
# <a name="migrating-xmpp-federation"></a>Migrar a federação XMPP

As versões anteriores forneceam um gateway XMPP (protocolo XMPP) extensível que poderia ser implantado como uma função de servidor separada para permitir a federação com implantações XMPP. A funcionalidade XMPP não está mais disponível e é preterida no Skype for Business Server 2019. Se você quiser continuar com a funcionalidade XMPP, poderá fazer isso em um ambiente de coexistência com uma versão herdada (Skype for Business Server 2015 ou Lync Server 2013). A funcionalidade XMPP é instalada em duas partes: como um proxy XMPP executado no Servidor de Borda herdado e o Gateway XMPP que é executado no Servidor Front-End herdado. 
  
Sob uma perspectiva de migração, os usuários que querem aproveitar o recurso XMPP devem permanecer no servidor herdável e não devem ser movidos para um pool do Skype for Business Server 2019, mas continuar a usar o gateway XMPP herdável. Isso só é possível quando o parceiro federado XMPP é configurado no Skype for Business Server 2015 ou no Lync Server 2013. Você não deve migrar o Servidor de Borda herdado para Skype for Business Server 2019 se quiser continuar com a funcionalidade XMPP. No entanto, você pode ter coexistência do Servidor de Borda herdado (com Proxy XMPP) e o servidor de borda Skype for Business 2019.
  

    

