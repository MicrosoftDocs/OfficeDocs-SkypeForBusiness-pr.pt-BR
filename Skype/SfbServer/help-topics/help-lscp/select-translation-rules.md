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
# <a name="select-translation-rules"></a>Selecionar Regras de Conversão
 
 O Enterprise Voice requer que todas as cadeias de discagem sejam normalizadas para o formato E. 164 para realizar uma pesquisa de número reverso (RNL). O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.
  
> [!IMPORTANT]
> A capacidade de associar uma ou mais regras de tradução a uma configuração de tronco Enterprise Voice deve ser usada como uma alternativa para configurar regras de tradução no par de troncos. Não associe as regras de tradução a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de tradução no par de tronco porque as duas regras podem entrar em conflito. 
  
Clique em uma regra na lista e então em **OK** para usar uma regra de conversão existente.
  
Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o painel de controle do Skype for Business Server, consulte [gerenciar o Skype for Business server 2015](../../manage/manage.md).
  

