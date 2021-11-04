---
title: Definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planejando usuários de roaming em uma implantação do E9-1-1 usando provedores de tronco SIP, Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 263c2e79e340492b27d196f73373505f7c1e4f66
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770109"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server
 
Planejando usuários de roaming em uma implantação do E9-1-1 usando provedores de tronco SIP, Skype for Business Server Enterprise Voice.
  
Se um cliente estiver localizado fora da rede ou em uma subrede indefinida, o usuário poderá inserir manualmente um local. Mas durante uma chamada de emergência, a chamada será roteada primeiro para o ECRC (Centro de resposta de chamada de emergência) de E9-1-1 nacional/regional antes de ser roteada para um PSAP (Ponto de atendimento público seguro). O ECRC consultará verbalmente o chamador por um local e encaminhará a chamada para o PSAP adequado, com base nas informações fornecidas. 
  
**Os usuários devem ser solicitados a inserir um local quando um não for fornecido automaticamente pelo serviço de Informações de Local?**
  
Por exemplo, se um cliente estiver localizado em uma sub-rede indefinida, em casa, em um hotel ou em qualquer outro lugar fora da rede, o usuário deverá inserir um local?
    
É possível definir a configuração **Local obrigatório** na política de local para definir o comportamento do cliente. Configurar este valor para Não significa que o usuário não será solicitado por um local. Configurar este valor para Sim significa que o usuário será solicitado por um local, mas pode ignorar a solicitação. A configuração deste valor para Isenção de responsabilidade significa que o usuário será solicitado por um local e exibirá uma isenção de responsabilidade se tentar ignorar a solicitação. De qualquer forma, o usuário pode contribuir com o uso do cliente, como sempre.
    
Quando um usuário insere manualmente um local, o local é mapeado para o endereço MAC do gateway padrão da rede do cliente e é armazenado em uma tabela por usuário localizada no cliente. Quando o usuário retorna para qualquer local armazenado anteriormente, o cliente Skype for Business automaticamente se define para esse local. 
  
> [!NOTE]
> Você pode modificar apenas o local atual do seu cliente, mas também pode excluir qualquer local armazenado na tabela do usuário local. 
  

