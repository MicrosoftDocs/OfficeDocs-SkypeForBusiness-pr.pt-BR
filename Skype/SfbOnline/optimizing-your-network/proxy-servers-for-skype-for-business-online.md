---
title: Servidores Proxy para Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "Este artigo fornecerá diretrizes para você usar um servidor proxy com o Skype for Business."
ms.openlocfilehash: 19c12ed4265c6549f00b54b3463215702d3ced2b
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Servidores Proxy para Skype for Business Online

Este artigo fornecerá diretrizes para você usar um servidor proxy com o Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>É recomendável não usar um servidor proxy

Quanto ao tráfego do Skype for Business por meio de proxies, a Microsoft recomenda não usar proxies. Os proxies não tornam o Skype for Business mais seguro, porque seu tráfego já é criptografado.
  
E o uso de um proxy pode ocasionar problemas. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Esses problemas resultarão em uma experiência negativa em cenários do Skype for Business como áudio e vídeo, onde streams em tempo real são essenciais.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Caso seja necessário o uso de um servidor proxy

Algumas organizações não têm a opção de não usar um proxy para o tráfego do Skype for Business. Nesse caso, os problemas mencionados acima deverão ser levados em consideração.
  
A Microsoft também recomenda:
  
- O uso de resolução DNS externa
    
- O uso de UDP direto com base em roteamento
    
- Permissão para tráfego UDP
    
- A seguir são apresentadas outras recomendações que constam em nossas diretrizes de rede:
    
  - [Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Como otimizar sua rede para o Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
A observação desta diretriz minimizará problemas potenciais.
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a>Os fornecedores proxy com o Skype for Business embutido oferecem suporte ou opções de configuração

Esta seção apresentará informações sobre fornecedores de proxy que fornecem produtos ou serviços que, comprovadamente, funcionam bem com o tráfego do Skype for Business.
  
Para as organizações que usam as **soluções Bluecoat Proxy**, foi lançado um novo firmware que trata de vários problemas relacionados a:
    
  - Interceptação SSL
    
  - Verificações de OCSP/SRL
    
  - SIP por meio de TLS
    
  - Suporte para TURN
    
O suporte nativo do Bluecoat para Skype for Business pode ser facilmente ativado, permitindo a identificação de tráfego relevante, e gerenciando-o adequadamente. Isso assegura autenticação, sinalização e fluxo de tráfego de mídia otimizados a fim de fornecer uma excelente experiência do usuário sem preocupações com segurança.
    
Consulte o seguinte link se Bluecoat Proxy é uma parte de sua topologia de rede: https://support.symantec.com/en_US/article.DOC9757.html

## <a name="related-topics"></a>Tópicos relacionados

[Como otimizar sua rede para o Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)