---
title: Expansor de configurações do Registrador Avançado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: Resiliência fornece alta disponibilidade e recuperação de desastres para o pool do registrador. Ao fornecer um registrador de backup em caso de falha do registrador principal, o registrador de backup pode assumir o registro com falha, permitindo que os usuários façam logon e se comuniquem. Os usuários podem experimentar recursos reduzidos, dependendo de quais sistemas falharam com o registrador principal.
ms.openlocfilehash: 122124140c93afb3ce58b1d9423839f3e21dbcad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277836"
---
# <a name="registrar-settings-expander"></a>Expansor de configurações do Registrador Avançado
 
Resiliência fornece alta disponibilidade e recuperação de desastres para o pool do registrador. Ao fornecer um registrador de backup em caso de falha do registrador principal, o registrador de backup pode assumir o registro com falha, permitindo que os usuários façam logon e se comuniquem. Os usuários podem experimentar recursos reduzidos, dependendo de quais sistemas falharam com o registrador principal.
  
Na seção **resiliência** da caixa de diálogo **Editar propriedades** de seu aparelho de ramificação e servidor de ramificação sobreviventes, você pode alterar as seguintes configurações:
  
- **Serviço de usuário associado e pool de registradores de backup** Na lista suspensa, selecione o pool de front-end do Enterprise Edition ou o servidor front-end Standard Edition que é para atuar como registrador de backup para o aparelho de ramificação sobreviventes ou para o servidor de ramificação sobreviventes.
    
- **Habilitar failover e failback** Selecione essa configuração para permitir a detecção automática de um registrador de falha e a determinação automática de que o registrador principal está em andamento e pronto para continuar o processo registrador.
    
- **Intervalo de detecção de falha (s)** Digite o número de segundos que devem decorrer antes que seja determinado que o registrador primário falhou. O valor padrão é 120 segundos. Este campo é obrigatório se você selecionar **habilitar failover e failback**.
    
- **Intervalo de detecção de fallback (s)** Digite o número de segundos que devem decorrer antes de determinar que o registrador primário está em backup. O valor padrão é 240 segundos. Este campo é obrigatório se você selecionar **habilitar failover e fallback**.
    
> [!IMPORTANT]
> Quando você define o intervalo de detecção de falha e o intervalo de detecção de fallback, tome cuidado para não inserir um intervalo que causará o failover e o fallback para ocorrer se o registrador não responder por um curto período de tempo. É possível que o registrador principal possa não responder por períodos curtos de tempo com base no carregamento do pool ou dos servidores. 
  

