---
title: Adicionar Servidor
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para adicionar um novo servidor a um pool de servidores existente, no qual o pool é um dos seguintes:'
ms.openlocfilehash: 12a8e65f85120bea9d6e9a466bbca4f7d1d070b6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857798"
---
# <a name="add-server"></a>Adicionar Servidor
 
Para adicionar um novo servidor a um pool de servidores existente, no qual o pool é um dos seguintes:
  
- Servidor Front-Ends Enterprise Edition
    
- Servidor de Diretor
    
- Servidor de Mediação
    
- Servidor de Conferência de Áudio/Vídeo
    
- Servidor de Aplicativo Confiável
    
Cada um dos novos servidores de pool possuem requisitos diferentes. Localize, nas seções a seguir, o tipo de servidor que você está adicionando ao pool existente e forneça a informação exigida, conforme definido para cada tipo de servidor. Você providencia a informação exigida para definir o novo servidor de pool.
  
 **Servidor de Front-Ends Enterprise Edition**
  
- FQDN (nome de domínio totalmente qualificado) do novo servidor como definido no DNS (Domain Name System).
    
- Selecione **Usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador pode ser usado. Alternativamente, você pode selecionar **Limitar utilização de serviço aos endereços IP selecionados** e inserir um endereço específico no novo servidor. O endereço IP inserido é o único endereço IP que responderá aos serviços hospedados.
    
- Definir um  **Endereço IP PSTN** quando um Servidor de Mediação é colocado no Servidor Front-Ends.
    
- Select **Enable IPv6** to enable IPv6 for this server.
    
  **Servidor de Diretor**
  
- O FQDN do novo servidor como definido no DNS.
    
- Selecione  **Usar todos os endereços de IP configurados**,  que significa que qualquer endereço IP definido no computador será usado.  Alternativamente, você pode selecionar  **Limitar utilização de serviço aos endereços IP selecionados** e inserir um endereço IP específico no novo servidor. O endereço IP inserido é o único endereço IP que responderá aos serviços hospedados.
    
  **Servidor de Mediação**
  
- O FQDN do novo servidor como definido no DNS.
    
- Selecione **Usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador pode ser usado.  Alternativamente, você pode selecionar **Limitar utilização de serviço aos endereços IP selecionados** e inserir um endereço IP específico no novo servidor como o endereço IP Primário, inserindo então um endereço IP para o endereço IP PSTN (rede telefônica pública comutada). O endereço IP inserido é o único endereço IP que responderá aos serviços hospedados.
    
    > [!NOTE]
    > Para o Servidor de Mediação, o endereço IP inserido para o endereço IP Primário e o endereço IP PSTN são os mesmos, por padrão. Os endereços IP podem ser definidos separadamente caso você esteja usando interfaces de rede dedicadas ou endereços IP separados na mesma interface de rede. Caso você tenha duas interfaces de rede, uma para a conexão de rede local e outra para a conexão PSTN, você deve atribuir endereços IP diferentes. 
  
  **Servidor de Conferência de Áudio/Vídeo**
  
- O FQDN do novo servidor como definido no DNS.
    
- Selecione  **Usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador pode ser usado. Alternativamente, você pode selecionar  **Limitar utilização de serviço aos endereços IP selecionados** e inserir um endereço específico no novo servidor. O endereço IP inserido é o único endereço IP que responderá aos serviços hospedados.
    
  **Servidor de Aplicativos Confiáveis**
  
- O FQDN do novo servidor como definido no DNS.
    

