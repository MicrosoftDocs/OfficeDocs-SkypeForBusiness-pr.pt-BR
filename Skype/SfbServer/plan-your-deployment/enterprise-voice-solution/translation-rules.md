---
title: Regras de conversão no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Saiba mais sobre as regras de conversão e discar normalization de cadeia de caracteres no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 5b609701779a80645061036fd04e4a46427261b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206456"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Regras de conversão no Skype para Business Server

Saiba mais sobre as regras de conversão e discar normalization de cadeia de caracteres no Skype para Business Server Enterprise Voice.

 O Enterprise Voice requer que todas as cadeias de caracteres de discagem ser normalizado no formato e. 164 para fins de executar a pesquisa inversa (RNL). Regras de conversão são suportadas para os números de chamada e chamada. Thetrunk ponto (ou seja, o gateway associado, privada de comutação de PBX ou tronco SIP) pode exigir que os números estar em um formato de discagem local. To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer. For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.

Executando a conversão da rota de saída no servidor, você pode reduzir os requisitos de configuração em cada par de tronco individual para converter os números de telefone em um formato de discagem. Quando você planejar quais gateways e quantos gateways, para associar um cluster de servidor de mediação específico, pode ser útil para pares de tronco de grupo com local semelhante requisitos de discagem. Isso pode reduzir o número de regras de conversão necessárias e o tempo necessário para gravá-las.

> [!IMPORTANT]
> Associar um ou mais regras de conversão de uma configuração de tronco do Enterprise Voice deverão ser usada como uma alternativa para configurar as regras de conversão no ponto do tronco. Não associe regras de conversão com uma configuração de tronco do Enterprise Voice se você tiver configurado as regras de conversão no ponto do tronco, pois as duas regras podem entrar em conflito.

## <a name="example-translation-rules"></a>Exemplo de regras de conversão

Os exemplos a seguir de regras de conversão mostram como você pode desenvolver as regras no servidor para converter números do formato E.164 para um formato local para o par de tronco.

Para obter detalhes sobre como implementar as regras de conversão, consulte  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) na documentação de Implantação.

|**Descrição**|**Dígitos iniciais**|**Tamanho**|**Dígitos a serem removidos**|**Dígitos a serem adicionados**|**Padrão de correspondência**|**Conversão**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Discagem convencional de longa distância nos EUA  <br/> (retirar o '+')  <br/> |+1  <br/> |Exatamente 12  <br/> |1  <br/> |0  <br/> |^\+(1\d{10}) $  <br/> |$1  <br/> |+14255551010 se torna 14255551010  <br/> |
|Discagem de longa distância internacional dos EUA  <br/> (retirar '+' e adicionar 011)  <br/> |+  <br/> |Pelo menos 11  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d+)$  <br/> |011$1  <br/> |+441235551010 se torna 011441235551010  <br/> |


