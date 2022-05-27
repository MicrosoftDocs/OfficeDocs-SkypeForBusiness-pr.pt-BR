---
title: API de Dados para CQD (Painel de Qualidade de Chamada) no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumo: Saiba mais sobre a API de Dados para o Painel de Qualidade da Chamada. O Painel de Qualidade de Chamadas é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 3204398dcf667f785f1efe71cc4d6dc5478ce54d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675733"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de Dados para CQD (Painel de Qualidade de Chamada) no Skype for Business Server
 
**Resumo:** Saiba mais sobre a API de Dados para o Painel de Qualidade da Chamada. O Painel de Qualidade de Chamadas é uma ferramenta para Skype for Business Server.
  
A API de Dados fornece acesso programático para o Painel de Qualidade de Chamadas para Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de Dados para Painel de Qualidade da Chamada

A API de Dados oferece uma interface de consulta para o cubo QoE. A API de Dados é uma API REST para trabalhar com o banco de dados multidimensional que fornece métricas de QoE agregadas com base em dimensões e filtros especificados.
  
As operações REST estão incluídas na tabela a seguir.
  

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter o cubo](get-cube.md) <br/> |Obtenha a lista de dimensões e medidas disponíveis.  <br/> |
|[Obtenha os Membros da Dimensão](get-dimension-members.md) <br/> |A operação Obter Membros da Dimensão retorna a lista de membros de uma dimensão específica. Ele também oferece a capacidade de filtrar a lista de membros e obter um subconjunto, para reduzir o custo de transferência eletrônica.  <br/> |
|[Executar Consulta](run-query.md) <br/> |A operação Executar Consulta fornece a capacidade de executar uma consulta no cubo com base em dimensões, medidas e filtros especificados e retornar os dados.  <br/> |
|[Limpar Cache](clear-cache.md) <br/> |A operação Limpar Cache exclui o cache no servidor para consultas e dados. Isso redefinirá o cache e obteremos dados atualizados do Cubo QoE posteriormente para novas solicitações.  <br/> |
|[Obter o Log de integração](get-integration-log.md) <br/> |A operação Obter Log de Integração retorna uma lista de entradas de log que descrevem as atividades no processamento do Cubo QoE.  <br/> |
|[Obter Últimos Dados de Integração](get-last-integration-data.md) <br/> |Obtenha os últimos dados de integração do cubo.  <br/> |
   
 **Suporte de CORS (Compartilhamento de Recursos entre Origens) para API de Dados**
  
A API de Dados dá suporte ao CORS (Compartilhamento de Recursos entre Origens). O CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio. Os navegadores da Web implementam uma restrição de segurança conhecida como política de mesma origem que impede que uma página da Web chama APIs em um domínio diferente.[](https://www.w3.org/Security/wiki/Same_Origin_Policy) O CORS fornece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio. Consulte a [especificação do CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre o CORS.
  
 **Habilitando o CORS para API de Dados**
  
 Veja a seguir um trecho da API de Dados web.config, mostrando dois domínios listados nas configurações do aplicativo corsTrustedOrigin. Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis pela API de Dados.
  
Lembre-se de incluir o protocolo exato, o nome do host e a porta (se houver). Não coloque nenhum caractere de barra (/) no final. Várias entradas podem ser especificadas separando-se com vírgulas.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
...  </appSettings>
</configuration>
```


