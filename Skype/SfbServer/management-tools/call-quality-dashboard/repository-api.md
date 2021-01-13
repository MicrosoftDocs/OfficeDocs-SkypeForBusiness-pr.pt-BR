---
title: REPOSITÓRIO API para Painel de Qualidade de Chamadas (CQD) no Skype for Business Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumo: Saiba mais sobre a API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803121"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="e0e4a-104">REPOSITÓRIO API para Painel de Qualidade de Chamadas (CQD) no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e0e4a-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="e0e4a-105">**Resumo:** Saiba mais sobre a API de repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e0e4a-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e0e4a-107">A API de Repositório fornece acesso programático para o Painel de Qualidade de Chamadas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="e0e4a-108">REPOSITÓRIO API para Painel de Qualidade de Chamada</span><span class="sxs-lookup"><span data-stu-id="e0e4a-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="e0e4a-109">A API de repositório oferece uma interface de acesso a dados para o banco de dados de repositório.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="e0e4a-110">O repositório permite que o conteúdo seja organizado em uma árvore ou estrutura de gráficos de forma que os usuários possam a groupá-los das maneiras que fazem sentido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="e0e4a-111">O repositório oferece suporte a dois tipos gerais de usuários: usuário do sistema, que é um usuário integrado que representa o repositório, e usuários regulares que representam os usuários autorizados do repositório.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="e0e4a-112">A API de repositório consiste em três serviços gerais:</span><span class="sxs-lookup"><span data-stu-id="e0e4a-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="e0e4a-113">[Serviço de Usuário para CQD](user-service.md) - para acessar Usuários.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="e0e4a-114">[Serviço de Item para Painel de Qualidade de Chamada (CQD)](item-service.md) - para acessar Itens e o conteúdo armazenado em Itens.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="e0e4a-115">[Serviço de Configurações do Usuário para o Painel de Qualidade da Chamada (CQD)](user-settings-service.md) - para acessar as Configurações do Usuário.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="e0e4a-116">O Painel de Qualidade da Chamada usa a API de Repositório para gerenciar as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="e0e4a-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="e0e4a-117">**Usuário** - representação de usuários que têm acesso ao repositório.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="e0e4a-118">**Relatório** – contém uma lista de consultas, armazenada como um conteúdo em itens de repositório.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="e0e4a-119">**Consulta -** usada para recuperar dados da API de Dados, armazenada como um conteúdo em itens de repositório.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="e0e4a-120">**Configuração do** Usuário - descreve um comportamento de aplicativo opcional para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="e0e4a-121">**Suporte ao CORS (Compartilhamento de Recursos entre Origens) para a API de Repositório**</span><span class="sxs-lookup"><span data-stu-id="e0e4a-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="e0e4a-122">A API do repositório dá suporte ao CORS (Compartilhamento de Recursos entre Origens).</span><span class="sxs-lookup"><span data-stu-id="e0e4a-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="e0e4a-123">CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="e0e4a-124">Os navegadores da Web [](https://www.w3.org/Security/wiki/Same_Origin_Policy) implementam uma restrição de segurança conhecida como política de mesma origem que impede que uma página da Web chamar APIs em um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="e0e4a-125">O CORS oferece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="e0e4a-126">Consulte a [especificação CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre CORS.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="e0e4a-127">**Habilitando o CORS para a API de Repositório**</span><span class="sxs-lookup"><span data-stu-id="e0e4a-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="e0e4a-128">Veja a seguir um trecho do repositório api web.config, mostrando dois domínios listados nas configurações de aplicativo corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="e0e4a-129">Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis para a API de Repositório.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="e0e4a-130">Lembre-se de incluir o protocolo exato, o nome do host e a porta (se algum).</span><span class="sxs-lookup"><span data-stu-id="e0e4a-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="e0e4a-131">Não coloque nenhum caractere de barra (/) no final.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="e0e4a-132">Várias entradas podem ser especificadas separando-as por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="e0e4a-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


