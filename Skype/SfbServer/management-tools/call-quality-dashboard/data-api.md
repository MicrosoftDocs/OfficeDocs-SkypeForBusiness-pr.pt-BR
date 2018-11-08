---
title: API de dados para o painel de qualidade de chamada (CQD) no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumo: Saiba mais sobre o API Rata para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 0af168c46e8b2732d5c967550391ab52459ddf95
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035628"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de dados para o painel de qualidade de chamada (CQD) no Skype para Business Server
 
**Resumo:** Saiba mais sobre o API Rata para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
A API de dados fornece acesso programático para painel de controle de qualidade de chamada para Skype para Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de dados para o painel de controle de qualidade de chamada

A API de dados oferece uma interface de consulta ao cubo do QoE. A API de dados é uma API REST para trabalhar com o banco de dados multidimensional que fornece agregadas métricas de QoE com base em filtros e dimensões especificadas.
  
As operações do REST estão incluídas na tabela a seguir.
  

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obtenha o cubo](get-cube.md) <br/> |Obter a lista de medidas e dimensões disponíveis.  <br/> |
|[Obtenha os membros de dimensão](get-dimension-members.md) <br/> |Operação de membros da dimensão Get retorna a lista de membros de uma dimensão específica. Ele também dá a capacidade de filtrar a lista de membro e obtenha um subconjunto, para reduzir o custo de transferência de transmissão.  <br/> |
|[Executar a consulta](run-query.md) <br/> |Execute a consulta operação fornece a capacidade de executar uma consulta no cubo com base em filtros, medidas e dimensões especificadas e retornar os dados de volta.  <br/> |
|[Limpar Cache](clear-cache.md) <br/> |Operação de Clear Cache exclui o cache no servidor para consultas e dados. Isso redefinirá o cache e abordaremos dados atualizados do cubo de QoE posteriormente para novas solicitações.  <br/> |
|[Obter o Log de integração](get-integration-log.md) <br/> |Obtenha a operação retorna uma lista de entradas de log descrevendo as atividades no cubo de QoE de processamento de Log de integração.  <br/> |
|[Obter dados de integração com o últimos](get-last-integration-data.md) <br/> |Obtenha os últimos dados de integração do cubo.  <br/> |
   
 **Suporte (CORS) API de dados de compartilhamento de recursos de entre origens**
  
API de dados oferece suporte a compartilhamento de recursos entre origens (CORS). CORS é um recurso HTTP que permite que um aplicativo da web em execução em um domínio para acessar recursos em outro domínio. Navegadores da Web implementam uma restrição de segurança conhecida como política de mesma origem da [Política de mesma origem](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impede que uma página da web de APIs de chamada em um domínio diferente. CORS fornece uma maneira segura para permitir que um domínio (o domínio de origem) para chamadas de APIs em outro domínio. Consulte a [especificação de CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre CORS.
  
 **Habilitando CORS para dados API**
  
 A seguir está um trecho de API de dados Web. config, mostrando dois domínios listados nas configurações do aplicativo corsTrustedOrigin. Todas as solicitações feitas pelos scripts carregados a partir desses servidores são confiáveis pelo API de dados.
  
Lembre-se de incluir o protocolo exato, nome do host e porta (se houver). Não para colocar qualquer um encaminhar barra invertida caractere (/) no final. Várias entradas podem ser especificadas separando-os com vírgulas.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


