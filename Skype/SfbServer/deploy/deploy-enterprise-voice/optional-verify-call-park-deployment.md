---
title: (Opcional) Verificar a implantação do Estacionamento de Chamada Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Verificando sua implantação do Estacionamento de Chamada no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 279f55e058678bdd33616a71642555b134052018
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579945"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Opcional) Verificar a implantação do Estacionamento de Chamada Skype for Business
 
Verificando sua implantação do Estacionamento de Chamada no Skype for Business Server Enterprise Voice. 
  
Depois de instalar e configurar o Estacionamento de Chamadas, você precisa verificar a configuração para garantir que o estacionamento e a recuperação de chamadas funcionem conforme o esperado. No mínimo, verifique o seguinte:
  
- Chame um usuário que tenha o Estacionamento de Chamada habilitado e que o usuário estae a chamada.
    
    > [!NOTE]
    > Se você habilitar o Estacionamento de Chamadas na política de voz pouco antes de executar esse teste, o usuário que estiver estacionando a chamada precisará sair do Skype for Business e entrar novamente, para poder ver a opção Estacionamento de Chamada na lista de chamadas de transferência. 
  
- Disque o número de órbita para recuperar a chamada.
    
- Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para **OnTimeoutURI**.
    

