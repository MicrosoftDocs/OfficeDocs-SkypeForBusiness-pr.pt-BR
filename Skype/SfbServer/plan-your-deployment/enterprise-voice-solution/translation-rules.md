---
title: Regras de tradução no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Saiba mais sobre as regras de tradução e disque a normalização de cadeias de caracteres no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: c82b925c9ef168d8a5f5e7ac730a93a53a432e2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802391"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Regras de tradução no Skype for Business Server

Saiba mais sobre as regras de tradução e disque a normalização de cadeias de caracteres no Skype for Business Server Enterprise Voice.

 O Enterprise Voice requer que todas as cadeias de discagem sejam normalizadas para o formato E. 164 para realizar uma pesquisa de número reverso (RNL). As regras de tradução têm suporte para números de chamada e números chamados. O par de troncos (ou seja, o gateway associado, o PBX (Private Branch Exchange) ou o tronco SIP) podem exigir que os números estejam em um formato de discagem local. To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer. For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.

Executando a conversão da rota de saída no servidor, você pode reduzir os requisitos de configuração em cada par de tronco individual para converter os números de telefone em um formato de discagem. Quando você planeja quais gateways e quantos gateways, associar a um cluster de servidor de mediação específico, pode ser útil agrupar pares de tronco com requisitos de discagem locais semelhantes. Isso pode reduzir o número de regras de conversão necessárias e o tempo necessário para gravá-las.

> [!IMPORTANT]
> Associar uma ou mais regras de tradução a uma configuração de tronco do Enterprise Voice deve ser usado como uma alternativa para configurar regras de tradução no par de troncos. Não associe as regras de tradução a uma configuração de tronco do Enterprise Voice se você tiver configurado regras de tradução no par de tronco, pois as duas regras podem entrar em conflito.

## <a name="example-translation-rules"></a>Exemplo de regras de conversão

Os exemplos a seguir de regras de conversão mostram como você pode desenvolver as regras no servidor para converter números do formato E.164 para um formato local para o par de tronco.

Para obter detalhes sobre como implementar as regras de conversão, consulte  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) na documentação de Implantação.

|**Descrição**|**Dígitos iniciais**|**Tamanho**|**Dígitos a serem removidos**|**Dígitos a serem adicionados**|**Padrão de correspondência**|**Conversão**|**Exemplo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Discagem convencional de longa distância nos EUA  <br/> (remova o "+")  <br/> |+1  <br/> |Exatamente 12  <br/> |1  <br/> |0  <br/> |^\+(1 \ d{10}) $  <br/> |$1  <br/> |+14255551010 se torna 14255551010  <br/> |
|Discagem de longa distância internacional dos EUA  <br/> (remover a faixa "+" e adicionar 011)  <br/> |+  <br/> |Pelo menos 11  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d +) $  <br/> |011$1  <br/> |+441235551010 se torna 011441235551010  <br/> |


