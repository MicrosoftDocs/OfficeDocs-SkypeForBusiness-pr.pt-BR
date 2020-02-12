---
title: API do repositório para o painel de qualidade da chamada (CQD) no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumo: Saiba mais sobre a API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 283ef7544435c3954898b2d5ae9e5f5b38762f3c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888780"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="1e3d2-104">API do repositório para o painel de qualidade da chamada (CQD) no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1e3d2-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="1e3d2-105">**Resumo:** Saiba mais sobre a API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1e3d2-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1e3d2-107">A API do repositório fornece acesso programático para o painel de qualidade de chamada para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="1e3d2-108">API do repositório para o painel de qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="1e3d2-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="1e3d2-109">A API do repositório oferece uma interface de acesso a dados ao banco de dados do repositório.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="1e3d2-110">O repositório permite que o conteúdo seja organizado em uma árvore de árvore ou de gráfico de forma que os usuários possam agrupá-los das maneiras que fazem sentido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="1e3d2-111">O repositório oferece suporte a dois tipos gerais de usuários: usuário do sistema, que é um usuário interno que representa o repositório e usuários regulares que representam os usuários autorizados do repositório.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="1e3d2-112">A API do repositório consiste em três serviços gerais:</span><span class="sxs-lookup"><span data-stu-id="1e3d2-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="1e3d2-113">[Serviço de usuário para CQD](user-service.md) -para acessar usuários.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="1e3d2-114">[Serviço de item para o painel de qualidade de chamada (CQD)](item-service.md) – para acessar itens e o conteúdo armazenado em itens.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="1e3d2-115">[Serviço de configurações do usuário para o painel de qualidade de chamada (CQD)](user-settings-service.md) -para acessar as configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="1e3d2-116">O painel de qualidade de chamada usa a API do repositório para gerenciar as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1e3d2-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="1e3d2-117">**Usuário** – representação de usuários que têm acesso ao repositório.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="1e3d2-118">**Report** -contém uma lista de consultas, armazenadas como um conteúdo em itens do repositório.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="1e3d2-119">**Consulta** – usada para recuperar dados da API de dados, armazenadas como um conteúdo em itens do repositório.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="1e3d2-120">**Configuração do usuário** – descreve um comportamento de aplicativo opcional para o usuário.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="1e3d2-121">**Suporte ao compartilhamento de recursos entre origens (CORS) para a API do repositório**</span><span class="sxs-lookup"><span data-stu-id="1e3d2-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="1e3d2-122">A API do repositório tem suporte para o compartilhamento de recursos entre origens (CORS).</span><span class="sxs-lookup"><span data-stu-id="1e3d2-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="1e3d2-123">O CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="1e3d2-124">Os navegadores da Web implementam uma restrição de segurança conhecida como política [da mesma origem](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impede que uma página da Web chame APIs em um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="1e3d2-125">O CORS fornece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="1e3d2-126">Consulte a [especificação CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre o CORS.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="1e3d2-127">**Habilitando o CORS para a API do repositório**</span><span class="sxs-lookup"><span data-stu-id="1e3d2-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="1e3d2-128">Veja a seguir um trecho da API do repositório Web. config, que mostra dois domínios listados em configurações do aplicativo corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="1e3d2-129">Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis para a API do repositório.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="1e3d2-130">Lembre-se de incluir o protocolo exato, o nome do host e a porta (se houver).</span><span class="sxs-lookup"><span data-stu-id="1e3d2-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="1e3d2-131">Não coloque nenhum caractere de barra (/) no final.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="1e3d2-132">Várias entradas podem ser especificadas separando-se com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="1e3d2-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


