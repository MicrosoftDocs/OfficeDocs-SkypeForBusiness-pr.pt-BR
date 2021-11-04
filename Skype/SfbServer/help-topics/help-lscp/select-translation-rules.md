---
title: Selecionar Regras de Conversão
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Enterprise Voice requer que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E.164 com a finalidade de executar a RNL (busca de número reverso). O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.
ms.openlocfilehash: e7e9c08c0d34070eda4abe0f2c490086428a3d4c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772437"
---
# <a name="select-translation-rules"></a>Selecionar Regras de Tradução
 
 Enterprise Voice requer que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E.164 com a finalidade de executar a RNL (busca de número reverso). O ponto de tronco (ou seja, o gateway, PBX ou tronco SIP associado) pode exigir que os números estejam no formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir, opcionalmente, uma ou mais regras de conversão para manipular a URI de Solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.
  
> [!IMPORTANT]
> A capacidade de associar uma ou mais regras de conversão de uma configuração de tronco do Enterprise Voice se destina a ser usada como uma alternativa  para configurar as regras de conversão no ponto de tronco. Não associe as regras de conversão de uma configuração de tronco Enterprise Voice se você tiver configurado regras de conversão no peer de tronco, porque as duas regras podem entrar em conflito. 
  
Clique em uma regra na lista e então em **OK** para usar uma regra de conversão existente.
  
Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o Painel de Controle Skype for Business Server, consulte [Manage Skype for Business Server 2015](../../manage/manage.md).
  

