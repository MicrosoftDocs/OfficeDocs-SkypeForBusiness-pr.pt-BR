---
title: Adicionar Servidor
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para adicionar um novo servidor a um pool existente de servidores, na qual o pool é um dos seguintes:'
ms.openlocfilehash: 5db99c8cdd2a08722a27a9da437911dcf573d5bf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220924"
---
# <a name="add-server"></a>Adicionar Servidor
 
Para adicionar um novo servidor a um pool existente de servidores, na qual o pool é um dos seguintes:
  
- Servidor de Front-End do Enterprise Edition
    
- Servidor de diretor
    
- Servidor de Mediação
    
- Servidor de conferência de áudio/vídeo
    
- Servidor de aplicativos confiáveis
    
Cada um dos novos servidores de pool tem requisitos diferentes. Nas seções a seguir, localize o tipo de servidor que você está adicionando ao pool existente e forneça as informações solicitadas como definido para cada tipo de servidor. Você fornecer as informações solicitadas para definir o novo servidor do pool.
  
 **Servidor de Front-End do Enterprise Edition**
  
- Nome domínio totalmente qualificado (FQDN) do novo servidor como definido no sistema de nome de domínio (DNS).
    
- Selecione **usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador que pode ser usado. Como alternativa, você pode selecionar **limitar o uso do serviço aos endereços IP selecionados** e digite um endereço específico no novo servidor. O endereço IP inserido é o único endereço IP qual responderá para os serviços hospedados.
    
- Defina um **endereço IP PSTN** quando um servidor de mediação é colocado no servidor Front-End.
    
- Selecione **Habilitar IPv6** para habilitar o IPv6 para esse servidor.
    
  **Servidor de diretor**
  
- O FQDN do novo servidor como definido no DNS.
    
- Selecione **usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador será usado. Como alternativa, você pode selecionar **limitar o uso do serviço aos endereços IP selecionados** e insira um endereço IP específico no novo servidor. O endereço IP inserido é o único endereço IP qual responderá para os serviços hospedados.
    
  **Servidor de mediação**
  
- O FQDN do novo servidor como definido no DNS.
    
- Selecione **usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador que pode ser usado. Como alternativa, você selecionar um endereço IP para o endereço IP (PSTN) da rede telefônica pública comutada enter e digite um endereço IP específico no novo servidor como o endereço IP principal e **limitar o uso do serviço aos endereços IP selecionados** . Os endereços IP digitados são o endereço IP único qual responderá para os serviços designados.
    
    > [!NOTE]
    > Para o servidor de mediação, o endereço IP inserido para o endereço IP principal e o endereço IP PSTN é a mesma por padrão. Os endereços IP podem ser definidos separadamente, se você estiver usando interfaces de rede dedicada ou endereços IP separados a mesma interface de rede. Se você tiver interfaces de rede dois, um para a conexão de rede local e um para a conexão de PSTN, você deve atribuir endereços IP diferentes. 
  
  **Servidor de conferência de áudio/vídeo**
  
- O FQDN do novo servidor como definido no DNS.
    
- Selecione **usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador que pode ser usado. Como alternativa, você pode selecionar **limitar o uso do serviço aos endereços IP selecionados** e digite um endereço específico no novo servidor. O endereço IP inserido é o único endereço IP qual responderá para os serviços hospedados.
    
  **Servidor de aplicativos confiáveis**
  
- O FQDN do novo servidor como definido no DNS.
    

