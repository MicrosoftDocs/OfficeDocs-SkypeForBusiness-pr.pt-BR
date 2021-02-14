---
title: Selecionar Regras de Conversão
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: O Enterprise Voice exige que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E.164 com a finalidade de realizar a RNL (busca inversa de números). O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.
ms.openlocfilehash: 033cfca7fcbb9cde12b585b7086dd7a8bf8d4de8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801311"
---
# <a name="select-translation-rules"></a><span data-ttu-id="d086e-106">Selecionar Regras de Tradução</span><span class="sxs-lookup"><span data-stu-id="d086e-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="d086e-107">O Enterprise Voice exige que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E.164 com a finalidade de realizar a RNL (busca inversa de números).</span><span class="sxs-lookup"><span data-stu-id="d086e-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="d086e-108">O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local.</span><span class="sxs-lookup"><span data-stu-id="d086e-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="d086e-109">Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco.</span><span class="sxs-lookup"><span data-stu-id="d086e-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="d086e-110">Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.</span><span class="sxs-lookup"><span data-stu-id="d086e-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d086e-111">A capacidade de associar uma ou mais regras de conversão de uma configuração de tronco do Enterprise Voice se destina a ser usada como uma alternativa  para configurar as regras de conversão no ponto de tronco.</span><span class="sxs-lookup"><span data-stu-id="d086e-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="d086e-112">Não associe as regras de conversão de uma configuração de tronco Enterprise Voice se você tiver configurado regras de conversão no peer de tronco, porque as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="d086e-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="d086e-113">Clique em uma regra na lista e então em **OK** para usar uma regra de conversão existente.</span><span class="sxs-lookup"><span data-stu-id="d086e-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
 
  

