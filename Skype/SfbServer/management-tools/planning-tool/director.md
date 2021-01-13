---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Um Diretor é um servidor que executa o software de comunicações do Skype for Business Server 2015 que pode autenticar solicitações de usuário, mas não tem contas de usuário.
ms.openlocfilehash: 76315e9f63e1121119f3823187c379985c4914f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834931"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Um Diretor é um servidor que executa o software de comunicações do Skype for Business Server 2015 que pode autenticar solicitações de usuário, mas não tem contas de usuário. 
  
Essa função é opcional, você pode optar por implantar um Diretor nos dois cenários a seguir:
  
- Se você habilitar o acesso por usuários externos implantando Servidores de Borda, também deverá implantar um Diretor. Nesse cenário, o Diretor autentica os usuários externos e, em seguida, passa seu tráfego para servidores internos. Quando um Diretor é usado para autenticar usuários externos, libera os servidores do pool de Front End da sobrecarga de executar a autenticação desses usuários. Ele também ajuda a isolar pools de Front End internos de tráfego mal-intencionado, como ataques de negação de serviço. Se a rede é preenchida com tráfego externo inválido em tal ataque, este tráfego termina no Diretor.
    
- Se você implantar vários pools de Front-End em um site central, adicionando um Diretor a esse site, você poderá simplificar as solicitações de autenticação e melhorar o desempenho. Nesse cenário, todas as solicitações vão primeiro para o Diretor, que as encaminha para o pool de Front-End correto.
    

