---
title: Expansor de Configurações do Registrador
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 75184413222c2de6d580b1ae088b4d65bc7e9851fd10aaaba6b303daa1a53e5e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329635"
---
# <a name="registrar-settings-expander"></a>Expansor de Configurações do Registrador
 
A resiliência oferece alta disponibilidade e recuperação de desastres para o pool de Registradores. Ao disponibilizar um Registrador de backup em caso de falha do Registrador principal, o Registrador de backup pode assumir o lugar do Registrador com falha, permitindo que os usuários façam logon e se comuniquem. É possível que os usuários tenham uma redução na funcionalidade, dependendo dos sistemas que falharam no Registrador principal.
  
Na seção  **Resiliência** da caixa de diálogo  **Editar Propriedades** de seu Aparelho de Filial Persistente, ou Servidor de Filial Persistente, você pode alterar as seguintes configurações:
  
- **Pool de** Registradores de backup e serviço de usuário associado Na listada, selecione o pool de front-end Edição Enterprise ou Edição Standard servidor front-end que deve atuar como o Registrador de backup para o Aparelho de Filial Desavivável ou Servidor de Filial Desavivável.
    
- **Habilitar Failover e Failback** Selecione essa configuração para permitir a detecção automática de um Registrador com falha e a determinação automática de que o Registrador principal está de volta e pronto para retomar o processo de Registrador.
    
- **Intervalo de detecção de falha (s)** Digite o número de segundos que devem ser definidos antes de determinar que o Registrador primário falhou. O valor padrão é 120 segundos. Este campo é obrigatório se você selecionou **Habilitar Failover e Failback**.
    
- **Intervalo de detecção de fallback (s)** Digite o número de segundos que devem ser definidos antes de determinar que o Registrador principal está com backup. O valor padrão é 240 segundos. Este campo é obrigatório se você selecionou  **Habilitar Failover e Failback**.
    
> [!IMPORTANT]
> Quando estiver definindo os intervalos de detecção de falha e de failback, tome cuidado para não informar um intervalo que cause com que o failover e o failback ocorram se um Registrador não responder em período curto de tempo. É possível que o Registrador primário não responda por curtos períodos de tempo baseado no carregamento de pool ou servidores. 
  

