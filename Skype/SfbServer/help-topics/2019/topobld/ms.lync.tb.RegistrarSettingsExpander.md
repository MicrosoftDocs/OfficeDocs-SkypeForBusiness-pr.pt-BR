---
title: Expansor de Configurações do Registrador
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: A resiliência oferece alta disponibilidade e recuperação de desastres para o pool de Registradores. Ao disponibilizar um Registrador de backup em caso de falha do Registrador principal, o Registrador de backup pode assumir o lugar do Registrador com falha, permitindo que os usuários façam logon e se comuniquem. É possível que os usuários tenham uma redução na funcionalidade, dependendo dos sistemas que falharam no Registrador principal.
ms.openlocfilehash: cb7a5204b3b282c73f9440e61267b723b112b735
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822111"
---
# <a name="registrar-settings-expander"></a>Expansor de Configurações do Registrador
 
A resiliência oferece alta disponibilidade e recuperação de desastres para o pool de Registradores. Ao disponibilizar um Registrador de backup em caso de falha do Registrador principal, o Registrador de backup pode assumir o lugar do Registrador com falha, permitindo que os usuários façam logon e se comuniquem. É possível que os usuários tenham uma redução na funcionalidade, dependendo dos sistemas que falharam no Registrador principal.
  
Na seção  **Resiliência** da caixa de diálogo  **Editar Propriedades** de seu Aparelho de Filial Persistente, ou Servidor de Filial Persistente, você pode alterar as seguintes configurações:
  
- **Serviço de usuário associado e pool de registradores de backup** Na lista drop-down, selecione o pool de Front-End Enterprise Edition ou o Servidor front-end Standard Edition que deve atuar como Registrador de backup para o Aparelho de FilialVivível ou Servidor de FilialVivível.
    
- **Habilitar Failover e Failback** Selecione essa configuração para permitir a detecção automática de um Registrador com falha e a determinação automática de que o Registrador primário está pronto para continuar o processo de Registrador.
    
- **Intervalo de detecção de falha (s)** Digite o número de segundos que devem se desempesar antes que seja determinado que o Registrador primário falhou. O valor padrão é 120 segundos. Este campo é obrigatório se você selecionou **Habilitar Failover e Failback**.
    
- **Intervalo de detecção de fallback (s)** Digite o número de segundos que devem se desemparar antes que seja determinado que o backup do Registrador primário será feito. O valor padrão é 240 segundos. Este campo é obrigatório se você selecionou  **Habilitar Failover e Failback**.
    
> [!IMPORTANT]
> Quando estiver definindo os intervalos de detecção de falha e de failback, tome cuidado para não informar um intervalo que cause com que o failover e o failback ocorram se um Registrador não responder em período curto de tempo. É possível que o Registrador primário não responda por curtos períodos de tempo baseado no carregamento de pool ou servidores. 
  

