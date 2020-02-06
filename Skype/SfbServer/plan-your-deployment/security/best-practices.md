---
title: Práticas recomendadas para a sua infraestrutura principal no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Provavelmente, você já executou etapas para projetar a tolerância a falhas em seu sistema, usando práticas como assegurar a redundância de hardware, proteger contra falta de energia, instalar rotineiramente atualizações de segurança e medidas antivírus e atividade do Monitoring Server. Essas práticas se beneficiam não apenas com a infraestrutura do Skype for Business Server, mas também para toda a sua rede. Se você não implementou essas práticas, recomendamos que faça isso antes de implantar o Skype for Business Server.
ms.openlocfilehash: 62200fc1ac45e1d647761af24d176a00d18693e4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815679"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Práticas recomendadas para a sua infraestrutura principal no Skype for Business Server
 
Provavelmente, você já executou etapas para projetar a tolerância a falhas em seu sistema, usando práticas como assegurar a redundância de hardware, proteger contra falta de energia, instalar rotineiramente atualizações de segurança e medidas antivírus e atividade do Monitoring Server. Essas práticas se beneficiam não apenas com a infraestrutura do Skype for Business Server, mas também para toda a sua rede. Se você não implementou essas práticas, recomendamos que faça isso antes de implantar o Skype for Business Server.
  
Para ajudar a proteger os servidores na implantação do Skype for Business Server contra danos acidentais ou intencionais que possam resultar em tempo de inatividade, tome as seguintes precauções:
  
- Mantenha os servidores atualizados com atualizações de segurança. A assinatura do Microsoft Security Notification Service ajuda a garantir que você receba notificações imediatas de versões de boletim de segurança de qualquer produto da Microsoft. Para se inscrever, acesse o [website de notificações técnicas de segurança da Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Verifique se os direitos de acesso estão configurados corretamente.
    
- Mantenha os servidores em um ambiente físico que impeça o acesso não autorizado. Verifique se o software antivírus adequado está instalado em todos os servidores. Mantenha o software atualizado com os arquivos de assinatura de vírus mais recentes. Use o recurso de atualização automática do seu aplicativo antivírus para manter as assinaturas de vírus atuais.
    
- Recomendamos que você desative os serviços do sistema operacional Windows Server que não são necessários nos computadores em que você instalou o Skype for Business Server.
    
- Criptografe os sistemas operacionais e as unidades de disco em que os dados estiverem armazenados com um sistema de criptografia de volume completo, a menos que você possa garantir o controle constante e completo dos servidores, o isolamento típico total e o descomissionamento apropriado e seguro de unidades de disco substituídas ou com falha.
    
- Desabilite todas as portas de DMA (Acesso Remoto Direto à Memória) externas do servido, a menos que você possa garantir o controle muito rigoroso sobre o acesso físico aos servidores. Ataques baseados em DMA, que podem ser iniciados de modo razoavelmente fácil, podem expor informações confidenciais, como chaves de criptografia privada.
    

