---
title: Ferramenta de planejamento de diretores
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Um Diretor é um servidor que executa Skype for Business Server software de comunicações 2015 que pode autenticar solicitações de usuário, mas não abriga nenhuma conta de usuário.
ms.openlocfilehash: bd2a7dfef3be16f8e2916a76c1bcb40971cdf8cc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750110"
---
# <a name="director-planning-tool"></a>Ferramenta de planejamento de diretores
 
Um Diretor é um servidor que executa Skype for Business Server software de comunicações 2015 que pode autenticar solicitações de usuário, mas não tem contas de usuário. 
  
Essa função é opcional, você optaria por implantar um Diretor nos dois cenários a seguir:
  
- Se você habilitar o acesso por usuários convidados implantando Servidores de Borda, você também deve implantar um Diretor. Nesse cenário, o Diretor autentica os convidados e, em seguida, passa o tráfego para servidores internos. Quando um Diretor é usado para autenticar convidados, ele alivia os servidores de pool front-end da sobrecarga de autenticação desses usuários. Ele também ajuda a isolar pools front-end internos de tráfego mal-intencionado, como ataques de negação de serviço. Se a rede é preenchida com tráfego externo inválido em tal ataque, este tráfego termina no Diretor.
    
- Se você implantar vários pools de Front-End em um site central, adicionando um Diretor a esse site, você pode simplificar as solicitações de autenticação e melhorar o desempenho. Nesse cenário, todas as solicitações vão primeiro para o Diretor, que as encaminha para o pool de Front-End correto.
    

