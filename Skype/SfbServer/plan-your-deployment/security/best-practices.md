---
title: Práticas recomendadas para a infraestrutura principal no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Provavelmente, você já executou etapas para projetar a tolerância a falhas em seu sistema, usando práticas como assegurar a redundância de hardware, proteger contra falta de energia, instalar rotineiramente atualizações de segurança e medidas antivírus e atividade do Monitoring Server. Essas práticas beneficiam não apenas sua Skype infra-estrutura de servidor de negócios, mas também toda a sua rede. Se você não implementou essas práticas, recomendamos que você faça isso antes de implantar o Skype para Business Server.
ms.openlocfilehash: 86d18e1d9d34b5f65f4cb938e13a9829af1646bb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213624"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Práticas recomendadas para a infraestrutura principal no Skype para Business Server
 
Provavelmente, você já executou etapas para projetar a tolerância a falhas em seu sistema, usando práticas como assegurar a redundância de hardware, proteger contra falta de energia, instalar rotineiramente atualizações de segurança e medidas antivírus e atividade do Monitoring Server. Essas práticas beneficiam não apenas sua Skype infra-estrutura de servidor de negócios, mas também toda a sua rede. Se você não implementou essas práticas, recomendamos que você faça isso antes de implantar o Skype para Business Server.
  
Para ajudar a proteger os servidores no seu Skype para implantação de servidor de negócios contra danos acidentais ou intencionais que possam resultar na inatividade do sistema, tome as seguintes precauções:
  
- Mantenha os servidores atualizados com atualizações de segurança. A assinatura do Microsoft Security Notification Service ajuda a garantir que você receba notificações imediatas de versões de boletim de segurança de qualquer produto da Microsoft. Para assinar, visite o [site de notificações de segurança técnica da Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Verifique se os direitos de acesso estão configurados corretamente.
    
- Mantenha os servidores em um ambiente físico que impeça o acesso não autorizado. Verifique se o software antivírus adequado está instalado em todos os servidores. Mantenha o software atualizado com os arquivos de assinatura de vírus mais recentes. Use o recurso de atualização automática do seu aplicativo antivírus para manter as assinaturas de vírus atuais.
    
- Recomendamos que você desabilite os serviços do sistema operacional Windows Server que não forem necessários nos computadores onde você instala o Skype para Business Server.
    
- Criptografe os sistemas operacionais e as unidades de disco em que os dados estiverem armazenados com um sistema de criptografia de volume completo, a menos que você possa garantir o controle constante e completo dos servidores, o isolamento típico total e o descomissionamento apropriado e seguro de unidades de disco substituídas ou com falha.
    
- Desabilite todas as portas de DMA (Acesso Remoto Direto à Memória) externas do servido, a menos que você possa garantir o controle muito rigoroso sobre o acesso físico aos servidores. Ataques baseados em DMA, que podem ser iniciados de modo razoavelmente fácil, podem expor informações confidenciais, como chaves de criptografia privada.
    

