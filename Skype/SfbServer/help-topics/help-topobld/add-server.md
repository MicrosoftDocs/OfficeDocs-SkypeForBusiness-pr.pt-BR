---
title: Adicionar Servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para adicionar um novo servidor a um pool de servidores existente, onde o pool é um dos seguintes:'
ms.openlocfilehash: c19aad7f55c6ebc22ee64c715700d8cc7116bccb
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698036"
---
# <a name="add-server"></a>Adicionar Servidor
 
Para adicionar um novo servidor a um pool de servidores existente, onde o pool é um dos seguintes:
  
- Servidor front-end do Enterprise Edition
    
- Servidor diretor
    
- Servidor de Mediação
    
- Servidor de conferência de áudio/vídeo
    
- Servidor de aplicativos confiável
    
Cada um dos novos servidores de pool tem requisitos diferentes. Nas seções a seguir, localize o tipo de servidor que você está adicionando ao pool existente e forneça as informações solicitadas conforme elas são definidas para cada tipo de servidor. Forneça as informações solicitadas para definir o novo servidor de pool.
  
 **Servidor front-end do Enterprise Edition**
  
- FQDN (nome de domínio totalmente qualificado) do novo servidor conforme definido no DNS (sistema de nomes de domínio).
    
- Selecione **usar todos os endereços IP configurados**, o que significa que qualquer endereço IP definido no computador poderá ser usado. Você também pode selecionar limitar o **uso do serviço a endereços IP selecionados** e inserir um endereço específico no novo servidor. O endereço IP inserido é o único endereço IP que irá responder aos serviços hospedados.
    
- Defina um **endereço IP PSTN** quando um servidor de mediação estiver posicionado no servidor front-end.
    
- Selecione **habilitar IPv6** para habilitar o IPv6 para este servidor.
    
  **Servidor diretor**
  
- O FQDN do novo servidor como ele está definido no DNS.
    
- Selecione **usar todos os endereços IP configurados**, o que significa que qualquer endereço IP definido no computador será usado. Ou, se preferir, selecione **limitar o uso do serviço para endereços IP selecionados** e insira um endereço IP específico no novo servidor. O endereço IP inserido é o único endereço IP que irá responder aos serviços hospedados.
    
  **Servidor de mediação**
  
- O FQDN do novo servidor como ele está definido no DNS.
    
- Selecione **usar todos os endereços IP configurados**, o que significa que qualquer endereço IP definido no computador poderá ser usado. Ou, se preferir, selecione **limitar o uso do serviço para endereços IP selecionados** e insira um endereço IP específico no novo servidor como o endereço IP principal e insira um endereço IP para o endereço IP da rede telefônica comutada pública (PSTN). Os endereços IP inseridos são o único endereço IP que responderá aos serviços designados.
    
    > [!NOTE]
    > Para o servidor de mediação, o endereço IP inserido para o endereço IP primário e o endereço IP PSTN é o mesmo por padrão. Os endereços IP podem ser definidos separadamente se você estiver usando interfaces de rede dedicadas ou endereços IP separados na mesma interface de rede. Se você tiver duas interfaces de rede, uma para a conexão de rede local e outra para a conexão PSTN, será preciso atribuir endereços IP diferentes. 
  
  **Servidor de conferência de áudio/vídeo**
  
- O FQDN do novo servidor como ele está definido no DNS.
    
- Selecione **usar todos os endereços IP configurados**, o que significa que qualquer endereço IP definido no computador poderá ser usado. Você também pode selecionar limitar o **uso do serviço a endereços IP selecionados** e inserir um endereço específico no novo servidor. O endereço IP inserido é o único endereço IP que irá responder aos serviços hospedados.
    
  **Servidor de aplicativos confiável**
  
- O FQDN do novo servidor como ele está definido no DNS.
    

