---
title: Diretor (Ferramenta de Planejamento)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Um Diretor é um servidor que executa Skype for Business Server software de comunicações que pode autenticar solicitações de usuário, mas não abriga nenhuma conta de usuário.
ms.openlocfilehash: 6ab7231aabdfead417b61324cfffa2bc8cc621999515da8964be749f3c1f5574
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294698"
---
# <a name="director-planning-tool"></a>Diretor (Ferramenta de Planejamento)
 
Um Diretor é um servidor que executa Skype for Business Server software de comunicações que pode autenticar solicitações de usuário, mas não abriga nenhuma conta de usuário. 
  
Essa função é opcional, você optaria por implantar um Diretor nos dois cenários a seguir:
  
- Se você habilitar o acesso por usuários externos implantando Servidores de Borda, também deverá implantar um Diretor. Nesse cenário, o Diretor autentica os usuários externos e, em seguida, passa o tráfego para servidores internos. Quando um Diretor é usado para autenticar usuários externos, ele alivia os servidores de pool front-end da sobrecarga de execução da autenticação desses usuários. Ele também ajuda a isolar pools front-end internos de tráfego mal-intencionado, como ataques de negação de serviço. Se a rede é preenchida com tráfego externo inválido em tal ataque, este tráfego termina no Diretor.
    
- Se você implantar vários pools de Front-End em um site central, adicionando um Diretor a esse site, você pode simplificar as solicitações de autenticação e melhorar o desempenho. Nesse cenário, todas as solicitações vão primeiro para o Diretor, que as encaminha para o pool de Front-End correto.
    

