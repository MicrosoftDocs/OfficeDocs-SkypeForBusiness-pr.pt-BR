---
title: (Opcional) Verificar a implantação do Estacionamento de Chamada no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Verificando a implantação do Estacionamento de Chamada no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830891"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Opcional) Verificar a implantação do Estacionamento de Chamada no Skype for Business
 
Verificando a implantação do Estacionamento de Chamada no Skype for Business Server Enterprise Voice. 
  
Depois de instalar e configurar o Estacionamento de Chamadas, você precisa verificar a configuração para garantir que o estacionamento e a recuperação de chamadas funcionem conforme o esperado. No mínimo, verifique o seguinte:
  
- Ligue para um usuário que tenha o Estacionamento de Chamada habilitado e que tenha o usuário estando a chamada.
    
    > [!NOTE]
    > Se você habilitar o Estacionamento de Chamada na política de voz antes de executar esse teste, o usuário que está estacionando a chamada precisará sair do Skype for Business e entrar novamente para poder ver a opção Estacionamento de Chamada na lista de chamadas de transferência. 
  
- Disque o número de órbita para recuperar a chamada.
    
- Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para **OnTimeoutURI**.
    

