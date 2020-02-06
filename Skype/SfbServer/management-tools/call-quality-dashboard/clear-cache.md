---
title: Limpar Cache
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumo: Saiba mais sobre a operação de limpeza de cache, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 821b02f204c98f5acefe69df1c848c31cd2205b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816880"
---
# <a name="clear-cache"></a>Limpar Cache
 
**Resumo:** Saiba mais sobre a operação de limpeza de cache, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A operação de cache limpar faz parte da API de dados para o painel de qualidade da chamada.
  
## <a name="clear-cache"></a>Limpar Cache

Limpar operação de cache exclui o cache no servidor para consultas e dados. Isso redefinirá o cache e obteremos dados atualizados do cubo de QoE posteriormente para novas solicitações.
  

|**Forma**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|Postar  <br/> |https://\<do\>portal de/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** -nenhum.
  
 **Solicitar cabeçalhos** -sem cabeçalhos adicionais.
  
 **Corpo da solicitação** -nenhum.
  
 **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Cabeçalhos de resposta** -sem cabeçalhos adicionais.
  
 **Corpo da resposta** -nenhum.
  

