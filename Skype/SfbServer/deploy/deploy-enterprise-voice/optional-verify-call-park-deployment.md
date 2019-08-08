---
title: Adicionais Verificar a implantação do estacionamento de chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Como verificar sua implantação do parque de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: d698bf46f0a36a86729856c388fde09514288253
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240432"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>Adicionais Verificar a implantação do estacionamento de chamadas no Skype for Business
 
Como verificar sua implantação do parque de chamadas no Skype for Business Server Enterprise Voice. 
  
Depois de instalar e configurar o parque de chamadas, você precisa verificar a configuração para garantir que o estacionamento e a recuperação de chamadas funcionarão como esperado. No mínimo, verifique o seguinte:
  
- Ligue para um usuário que tenha o estacionamento de chamadas habilitado e tenha o usuário que estaciona a chamada.
    
    > [!NOTE]
    > Se você ativou o estacionamento de chamadas na política de voz antes de realizar esse teste, o usuário que está estacionando a chamada precisa sair do Skype for Business e, em seguida, entrar novamente para poder ver a opção parque de chamadas na lista transferir chamadas. 
  
- Disque o número de órbita para recuperar a chamada.
    
- Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para **OnTimeoutURI**.
    

