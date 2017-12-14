---
title: "Servidores Proxy para Skype for Business Online"
ms.author: tonysmit
author: tonysmit
ms.date: 11/6/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
description: "Este artigo fornecerá diretrizes para você usar um servidor proxy com o Skype for Business."
---

# Servidores Proxy para Skype for Business Online

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](7acaf2c2-35fa-490f-84cd-822e446e0fc7.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/7acaf2c2-35fa-490f-84cd-822e446e0fc7). 
  
Este artigo fornecerá diretrizes para você usar um servidor proxy com o Skype for Business.
  
## É recomendável não usar um servidor proxy

Quanto ao tráfego do Skype for Business por meio de proxies, a Microsoft recomenda não usar proxies. Os proxies não tornam o Skype for Business mais seguro, porque seu tráfego já é criptografado.
  
E o uso de um proxy pode ocasionar problemas. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Esses problemas resultarão em uma experiência negativa em cenários do Skype for Business como áudio e vídeo, onde streams em tempo real são essenciais.
  
## Caso seja necessário o uso de um servidor proxy

Algumas organizações não têm nenhuma opção para ignorar um proxy para Skype para o tráfego de negócios. Se esse for o caso, os problemas mencionados acima precisam ser mantidos em mente.
  
A Microsoft também recomenda:
  
- O uso de resolução DNS externa
    
- O uso de UDP direto com base em roteamento
    
- Permissão para tráfego UDP 
    
- A seguir são apresentadas outras recomendações que constam em nossas diretrizes de rede:
    
  - [Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Como otimizar sua rede para o Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
A observação desta diretriz minimizará problemas potenciais.
  
## Os fornecedores proxy com o Skype for Business embutido oferecem suporte ou opções de configuração

Esta seção apresentará informações sobre fornecedores de proxy que fornecem produtos ou serviços que, comprovadamente, funcionam bem com o tráfego do Skype for Business.
  
- Para as organizações que usam as **soluções Bluecoat Proxy**, foi lançado um novo firmware que trata de vários problemas relacionados a:
    
  - Interceptação SSL
    
  - Verificações de OCSP/SRL
    
  - SIP por meio de TLS
    
  - Suporte para TURN
    
    O suporte nativo do Bluecoat para Skype for Business pode ser facilmente ativado, permitindo a identificação de tráfego relevante, e gerenciando-o adequadamente. Isso assegura autenticação, sinalização e fluxo de tráfego de mídia otimizados a fim de fornecer uma excelente experiência do usuário sem preocupações com segurança.
    
    Consulte o link a seguir se Bluecoat Proxy é uma parte da sua topologia de rede
    
- https://support.Symantec.com/en_US/article.DOC9757.HTML
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

