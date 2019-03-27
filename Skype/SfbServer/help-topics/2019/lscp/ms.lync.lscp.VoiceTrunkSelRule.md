---
title: Selecionar Regras de Conversão
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: O Enterprise Voice requer que todas as cadeias de caracteres de discagem ser normalizado no formato e. 164 para fins de executar a pesquisa inversa (RNL). O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.
ms.openlocfilehash: 30b1102ad6bff37079af8d99ee7ecaa1801d7fdb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875157"
---
# <a name="select-translation-rules"></a>Selecionar Regras de Conversão
 
 O Enterprise Voice requer que todas as cadeias de caracteres de discagem ser normalizado no formato e. 164 para fins de executar a pesquisa inversa (RNL). O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.
  
> [!IMPORTANT]
> A capacidade de associar um ou mais regras de conversão de uma configuração de tronco do Enterprise Voice é destinada a ser usado como uma alternativa para configurar as regras de conversão no ponto do tronco. Não associe regras de conversão com uma configuração de tronco do Enterprise Voice se você tiver configurado regras de conversão no ponto do tronco, pois as duas regras podem entrar em conflito. 
  
Clique em uma regra na lista e então em **OK** para usar uma regra de conversão existente.
  
 
  

