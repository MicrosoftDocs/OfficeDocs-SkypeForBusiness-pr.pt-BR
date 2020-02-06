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
ms.openlocfilehash: a027cc7402bad7524343391f9bf7039dd077a46c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816690"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API do repositório para o painel de qualidade da chamada (CQD) no Skype for Business Server
 
**Resumo:** Saiba mais sobre a API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A API do repositório fornece acesso programático para o painel de qualidade de chamada para o Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API do repositório para o painel de qualidade da chamada

A API do repositório oferece uma interface de acesso a dados ao banco de dados do repositório. O repositório permite que o conteúdo seja organizado em uma árvore de árvore ou de gráfico de forma que os usuários possam agrupá-los das maneiras que fazem sentido para os usuários. O repositório oferece suporte a dois tipos gerais de usuários: usuário do sistema, que é um usuário interno que representa o repositório e usuários regulares que representam os usuários autorizados do repositório.
  
A API do repositório consiste em três serviços gerais: 
  
- [Serviço de usuário para CQD](user-service.md) -para acessar usuários.
    
- [Serviço de item para o painel de qualidade de chamada (CQD)](item-service.md) – para acessar itens e o conteúdo armazenado em itens.
    
- [Serviço de configurações do usuário para o painel de qualidade de chamada (CQD)](user-settings-service.md) -para acessar as configurações do usuário.
    
O painel de qualidade de chamada usa a API do repositório para gerenciar as seguintes informações: 
  
- **Usuário** – representação de usuários que têm acesso ao repositório.
    
- **Report** -contém uma lista de consultas, armazenadas como um conteúdo em itens do repositório.
    
- **Consulta** – usada para recuperar dados da API de dados, armazenadas como um conteúdo em itens do repositório.
    
- **Configuração do usuário** – descreve um comportamento de aplicativo opcional para o usuário.
    
  **Suporte ao compartilhamento de recursos entre origens (CORS) para a API do repositório**
  
A API do repositório tem suporte para o compartilhamento de recursos entre origens (CORS). O CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio. Os navegadores da Web implementam uma restrição de segurança conhecida como política [da mesma origem](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impede que uma página da Web chame APIs em um domínio diferente. O CORS fornece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio. Consulte a [especificação CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre o CORS.
  
 **Habilitando o CORS para a API do repositório**
  
 Veja a seguir um trecho da API do repositório Web. config, que mostra dois domínios listados em configurações do aplicativo corsTrustedOrigin. Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis para a API do repositório.
  
Lembre-se de incluir o protocolo exato, o nome do host e a porta (se houver). Não coloque nenhum caractere de barra (/) no final. Várias entradas podem ser especificadas separando-se com vírgulas.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


