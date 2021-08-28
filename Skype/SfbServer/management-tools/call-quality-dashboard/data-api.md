---
title: API de dados para CQD (Painel de Qualidade de Chamada) no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumo: Saiba mais sobre a API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 2497b978944ec860d7188560ecaf72091df3f626
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586913"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de dados para CQD (Painel de Qualidade de Chamada) no Skype for Business Server
 
**Resumo:** Saiba mais sobre a API de dados para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A API de dados fornece acesso programático para o Painel de Qualidade de Chamada para Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de dados para Painel de Qualidade de Chamada

A API de Dados oferece uma interface de consulta para o Cubo QoE. A API de Dados é uma API REST para trabalhar com banco de dados multidimensional que fornece métricas de QoE agregadas com base em dimensões e filtros especificados.
  
As operações REST estão incluídas na tabela a seguir.
  

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter o cubo](get-cube.md) <br/> |Obter a lista de dimensões e medidas disponíveis.  <br/> |
|[Obtenha os Membros da Dimensão](get-dimension-members.md) <br/> |Obter a operação Membros da Dimensão retorna a lista de membros de uma dimensão específica. Ele também dá a capacidade de filtrar a lista de membros e obter um subconjunto, para reduzir o custo de transferência de fio.  <br/> |
|[Executar Consulta](run-query.md) <br/> |Executar a operação de consulta fornece a capacidade de executar uma consulta no cubo com base em dimensões, medidas e filtros especificados e retornar os dados.  <br/> |
|[Limpar Cache](clear-cache.md) <br/> |A operação Limpar Cache exclui o cache no servidor para consultas e dados. Isso redefinirá o cache e obteremos dados atualizados do Cubo QoE posteriormente para novas solicitações.  <br/> |
|[Obter o Log de integração](get-integration-log.md) <br/> |Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.  <br/> |
|[Obter Últimos Dados de Integração](get-last-integration-data.md) <br/> |Obter os últimos dados de integração do cubo.  <br/> |
   
 **Suporte a CORS (Compartilhamento de Recursos entre Origens) para API de Dados**
  
A API de dados dá suporte a CORS (Compartilhamento de Recursos de Origem Cruzada). O CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio. Os navegadores da Web [](https://www.w3.org/Security/wiki/Same_Origin_Policy) implementam uma restrição de segurança conhecida como política de mesma origem da Política de Mesma Origem que impede uma página da Web de chamar APIs em um domínio diferente. O CORS fornece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio. Consulte a [especificação do CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre o CORS.
  
 **Habilitando o CORS para API de Dados**
  
 Veja a seguir um trecho da API de dados web.config, mostrando dois domínios listados nas configurações do aplicativo corsTrustedOrigin. Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis pela API de Dados.
  
Lembre-se de incluir o protocolo exato, o nome do host e a porta (se for o caso). Não coloque nenhum caractere de barra para frente (/) no final. Várias entradas podem ser especificadas separando-se com vírgulas.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


