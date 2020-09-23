---
title: Expansor de Configurações do Registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: A resiliência oferece alta disponibilidade e recuperação de desastres para o pool de Registradores. Ao disponibilizar um Registrador de backup em caso de falha do Registrador principal, o Registrador de backup pode assumir o lugar do Registrador com falha, permitindo que os usuários façam logon e se comuniquem. É possível que os usuários tenham uma redução na funcionalidade, dependendo dos sistemas que falharam no Registrador principal.
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217152"
---
# <a name="registrar-settings-expander"></a>Expansor de Configurações do Registrador
 
A resiliência oferece alta disponibilidade e recuperação de desastres para o pool de Registradores. Ao disponibilizar um Registrador de backup em caso de falha do Registrador principal, o Registrador de backup pode assumir o lugar do Registrador com falha, permitindo que os usuários façam logon e se comuniquem. É possível que os usuários tenham uma redução na funcionalidade, dependendo dos sistemas que falharam no Registrador principal.
  
Na seção  **Resiliência ** da caixa de diálogo  **Editar Propriedades ** de seu Aparelho de Filial Persistente, ou Servidor de Filial Persistente, você pode alterar as seguintes configurações:
  
- **Serviço de usuário associado e pool de registradores de backup** Na lista suspensa, selecione o pool de front-ends Enterprise Edition ou o servidor front-end Standard Edition que deve atuar como registrador de backup para o aparelho de filial persistente ou servidor de filial persistente.
    
- **Habilitar failover e failback** Selecione essa configuração para permitir a detecção automática de um registrador com falha e a determinação automática de que o registrador primário está em backup e pronto para retomar o processo registrador.
    
- **Intervalo de detecção de falhas (s)** Digite o número de segundos que devem decorrer antes de determinar que o registrador principal falhou. O valor padrão é 120 segundos. Este campo é obrigatório se você selecionou **Habilitar Failover e Failback **.
    
- **Intervalo de detecção de fallback (s)** Digite o número de segundos que devem decorrer antes de determinar que o registrador principal é armazenado em backup. O valor padrão é 240 segundos. Este campo é obrigatório se você selecionou  **Habilitar Failover e Failback **.
    
> [!IMPORTANT]
> Quando estiver definindo os intervalos de detecção de falha e de failback, tome cuidado para não informar um intervalo que cause com que o failover e o failback ocorram se um Registrador não responder em período curto de tempo. É possível que o Registrador primário não responda por curtos períodos de tempo baseado no carregamento de pool ou servidores. 
  

