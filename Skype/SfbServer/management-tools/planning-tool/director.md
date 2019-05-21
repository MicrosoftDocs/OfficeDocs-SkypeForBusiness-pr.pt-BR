---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Um diretor é um servidor que executa o software de comunicações do Skype for Business Server 2015, que pode autenticar solicitações de usuário, mas não hospeda nenhuma conta de usuário.
ms.openlocfilehash: a551e2568b814f1811ebc84a8d187c8554cc1542
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274258"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Um diretor é um servidor que executa o software de comunicações do Skype for Business Server 2015, que pode autenticar solicitações de usuário, mas não hospeda nenhuma conta de usuário. 
  
Esta função é opcional, você optaria por implantar um diretor nos dois cenários a seguir:
  
- Se você habilitar o acesso por usuários externos implantando servidores de borda, também deverá implantar um diretor. Nesse cenário, o diretor autentica os usuários externos e, em seguida, passa o tráfego deles para servidores internos. Quando um diretor é usado para autenticar usuários externos, ele libera os servidores de pool de front-end da sobrecarga de execução de autenticação desses usuários. Também ajuda a proteger pools de front-end internos contra tráfego mal-intencionado, como ataques de negação de serviço. Se a rede estiver inundada com tráfego externo inválido nesse tipo de ataque, esse tráfego terminará no diretor.
    
- Se você implantar vários pools de front-end em um site central, adicionando um diretor ao site, você pode simplificar solicitações de autenticação e melhorar o desempenho. Nesse cenário, todas as solicitações entram primeiro no director, que, em seguida, as roteia para o pool de front-end correto.
    

