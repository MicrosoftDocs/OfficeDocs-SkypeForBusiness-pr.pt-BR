---
title: Adicionais Verificar a implantação do estacionamento de chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Como verificar sua implantação do parque de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 94d230491c0207c05016545de3c45cf0582ca496
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292840"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="06239-103">Adicionais Verificar a implantação do estacionamento de chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="06239-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="06239-104">Como verificar sua implantação do parque de chamadas no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="06239-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="06239-105">Depois de instalar e configurar o parque de chamadas, você precisa verificar a configuração para garantir que o estacionamento e a recuperação de chamadas funcionarão como esperado.</span><span class="sxs-lookup"><span data-stu-id="06239-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="06239-106">No mínimo, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="06239-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="06239-107">Ligue para um usuário que tenha o estacionamento de chamadas habilitado e tenha o usuário que estaciona a chamada.</span><span class="sxs-lookup"><span data-stu-id="06239-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="06239-108">Se você ativou o estacionamento de chamadas na política de voz antes de realizar esse teste, o usuário que está estacionando a chamada precisa sair do Skype for Business e, em seguida, entrar novamente para poder ver a opção parque de chamadas na lista transferir chamadas.</span><span class="sxs-lookup"><span data-stu-id="06239-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="06239-109">Disque o número de órbita para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="06239-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="06239-p102">Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="06239-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

