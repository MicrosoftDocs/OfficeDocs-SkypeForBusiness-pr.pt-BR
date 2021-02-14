---
title: Regras de conversão no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Saiba mais sobre regras de conversão e normalização de cadeia de caracteres de discagem no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 0c00776dae502bfd28bbe27e90012fabb6e25c93
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802681"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Regras de conversão no Skype for Business Server

Saiba mais sobre regras de conversão e normalização de cadeia de caracteres de discagem no Skype for Business Server Enterprise Voice.

 O Enterprise Voice exige que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E.164 com a finalidade de realizar a RNL (busca inversa de números). As regras de conversão são suportadas tanto para números chamados quanto para números de chamada. O par de troncos (ou seja, o gateway associado, PBX ou tronco SIP) pode exigir que os números estão em um formato de discagem local. Para converter os números do formato E.164 em um formato de discagem local, você pode definir uma ou mais regras de conversão para manipular a URI da solicitação antes de roteá-la para o ponto do tronco. Por exemplo, é possível elaborar uma regra de conversão para remover o +44 do início de uma cadeia de caracteres de discagem e substituí-lo por 0144.

Executando a conversão da rota de saída no servidor, você pode reduzir os requisitos de configuração em cada par de tronco individual para converter os números de telefone em um formato de discagem. Ao planejar quais gateways e quantos gateways associar a um cluster específico do Servidor de Mediação, pode ser útil agrupar pares de tronco com requisitos de discagem local semelhantes. Isso pode reduzir o número de regras de conversão necessárias e o tempo necessário para gravá-las.

> [!IMPORTANT]
> A associação de uma ou mais regras de conversão a uma configuração de tronco do Enterprise Voice deve ser usada como uma alternativa à configuração de regras de conversão no ponto de tronco. Não associe as regras de conversão a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de conversão no ponto do tronco, porque as duas regras podem estar em conflito.

## <a name="example-translation-rules"></a>Exemplo de regras de conversão

Os exemplos a seguir de regras de conversão mostram como você pode desenvolver as regras no servidor para converter números do formato E.164 para um formato local para o par de tronco.

Para obter detalhes sobre como implementar as regras de conversão, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) na documentação de Implantação.

|**Descrição**|**Dígitos iniciais**|**Length**|**Dígitos a serem removidos**|**Dígitos a serem adicionados**|**Padrão de correspondência**|**Tradução**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Discagem convencional de longa distância nos EUA  <br/> (retirar o '+')  <br/> |+1  <br/> |Exatamente 12  <br/> |1   <br/> |0  <br/> |^\+(1\d) {10} $  <br/> |$1  <br/> |+14255551010 se torna 14255551010  <br/> |
|Discagem de longa distância internacional dos EUA  <br/> (retirar '+' e adicionar 011)  <br/> |+  <br/> |Pelo menos 11  <br/> |1   <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 se torna 011441235551010  <br/> |


