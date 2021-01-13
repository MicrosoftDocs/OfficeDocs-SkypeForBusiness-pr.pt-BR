---
title: Práticas recomendadas para sua infraestrutura principal no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Provavelmente, você já executou etapas para designar a tolerância a falha em seu sistema, usando práticas como a garantia da redundância de hardware, proteção contra perda de energia, instalação rotineira de atualizações de segurança e medidas antivírus, e atividade do Monitoring Server. Essas práticas beneficiam não apenas a infraestrutura do Skype for Business Server, mas também toda a rede. Se você não implementou essas práticas, recomendamos que o faça antes de implantar o Skype for Business Server.
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832241"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Práticas recomendadas para sua infraestrutura principal no Skype for Business Server
 
Provavelmente, você já executou etapas para designar a tolerância a falha em seu sistema, usando práticas como a garantia da redundância de hardware, proteção contra perda de energia, instalação rotineira de atualizações de segurança e medidas antivírus, e atividade do Monitoring Server. Essas práticas beneficiam não apenas a infraestrutura do Skype for Business Server, mas também toda a rede. Se você não implementou essas práticas, recomendamos que o faça antes de implantar o Skype for Business Server.
  
Para ajudar a proteger os servidores em sua implantação do Skype for Business Server contra danos acidentais ou proposital que possam resultar em tempo de inatividade, tome as seguintes precauções:
  
- Mantenha em dia as atualizações de segurança nos servidores. Inscreva-se no serviço Microsoft Security Notification Service para receber uma notificação imediata do lançamento de boletins de segurança referentes a qualquer produto da Microsoft. Para se inscrever, acesse o site de Notificações de Segurança Técnica [da Microsoft.](https://go.microsoft.com/fwlink/p/?LinkId=145202)
    
- Certifique-se de que os direitos de acesso estão configurados corretamente.
    
- Mantenha os servidores em um ambiente físico que evite o acesso não autorizado. Verifique se um software antivírus adequado está instalado em todos os servidores. Mantenha o software atualizado com os arquivos de assinatura de vírus mais recentes. Use o recurso de atualização automática do aplicativo antivírus para deixar essas assinaturas sempre em dia.
    
- Recomendamos que você desabilite os serviços do sistema operacional Windows Server que não são necessários nos computadores em que você instala o Skype for Business Server.
    
- Criptografe os sistemas operacionais e as unidades de disco nos quais os dados são armazenados com um sistema de criptografia de volume completo, a menos que você possa garantir um controle constante e completo dos servidores, isolamento físico total e descomissionamento apropriado e seguro de unidades de disco substituídas ou com falha.
    
- Desabilite todas as portas DMA (Acesso direto à memória) externas do servidor, a menos que você possa garantir um controle muito rígido sobre o acesso físico aos servidores. Os ataques baseados em DMA, que podem ser iniciados com bastante facilidade, podem expor informações muito confidenciais, como chaves de criptografia privadas.
    

