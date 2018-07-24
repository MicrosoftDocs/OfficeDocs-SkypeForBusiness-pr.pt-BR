---
title: Diretor (ferramenta de planejamento)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Um diretor é um servidor que executa o Skype Business Server software de comunicações que pode autenticar solicitações de usuário, mas não hospeda nenhuma conta de usuário.
ms.openlocfilehash: e6210c6c4c6b4f92b99eb9287f82e6268db5df12
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21058269"
---
# <a name="director-planning-tool"></a>Diretor (ferramenta de planejamento)
 
Um diretor é um servidor que executa o Skype Business Server software de comunicações que pode autenticar solicitações de usuário, mas não hospeda nenhuma conta de usuário. 
  
Essa função é opcional, que você escolheria implantar um diretor em dois cenários a seguir:
  
- Se você habilitar o acesso por usuários externos implantando servidores de borda, você também deve implantar um diretor. Neste cenário, o Diretor autentica os usuários externos e, em seguida, passa o tráfego para os servidores internos. Quando um diretor é usado para autenticar usuários externos, ele libera os servidores de pool de Front-End da sobrecarga de realizar a autenticação desses usuários. Isso também ajuda a isolar os pools de Front-End internos contra tráfego malicioso, como ataques de negação de serviço. Se a rede é inundada com o tráfego externo inválido nesse ataque, esse tráfego termina no diretor.
    
- Se você implantar vários pools de Front-End em um site central, adicionando um diretor para esse site pode simplificar a solicitações de autenticação e melhorar o desempenho. Neste cenário, todas as solicitações vão primeira para o diretor, que, em seguida, encaminha-los para o pool de Front-End correto.
    

