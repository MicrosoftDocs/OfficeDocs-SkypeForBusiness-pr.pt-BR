---
title: (Opcional) Verificar a implantação de estacionamento de chamada no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Verificando a implantação do estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: b07b3b3bfb709770a4f30f2f6cb43e5ce5dbcc3a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000526"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Opcional) Verificar a implantação de estacionamento de chamada no Skype para negócios
 
Verificando a implantação do estacionamento de chamada no Skype para Business Server Enterprise Voice. 
  
Depois de instalar e configurar o estacionamento de chamada, você precisará verificar a configuração para certificar-se de que o estacionamento e recuperação de chamadas funcionam como esperado. No mínimo, verifique o seguinte:
  
- Ligue para um usuário que tem o estacionamento de chamadas ativado e ter o estacionamento de usuário a chamada.
    
    > [!NOTE]
    > Se você habilitou o estacionamento de chamadas na política de voz antes de executar esse teste, o usuário que é o estacionamento de chamada deve sair do Skype para negócios e entrar novamente, para conseguir ver a opção de estacionamento de chamada na transferência de lista de chamadas. 
  
- Disque o número de órbita para recuperar a chamada.
    
- Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para **OnTimeoutURI**.
    

