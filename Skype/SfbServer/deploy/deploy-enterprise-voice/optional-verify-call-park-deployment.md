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
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="c9882-103">(Opcional) Verificar a implantação do Estacionamento de Chamada no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c9882-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="c9882-104">Verificando a implantação do Estacionamento de Chamada no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c9882-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c9882-105">Depois de instalar e configurar o Estacionamento de Chamadas, você precisa verificar a configuração para garantir que o estacionamento e a recuperação de chamadas funcionem conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="c9882-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="c9882-106">No mínimo, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c9882-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="c9882-107">Ligue para um usuário que tenha o Estacionamento de Chamada habilitado e que tenha o usuário estando a chamada.</span><span class="sxs-lookup"><span data-stu-id="c9882-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c9882-108">Se você habilitar o Estacionamento de Chamada na política de voz antes de executar esse teste, o usuário que está estacionando a chamada precisará sair do Skype for Business e entrar novamente para poder ver a opção Estacionamento de Chamada na lista de chamadas de transferência.</span><span class="sxs-lookup"><span data-stu-id="c9882-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="c9882-109">Disque o número de órbita para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="c9882-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="c9882-p102">Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="c9882-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

