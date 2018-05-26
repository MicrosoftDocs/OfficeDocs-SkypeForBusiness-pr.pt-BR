---
title: Selecionar Regras de Conversão
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: O Enterprise Voice requer que todas as cadeias de caracteres de discagem ser normalizado no formato e. 164 para fins de executar a pesquisa inversa (RNL). O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.
ms.openlocfilehash: b0f99ee8faa679c25d9b2de1b129970d07291dbe
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2018
---
# <a name="select-translation-rules"></a><span data-ttu-id="c835c-106">Selecionar Regras de Conversão</span><span class="sxs-lookup"><span data-stu-id="c835c-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="c835c-107">O Enterprise Voice requer que todas as cadeias de caracteres de discagem ser normalizado no formato e. 164 para fins de executar a pesquisa inversa (RNL).</span><span class="sxs-lookup"><span data-stu-id="c835c-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="c835c-108">O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local.</span><span class="sxs-lookup"><span data-stu-id="c835c-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="c835c-109">Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco.</span><span class="sxs-lookup"><span data-stu-id="c835c-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="c835c-110">Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.</span><span class="sxs-lookup"><span data-stu-id="c835c-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c835c-111">A capacidade de associar um ou mais regras de conversão de uma configuração de tronco do Enterprise Voice é destinada a ser usado como uma alternativa para configurar as regras de conversão no ponto do tronco.</span><span class="sxs-lookup"><span data-stu-id="c835c-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="c835c-112">Não associe regras de conversão com uma configuração de tronco do Enterprise Voice se você tiver configurado regras de conversão no ponto do tronco, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="c835c-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="c835c-113">Clique em uma regra na lista e então em **OK** para usar uma regra de conversão existente.</span><span class="sxs-lookup"><span data-stu-id="c835c-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="c835c-114">Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o Skype para o painel de controle do Business Server, consulte [Gerenciar Skype para Business Server 2015](../../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="c835c-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../../manage/manage.md).</span></span>
  

