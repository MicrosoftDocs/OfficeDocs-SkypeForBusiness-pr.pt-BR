---
title: API de Dados para Painel de Qualidade de Chamadas (CQD) no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumo: Saiba mais sobre a API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832691"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de Dados para Painel de Qualidade de Chamadas (CQD) no Skype for Business Server
 
**Resumo:** Saiba mais sobre a API de Dados para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A API de Dados fornece acesso programático para o Painel de Qualidade de Chamadas do Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de Dados para Painel de Qualidade da Chamada

A API de Dados oferece uma interface de consulta para o cubo QoE. A API de Dados é uma API REST para trabalhar com banco de dados multidimensional que fornece métricas de QoE agregadas com base em dimensões e filtros especificados.
  
As operações REST estão incluídas na tabela a seguir.
  

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter o cubo](get-cube.md) <br/> |Obter a lista de dimensões e medidas disponíveis.  <br/> |
|[Obtenha os Membros da Dimensão](get-dimension-members.md) <br/> |A operação Obter Membros da Dimensão retorna a lista de membros de uma dimensão específica. Ele também dá a capacidade de filtrar a lista de membros e obter um subconjunto, para reduzir o custo de transferência eletrônica.  <br/> |
|[Executar Consulta](run-query.md) <br/> |A operação Executar Consulta oferece a capacidade de executar uma consulta no cubo com base em dimensões, medidas e filtros especificados e retornar os dados.  <br/> |
|[Limpar Cache](clear-cache.md) <br/> |A operação Limpar Cache exclui o cache no servidor para consultas e dados. Isso redefini o cache e obteremos dados atualizados do Cubo QoE posteriormente para novas solicitações.  <br/> |
|[Obter o Log de integração](get-integration-log.md) <br/> |A operação Obter Log de Integração retorna uma lista de entradas de log que descrevem as atividades no processamento do cubo de QoE.  <br/> |
|[Obter Últimos Dados de Integração](get-last-integration-data.md) <br/> |Obter os últimos dados de integração do cubo.  <br/> |
   
 **Suporte ao CORS (Compartilhamento de Recursos entre Origens) para API de Dados**
  
A API de Dados dá suporte ao CORS (Compartilhamento de Recursos entre Origens). CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio. Os navegadores da Web [](https://www.w3.org/Security/wiki/Same_Origin_Policy) implementam uma restrição de segurança conhecida como política de mesma origem que impede que uma página da Web chamar APIs em um domínio diferente. O CORS oferece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio. Consulte a [especificação CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre CORS.
  
 **Habilitando CORS para API de Dados**
  
 Veja a seguir um trecho da API de dados web.config, mostrando dois domínios listados nas configurações do aplicativo corsTrustedOrigin. Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis para a API de Dados.
  
Lembre-se de incluir o protocolo exato, o nome do host e a porta (se algum). Não coloque nenhum caractere de barra (/) no final. Várias entradas podem ser especificadas separando-as por vírgulas.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


