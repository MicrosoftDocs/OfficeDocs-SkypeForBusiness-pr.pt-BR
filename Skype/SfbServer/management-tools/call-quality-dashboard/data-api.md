---
title: API de dados para o painel de qualidade de chamada (CQD) no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumo: Saiba mais sobre a API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "36571915"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="edeb7-104">API de dados para o painel de qualidade de chamada (CQD) no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="edeb7-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="edeb7-105">**Resumo:** Saiba mais sobre a API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="edeb7-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="edeb7-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="edeb7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="edeb7-107">A API de dados fornece acesso programático para o painel de qualidade de chamada para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="edeb7-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="edeb7-108">API de dados para o painel de qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="edeb7-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="edeb7-109">A API de dados oferece uma interface de consulta para o cubo de QoE.</span><span class="sxs-lookup"><span data-stu-id="edeb7-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="edeb7-110">A API de dados é uma API REST para trabalhar com um banco de dados multidimensional que fornece métricas de QoE agregadas com base em dimensões e filtros especificados.</span><span class="sxs-lookup"><span data-stu-id="edeb7-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="edeb7-111">As operações REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="edeb7-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="edeb7-112">**Operação**</span><span class="sxs-lookup"><span data-stu-id="edeb7-112">**Operation**</span></span>|<span data-ttu-id="edeb7-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="edeb7-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="edeb7-114">Obter o cubo</span><span class="sxs-lookup"><span data-stu-id="edeb7-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="edeb7-115">Obter a lista de dimensões e medidas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="edeb7-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="edeb7-116">Obtenha os Membros da Dimensão</span><span class="sxs-lookup"><span data-stu-id="edeb7-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="edeb7-117">A operação obter membros da dimensão retorna a lista de membros de uma dimensão específica.</span><span class="sxs-lookup"><span data-stu-id="edeb7-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="edeb7-118">Ele também permite filtrar a lista de membros e obter um subconjunto para reduzir o custo de transferência de fio.</span><span class="sxs-lookup"><span data-stu-id="edeb7-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="edeb7-119">Executar Consulta</span><span class="sxs-lookup"><span data-stu-id="edeb7-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="edeb7-120">Executar a operação de consulta fornece a capacidade de executar uma consulta no cubo com base em dimensões, medidas e filtros especificados e retornar os dados.</span><span class="sxs-lookup"><span data-stu-id="edeb7-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="edeb7-121">Limpar Cache</span><span class="sxs-lookup"><span data-stu-id="edeb7-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="edeb7-122">Limpar operação de cache exclui o cache no servidor para consultas e dados.</span><span class="sxs-lookup"><span data-stu-id="edeb7-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="edeb7-123">Isso redefinirá o cache e obteremos dados atualizados do cubo de QoE posteriormente para novas solicitações.</span><span class="sxs-lookup"><span data-stu-id="edeb7-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="edeb7-124">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="edeb7-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="edeb7-125">A operação obter log de integração retorna uma lista de entradas de log que descrevem as atividades em processamento de cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="edeb7-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="edeb7-126">Obter Últimos Dados de Integração</span><span class="sxs-lookup"><span data-stu-id="edeb7-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="edeb7-127">Obter os últimos dados de integração do cubo.</span><span class="sxs-lookup"><span data-stu-id="edeb7-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="edeb7-128">**Suporte ao compartilhamento de recursos entre origens (CORS) para a API de dados**</span><span class="sxs-lookup"><span data-stu-id="edeb7-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="edeb7-129">A API de dados dá suporte ao compartilhamento de recursos entre origens (CORS).</span><span class="sxs-lookup"><span data-stu-id="edeb7-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="edeb7-130">O CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="edeb7-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="edeb7-131">Os navegadores da Web implementam uma restrição de segurança conhecida como política [da mesma origem](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impede que uma página da Web chame APIs em um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="edeb7-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="edeb7-132">O CORS fornece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="edeb7-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="edeb7-133">Consulte a [especificação CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre o CORS.</span><span class="sxs-lookup"><span data-stu-id="edeb7-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="edeb7-134">**Habilitando o CORS para a API de dados**</span><span class="sxs-lookup"><span data-stu-id="edeb7-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="edeb7-135">Veja a seguir um trecho do Web API Web. config, mostrando dois domínios listados em configurações do aplicativo corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="edeb7-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="edeb7-136">Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis para a API de dados.</span><span class="sxs-lookup"><span data-stu-id="edeb7-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="edeb7-137">Lembre-se de incluir o protocolo exato, o nome do host e a porta (se houver).</span><span class="sxs-lookup"><span data-stu-id="edeb7-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="edeb7-138">Não coloque nenhum caractere de barra (/) no final.</span><span class="sxs-lookup"><span data-stu-id="edeb7-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="edeb7-139">Várias entradas podem ser especificadas separando-se com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="edeb7-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


