---
title: Definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Planejando para usuários móveis em uma implantação do E9-1-1 usando provedores de entroncamento SIP no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 85bf13325d3c7c16958877d50f49057a7f402226
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802711"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server
 
Planejando para usuários móveis em uma implantação do E9-1-1 usando provedores de entroncamento SIP no Skype for Business Server Enterprise Voice.
  
Se um cliente estiver localizado fora da rede ou em uma subrede indefinida, o usuário poderá inserir manualmente um local. Mas durante uma chamada de emergência, a chamada será roteada primeiro para o ECRC (Centro de resposta de chamada de emergência) de E9-1-1 nacional/regional antes de ser roteada para um PSAP (Ponto de atendimento público seguro). O ECRC consultará verbalmente o chamador por um local e encaminhará a chamada para o PSAP adequado, com base nas informações fornecidas. 
  
**Os usuários devem ser solicitados a inserir um local quando um não é fornecido automaticamente pelo serviço de informações de localização?**
  
Por exemplo, se um cliente estiver localizado em uma sub-rede indefinida, em casa, em um hotel ou em qualquer outro lugar fora da rede, o usuário deverá inserir um local?
    
É possível definir a configuração **Local obrigatório** na política de local para definir o comportamento do cliente. Configurar este valor para Não significa que o usuário não será solicitado por um local. Configurar este valor para Sim significa que o usuário será solicitado por um local, mas pode ignorar a solicitação. A configuração deste valor para Isenção de responsabilidade significa que o usuário será solicitado por um local e exibirá uma isenção de responsabilidade se tentar ignorar a solicitação. De qualquer forma, o usuário pode contribuir com o uso do cliente, como sempre.
    
Quando um usuário insere manualmente um local, o local é mapeado para o endereço MAC do gateway padrão da rede do cliente e é armazenado em uma tabela por usuário localizada no cliente. Quando o usuário retorna a qualquer local armazenado anteriormente, o cliente Skype for Business define-se automaticamente para esse local. 
  
> [!NOTE]
> Você pode modificar apenas a localização atual do cliente, mas também pode excluir qualquer local armazenado na tabela do usuário local. 
  

