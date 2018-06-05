---
title: Dados API para painel de controle de qualidade de chamada (CQD) no Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumo: Saiba mais sobre o API Rata para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: ccc9965af4766277978968b91321aefb5fdae3b9
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568860"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="ff664-104">Dados API para painel de controle de qualidade de chamada (CQD) no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ff664-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ff664-105">**Resumo:** Saiba mais sobre o API Rata para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="ff664-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="ff664-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ff664-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ff664-107">A API de dados fornece acesso programático para painel de controle de qualidade de chamada para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ff664-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="ff664-108">API de dados para o painel de controle de qualidade de chamada</span><span class="sxs-lookup"><span data-stu-id="ff664-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="ff664-109">A API de dados oferece uma interface de consulta ao cubo do QoE.</span><span class="sxs-lookup"><span data-stu-id="ff664-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="ff664-110">A API de dados é uma API REST para trabalhar com o banco de dados multidimensional que fornece agregadas métricas de QoE com base em filtros e dimensões especificadas.</span><span class="sxs-lookup"><span data-stu-id="ff664-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="ff664-111">As operações do REST estão incluídas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ff664-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="ff664-112">**Operação**</span><span class="sxs-lookup"><span data-stu-id="ff664-112">**Operation**</span></span>|<span data-ttu-id="ff664-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ff664-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ff664-114">Obtenha o cubo</span><span class="sxs-lookup"><span data-stu-id="ff664-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="ff664-115">Obter a lista de medidas e dimensões disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ff664-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="ff664-116">Obtenha os membros de dimensão</span><span class="sxs-lookup"><span data-stu-id="ff664-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="ff664-117">Operação de membros da dimensão Get retorna a lista de membros de uma dimensão específica.</span><span class="sxs-lookup"><span data-stu-id="ff664-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="ff664-118">Ele também dá a capacidade de filtrar a lista de membro e obtenha um subconjunto, para reduzir o custo de transferência de transmissão.</span><span class="sxs-lookup"><span data-stu-id="ff664-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="ff664-119">Executar a consulta</span><span class="sxs-lookup"><span data-stu-id="ff664-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="ff664-120">Execute a consulta operação fornece a capacidade de executar uma consulta no cubo com base em filtros, medidas e dimensões especificadas e retornar os dados de volta.</span><span class="sxs-lookup"><span data-stu-id="ff664-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="ff664-121">Limpar Cache</span><span class="sxs-lookup"><span data-stu-id="ff664-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="ff664-122">Operação de Clear Cache exclui o cache no servidor para consultas e dados.</span><span class="sxs-lookup"><span data-stu-id="ff664-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="ff664-123">Isso redefinirá o cache e abordaremos dados atualizados do cubo de QoE posteriormente para novas solicitações.</span><span class="sxs-lookup"><span data-stu-id="ff664-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="ff664-124">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="ff664-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="ff664-125">Obtenha a operação retorna uma lista de entradas de log descrevendo as atividades no cubo de QoE de processamento de Log de integração.</span><span class="sxs-lookup"><span data-stu-id="ff664-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="ff664-126">Obter dados de integração com o últimos</span><span class="sxs-lookup"><span data-stu-id="ff664-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="ff664-127">Obtenha os últimos dados de integração do cubo.</span><span class="sxs-lookup"><span data-stu-id="ff664-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="ff664-128">**Suporte (CORS) API de dados de compartilhamento de recursos de entre origens**</span><span class="sxs-lookup"><span data-stu-id="ff664-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="ff664-129">API de dados oferece suporte a compartilhamento de recursos entre origens (CORS).</span><span class="sxs-lookup"><span data-stu-id="ff664-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="ff664-130">CORS é um recurso HTTP que permite que um aplicativo da web em execução em um domínio para acessar recursos em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="ff664-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="ff664-131">Navegadores da Web implementam uma restrição de segurança conhecida como política de mesma origem da [Política de mesma origem](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impede que uma página da web de APIs de chamada em um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="ff664-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="ff664-132">CORS fornece uma maneira segura para permitir que um domínio (o domínio de origem) para chamadas de APIs em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="ff664-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="ff664-133">Consulte a [especificação de CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre CORS.</span><span class="sxs-lookup"><span data-stu-id="ff664-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="ff664-134">**Habilitando CORS para dados API**</span><span class="sxs-lookup"><span data-stu-id="ff664-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="ff664-135">A seguir está um trecho de API de dados Web. config, mostrando dois domínios listados nas configurações do aplicativo corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="ff664-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="ff664-136">Todas as solicitações feitas pelos scripts carregados a partir desses servidores são confiáveis pelo API de dados.</span><span class="sxs-lookup"><span data-stu-id="ff664-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="ff664-137">Lembre-se de incluir o protocolo exato, nome do host e porta (se houver).</span><span class="sxs-lookup"><span data-stu-id="ff664-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="ff664-138">Não para colocar qualquer um encaminhar barra invertida caractere (/) no final.</span><span class="sxs-lookup"><span data-stu-id="ff664-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="ff664-139">Várias entradas podem ser especificadas separando-os com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="ff664-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


