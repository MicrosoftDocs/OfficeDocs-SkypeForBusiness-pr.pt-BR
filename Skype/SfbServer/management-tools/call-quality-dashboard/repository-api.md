---
title: API do repositório para o painel de qualidade de chamada (CQD) no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumo: Saiba mais sobre o API de repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: de933063e5768b12af5ae8dc678ec7aa2da5f168
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035551"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="3dfe8-104">API do repositório para o painel de qualidade de chamada (CQD) no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3dfe8-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="3dfe8-105">**Resumo:** Saiba mais sobre o API de repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3dfe8-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="3dfe8-107">A API do repositório fornece acesso programático para painel de controle de qualidade de chamada para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="3dfe8-108">API do repositório para o painel de controle de qualidade de chamada</span><span class="sxs-lookup"><span data-stu-id="3dfe8-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="3dfe8-109">API do repositório oferece uma interface de acesso de dados ao banco de dados de repositório.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="3dfe8-110">O repositório permite que o conteúdo a ser organizados em uma estrutura de árvore ou gráfico, de forma que os usuários podem agrupar das maneiras que fazem sentido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="3dfe8-111">O repositório suporta dois tipos gerais de usuários: usuário do sistema, o que é um usuário interno representando o repositório e usuários regulares que representam os usuários autorizados do repositório.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="3dfe8-112">API do repositório consiste em três serviços gerais:</span><span class="sxs-lookup"><span data-stu-id="3dfe8-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="3dfe8-113">[Serviço de usuário para CQD](user-service.md) - para acessar os usuários.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="3dfe8-114">[Serviço de item para o painel de qualidade de chamada (CQD)](item-service.md) - para acessar os itens e o conteúdo armazenado em itens.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="3dfe8-115">[Serviço de configurações de usuário para o painel de qualidade de chamada (CQD)](user-settings-service.md) - para acessar as configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="3dfe8-116">Painel de controle de qualidade de chamada usa API de repositório para gerenciar as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3dfe8-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="3dfe8-117">**Usuário** - representação dos usuários que têm acesso ao repositório.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="3dfe8-118">**Relatório** - contém uma lista de consultas, armazenado como um itens no repositório de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="3dfe8-119">**Consulta** - usado para recuperar dados da API de dados, armazenado como um itens no repositório de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="3dfe8-120">**Configuração do usuário** - descreve um comportamento de aplicativo opcional para o usuário.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="3dfe8-121">**Compartilhamento (CORS) suporte para API do repositório de recursos de entre origens**</span><span class="sxs-lookup"><span data-stu-id="3dfe8-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="3dfe8-122">API do repositório oferece suporte a compartilhamento de recursos entre origens (CORS).</span><span class="sxs-lookup"><span data-stu-id="3dfe8-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="3dfe8-123">CORS é um recurso HTTP que permite que um aplicativo da web em execução em um domínio para acessar recursos em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="3dfe8-124">Navegadores da Web implementam uma restrição de segurança conhecida como política de mesma origem da [Política de mesma origem](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impede que uma página da web de APIs de chamada em um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="3dfe8-125">CORS fornece uma maneira segura para permitir que um domínio (o domínio de origem) para chamadas de APIs em outro domínio.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="3dfe8-126">Consulte a [especificação de CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre CORS.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="3dfe8-127">**Habilitando CORS para API do repositório**</span><span class="sxs-lookup"><span data-stu-id="3dfe8-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="3dfe8-128">A seguir está um trecho de API do repositório Web. config, mostrando dois domínios listados nas configurações do aplicativo corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="3dfe8-129">Todas as solicitações feitas pelos scripts carregados a partir desses servidores são confiáveis pelo API de repositório.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="3dfe8-130">Lembre-se de incluir o protocolo exato, nome do host e porta (se houver).</span><span class="sxs-lookup"><span data-stu-id="3dfe8-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="3dfe8-131">Não para colocar qualquer um encaminhar barra invertida caractere (/) no final.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="3dfe8-132">Várias entradas podem ser especificadas separando-os com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="3dfe8-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


