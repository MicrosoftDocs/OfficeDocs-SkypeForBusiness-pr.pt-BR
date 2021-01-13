---
title: Definir a experiência do usuário para aquisição manual de um local no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planejamento para usuários em roaming em uma implantação E9-1-1 usando provedores de tronco SIP, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: dd43d78b4c139b4fb30a0b4ba379d96150314332
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825421"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definir a experiência do usuário para aquisição manual de um local no Skype for Business Server
 
Planejamento para usuários em roaming em uma implantação E9-1-1 usando provedores de tronco SIP, no Skype for Business Server Enterprise Voice.
  
Se um cliente estiver localizado fora da rede ou em uma subrede indefinida, o usuário poderá inserir manualmente um local. Mas durante uma chamada de emergência, a chamada será roteada primeiro para o ECRC (Centro de resposta de chamada de emergência) de E9-1-1 nacional/regional antes de ser roteada para um PSAP (Ponto de atendimento público seguro). O ECRC consultará verbalmente o chamador por um local e encaminhará a chamada para o PSAP adequado, com base nas informações fornecidas. 
  
**Os usuários devem ser solicitados a inserir um local quando não for fornecido automaticamente pelo serviço de Informações de Local?**
  
Por exemplo, se um cliente estiver localizado em uma sub-rede indefinida, em casa, em um hotel ou em qualquer outro lugar fora da rede, o usuário deverá inserir um local?
    
É possível definir a configuração **Local obrigatório** na política de local para definir o comportamento do cliente. Configurar este valor para Não significa que o usuário não será solicitado por um local. Configurar este valor para Sim significa que o usuário será solicitado por um local, mas pode ignorar a solicitação. A configuração deste valor para Isenção de responsabilidade significa que o usuário será solicitado por um local e exibirá uma isenção de responsabilidade se tentar ignorar a solicitação. De qualquer forma, o usuário pode contribuir com o uso do cliente, como sempre.
    
Quando um usuário insere manualmente um local, o local é mapeado para o endereço MAC do gateway padrão da rede do cliente e armazenado em uma tabela por usuário localizada no cliente. Quando o usuário retorna a qualquer local armazenado anteriormente, o cliente Skype for Business se define automaticamente para esse local. 
  
> [!NOTE]
> Você pode modificar apenas a localização atual do seu cliente, mas também pode excluir qualquer local armazenado na tabela do usuário local. 
  

