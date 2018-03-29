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
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a><span data-ttu-id="a3d51-103">(Opcional) Verificar implantação de Estacionamento de Chamada no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="a3d51-103">(Optional) Verify Call Park deployment in Skype for Business 2015</span></span>
 
<span data-ttu-id="a3d51-104">Verificando a implantação do estacionamento de chamada no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a3d51-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="a3d51-105">Depois de instalar e configurar o estacionamento de chamada, você precisará verificar a configuração para certificar-se de que o estacionamento e recuperação de chamadas funcionam como esperado.</span><span class="sxs-lookup"><span data-stu-id="a3d51-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="a3d51-106">No mínimo, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a3d51-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="a3d51-107">Ligue para um usuário que tem o estacionamento de chamadas ativado e ter o estacionamento de usuário a chamada.</span><span class="sxs-lookup"><span data-stu-id="a3d51-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a3d51-108">Se você habilitou o estacionamento de chamadas na política de voz antes de executar esse teste, o usuário que é o estacionamento de chamada deve sair do Skype para negócios e entrar novamente, para conseguir ver a opção de estacionamento de chamada na transferência de lista de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a3d51-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="a3d51-109">Disque o número de órbita para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="a3d51-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="a3d51-p102">Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="a3d51-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

