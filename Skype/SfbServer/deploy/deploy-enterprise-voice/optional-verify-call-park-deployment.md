---
title: (Opcional) Verificar implantação de Estacionamento de Chamada no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Verificando a implantação do estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: e8b3b0abd06ab8dc69bbe1fbcc5f091dd1350966
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a>(Opcional) Verificar implantação de Estacionamento de Chamada no Skype for Business 2015
 
Verificando a implantação do estacionamento de chamada no Skype para Business Server Enterprise Voice. 
  
Depois de instalar e configurar o estacionamento de chamada, você precisará verificar a configuração para certificar-se de que o estacionamento e recuperação de chamadas funcionam como esperado. No mínimo, verifique o seguinte:
  
- Ligue para um usuário que tem o estacionamento de chamadas ativado e ter o estacionamento de usuário a chamada.
    
    > [!NOTE]
    > Se você habilitou o estacionamento de chamadas na política de voz antes de executar esse teste, o usuário que é o estacionamento de chamada deve sair do Skype para negócios e entrar novamente, para conseguir ver a opção de estacionamento de chamada na transferência de lista de chamadas. 
  
- Disque o número de órbita para recuperar a chamada.
    
- Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para **OnTimeoutURI**.
    

