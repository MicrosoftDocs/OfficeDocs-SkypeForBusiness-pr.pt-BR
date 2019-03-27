---
title: Expansor de configurações do Registrador Avançado
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: Resiliência oferece alta disponibilidade e recuperação de desastres para o pool de registrador. Fornecendo um registrador de backup em caso de falha do registrador principal, o backup registrador possa assumir o controle para o registro com falha, permitindo que os usuários se conectem e se comunicar. Os usuários podem potencialmente experimentar funcionalidade reduzida, dependendo de qual sistemas falharam com o registrador principal.
ms.openlocfilehash: dff7561a1e461283768601515a52207de1b4140b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893080"
---
# <a name="registrar-settings-expander"></a>Expansor de configurações do Registrador Avançado
 
Resiliência oferece alta disponibilidade e recuperação de desastres para o pool de registrador. Fornecendo um registrador de backup em caso de falha do registrador principal, o backup registrador possa assumir o controle para o registro com falha, permitindo que os usuários se conectem e se comunicar. Os usuários podem potencialmente experimentar funcionalidade reduzida, dependendo de qual sistemas falharam com o registrador principal.
  
Na seção **resiliência** da caixa de diálogo **Editar propriedades** para o aparelho de filial persistente ou servidor de filial persistente, você pode alterar as configurações a seguir:
  
- **Serviço de usuário associados e o pool de registradores de backup** Na lista suspensa, selecione o pool de Front End do Enterprise Edition ou Standard Edition servidor Front-End que deve agir como o registrador de backup para o aparelho de filial persistente ou servidor de filial persistente.
    
- **Habilitar o Failover e Failback** Selecione esta configuração para permitir a detecção automática de uma falha registrador e a determinação automática que o registro primário estiver fazer backup e pronto para continuar o processo de registrador.
    
- **Intervalo de detecção de falha (s)** Digite o número de segundos que deverão decorrer antes de ser determinado que a principal registrador falhou. O valor padrão é de 120 segundos. Este campo é obrigatório se você selecionar **Habilitar o Failover e Failback**.
    
- **Intervalo de detecção de fallback (s)** Digite o número de segundos que deverão decorrer antes que o registrador principal é feito o backup for determinado. O valor padrão é 240 segundos. Este campo é obrigatório se você selecionar **Habilitar o Failover e failback**.
    
> [!IMPORTANT]
> Quando você definir o intervalo de detecção de falha e o intervalo de detecção de fallback, ser cuidado para não inserir um intervalo que fará com que o failover e failback para ocorrer se o registrador não responder por um curto período de tempo. É possível que o registrador principal pode não responder por curtos períodos de tempo baseado no carregamento do pool ou servidores. 
  

