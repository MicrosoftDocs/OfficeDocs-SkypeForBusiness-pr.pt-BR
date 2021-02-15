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
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="272bc-104">API de Dados para Painel de Qualidade de Chamadas (CQD) no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="272bc-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="272bc-105">**Resumo:** Saiba mais sobre a API de Dados para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="272bc-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="272bc-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="272bc-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="272bc-107">A API de Dados fornece acesso programático para o Painel de Qualidade de Chamadas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="272bc-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="272bc-108">API de Dados para Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="272bc-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="272bc-109">A API de Dados oferece uma interface de consulta para o cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="272bc-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="272bc-110">A API de Dados é uma API REST para trabalhar com banco de dados multidimensional que fornece métricas de QoE agregadas com base em dimensões e filtros especificados.</span><span class="sxs-lookup"><span data-stu-id="272bc-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="272bc-111">As operações REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="272bc-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="272bc-112">**Operação**</span><span class="sxs-lookup"><span data-stu-id="272bc-112">**Operation**</span></span>|<span data-ttu-id="272bc-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="272bc-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="272bc-114">Obter o cubo</span><span class="sxs-lookup"><span data-stu-id="272bc-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="272bc-115">Obter a lista de dimensões e medidas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="272bc-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="272bc-116">Obtenha os Membros da Dimensão</span><span class="sxs-lookup"><span data-stu-id="272bc-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="272bc-117">A operação Obter Membros da Dimensão retorna a lista de membros de uma dimensão específica.</span><span class="sxs-lookup"><span data-stu-id="272bc-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="272bc-118">Ele também dá a capacidade de filtrar a lista de membros e obter um subconjunto, para reduzir o custo de transferência eletrônica.</span><span class="sxs-lookup"><span data-stu-id="272bc-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="272bc-119">Executar Consulta</span><span class="sxs-lookup"><span data-stu-id="272bc-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="272bc-120">A operação Executar Consulta oferece a capacidade de executar uma consulta no cubo com base em dimensões, medições e filtros especificados e retornar os dados.</span><span class="sxs-lookup"><span data-stu-id="272bc-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="272bc-121">Limpar Cache</span><span class="sxs-lookup"><span data-stu-id="272bc-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="272bc-122">A operação Limpar Cache exclui o cache no servidor para consultas e dados.</span><span class="sxs-lookup"><span data-stu-id="272bc-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="272bc-123">Isso redefini o cache e obteremos dados atualizados do Cubo QoE posteriormente para novas solicitações.</span><span class="sxs-lookup"><span data-stu-id="272bc-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="272bc-124">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="272bc-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="272bc-125">A operação Obter Log de Integração retorna uma lista de entradas de log que descrevem as atividades no processamento do cubo de QoE.</span><span class="sxs-lookup"><span data-stu-id="272bc-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="272bc-126">Obter Últimos Dados de Integração</span><span class="sxs-lookup"><span data-stu-id="272bc-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="272bc-127">Obter os últimos dados de integração do cubo.</span><span class="sxs-lookup"><span data-stu-id="272bc-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="272bc-128">**Suporte ao CORS (Compartilhamento de Recursos entre Origens) para API de Dados**</span><span class="sxs-lookup"><span data-stu-id="272bc-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="272bc-129">A API de Dados dá suporte ao CORS (Compartilhamento de Recursos entre Origens).</span><span class="sxs-lookup"><span data-stu-id="272bc-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="272bc-130">CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="272bc-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="272bc-131">Os navegadores da Web [](https://www.w3.org/Security/wiki/Same_Origin_Policy) implementam uma restrição de segurança conhecida como política de mesma origem que impede que uma página da Web chamar APIs em um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="272bc-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="272bc-132">O CORS oferece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="272bc-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="272bc-133">Consulte a [especificação CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre CORS.</span><span class="sxs-lookup"><span data-stu-id="272bc-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="272bc-134">**Habilitando CORS para API de Dados**</span><span class="sxs-lookup"><span data-stu-id="272bc-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="272bc-135">Veja a seguir um trecho da API de dados web.config, mostrando dois domínios listados nas configurações do aplicativo corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="272bc-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="272bc-136">Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis para a API de Dados.</span><span class="sxs-lookup"><span data-stu-id="272bc-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="272bc-137">Lembre-se de incluir o protocolo exato, o nome do host e a porta (se algum).</span><span class="sxs-lookup"><span data-stu-id="272bc-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="272bc-138">Não coloque nenhum caractere de barra (/) no final.</span><span class="sxs-lookup"><span data-stu-id="272bc-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="272bc-139">Várias entradas podem ser especificadas separando-as por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="272bc-139">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


