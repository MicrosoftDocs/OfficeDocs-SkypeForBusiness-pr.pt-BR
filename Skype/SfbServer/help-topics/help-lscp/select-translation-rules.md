---
title: Selecionar Regras de Conversão
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: O Enterprise Voice requer que todas as cadeias de discagem sejam normalizadas para o formato E. 164 para realizar uma pesquisa de número reverso (RNL). O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.
ms.openlocfilehash: 89505dda4bb534ad62455bf1fd835efb81ce6f0b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293295"
---
# <a name="select-translation-rules"></a><span data-ttu-id="6eb10-106">Selecionar Regras de Conversão</span><span class="sxs-lookup"><span data-stu-id="6eb10-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="6eb10-107">O Enterprise Voice requer que todas as cadeias de discagem sejam normalizadas para o formato E. 164 para realizar uma pesquisa de número reverso (RNL).</span><span class="sxs-lookup"><span data-stu-id="6eb10-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="6eb10-108">O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local.</span><span class="sxs-lookup"><span data-stu-id="6eb10-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="6eb10-109">Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco.</span><span class="sxs-lookup"><span data-stu-id="6eb10-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="6eb10-110">Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.</span><span class="sxs-lookup"><span data-stu-id="6eb10-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6eb10-111">A capacidade de associar uma ou mais regras de tradução a uma configuração de tronco Enterprise Voice deve ser usada como uma alternativa para configurar regras de tradução no par de troncos.</span><span class="sxs-lookup"><span data-stu-id="6eb10-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="6eb10-112">Não associe as regras de tradução a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de tradução no par de tronco porque as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="6eb10-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="6eb10-113">Clique em uma regra na lista e então em **OK** para usar uma regra de conversão existente.</span><span class="sxs-lookup"><span data-stu-id="6eb10-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="6eb10-114">Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o painel de controle do Skype for Business Server, consulte [gerenciar o Skype for Business server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="6eb10-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

