---
title: Limpar Cache
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumo: Saiba mais sobre a operação Clear Cache, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 918709d87545289e46c6bef49aafb0f1d37b2950
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930802"
---
# <a name="clear-cache"></a>Limpar Cache
 
**Resumo:** Saiba mais sobre a operação Clear Cache, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
A operação de Clear Cache é parte da API de dados para o painel de qualidade de chamada.
  
## <a name="clear-cache"></a>Limpar Cache

Operação de Clear Cache exclui o cache no servidor para consultas e dados. Isso redefinirá o cache e abordaremos dados atualizados do cubo de QoE posteriormente para novas solicitações.
  

|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Postar  <br/> |https://\<portal\>/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
 O **corpo da solicitação** - None.
  
 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).
  
 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
 **Corpo de resposta** - None.
  

