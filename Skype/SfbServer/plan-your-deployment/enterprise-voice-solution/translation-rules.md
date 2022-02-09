---
title: Regras de conversão em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Saiba mais sobre regras de conversão e normalização da cadeia de caracteres de discagem Skype for Business Server Enterprise Voice.
ms.openlocfilehash: c2cc7990a0b3c61ef11e20fbc43b678a841d8137
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403740"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Regras de conversão em Skype for Business Server

Saiba mais sobre regras de conversão e normalização da cadeia de caracteres de discagem Skype for Business Server Enterprise Voice.

 Enterprise Voice requer que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E.164 com a finalidade de executar a RNL (busca de número reverso). As regras de conversão são suportadas para números chamados e números de chamadas. O partrunk (ou seja, o gateway associado, PBX (private branch exchange) ou tronco SIP) pode exigir que os números sejam em um formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir uma ou mais regras de conversão para manipular a URI da solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.

Executando a conversão da rota de saída no servidor, você pode reduzir os requisitos de configuração em cada par de tronco individual para converter os números de telefone em um formato de discagem. Quando você planeja quais gateways e quantos gateways associar a um cluster específico do Servidor de Mediação, pode ser útil agrupar pares de tronco com requisitos de discagem locais semelhantes. Isso pode reduzir o número de regras de conversão necessárias e o tempo necessário para gravá-las.

> [!IMPORTANT]
> Associar uma ou mais regras de conversão a uma configuração de tronco Enterprise Voice deve ser usada como uma alternativa à configuração de regras de conversão no ponto de tronco. Não associe regras de conversão a uma configuração de tronco Enterprise Voice se você tiver configurado regras de conversão no ponto de tronco, pois as duas regras podem estar em conflito.

## <a name="example-translation-rules"></a>Exemplo de regras de conversão

Os exemplos a seguir de regras de conversão mostram como você pode desenvolver as regras no servidor para converter números do formato E.164 para um formato local para o par de tronco.

Para obter detalhes sobre como implementar as regras de conversão, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) na documentação de Implantação.

|**Descrição**|**Dígitos iniciais**|**Length**|**Dígitos a serem removidos**|**Dígitos a serem adicionados**|**Padrão de correspondência**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Discagem convencional de longa distância nos EUA  <br/> (tire o '+')  <br/> |+1  <br/> |Exatamente 12  <br/> |1  <br/> |0  <br/> |^\+(1\d{10}) $  <br/> |$1  <br/> |+14255551010 se torna 14255551010  <br/> |
|Discagem de longa distância internacional dos EUA  <br/> (desmarcar '+' e adicionar 011)  <br/> |+  <br/> |Pelo menos 11  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d+)$  <br/> |011$1  <br/> |+441235551010 se torna 011441235551010  <br/> |