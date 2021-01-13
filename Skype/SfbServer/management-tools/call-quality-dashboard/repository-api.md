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
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>REPOSITÓRIO API para Painel de Qualidade de Chamadas (CQD) no Skype for Business Server
 
**Resumo:** Saiba mais sobre a API de repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A API de Repositório fornece acesso programático para o Painel de Qualidade de Chamadas do Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>REPOSITÓRIO API para Painel de Qualidade de Chamada

A API de repositório oferece uma interface de acesso a dados para o banco de dados de repositório. O repositório permite que o conteúdo seja organizado em uma árvore ou estrutura de gráficos de forma que os usuários possam a groupá-los das maneiras que fazem sentido para os usuários. O repositório oferece suporte a dois tipos gerais de usuários: usuário do sistema, que é um usuário integrado que representa o repositório, e usuários regulares que representam os usuários autorizados do repositório.
  
A API de repositório consiste em três serviços gerais: 
  
- [Serviço de Usuário para CQD](user-service.md) - para acessar Usuários.
    
- [Serviço de Item para Painel de Qualidade de Chamada (CQD)](item-service.md) - para acessar Itens e o conteúdo armazenado em Itens.
    
- [Serviço de Configurações do Usuário para o Painel de Qualidade da Chamada (CQD)](user-settings-service.md) - para acessar as Configurações do Usuário.
    
O Painel de Qualidade da Chamada usa a API de Repositório para gerenciar as seguintes informações: 
  
- **Usuário** - representação de usuários que têm acesso ao repositório.
    
- **Relatório** – contém uma lista de consultas, armazenada como um conteúdo em itens de repositório.
    
- **Consulta -** usada para recuperar dados da API de Dados, armazenada como um conteúdo em itens de repositório.
    
- **Configuração do** Usuário - descreve um comportamento de aplicativo opcional para o usuário.
    
  **Suporte ao CORS (Compartilhamento de Recursos entre Origens) para a API de Repositório**
  
A API do repositório dá suporte ao CORS (Compartilhamento de Recursos entre Origens). CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio. Os navegadores da Web [](https://www.w3.org/Security/wiki/Same_Origin_Policy) implementam uma restrição de segurança conhecida como política de mesma origem que impede que uma página da Web chamar APIs em um domínio diferente. O CORS oferece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio. Consulte a [especificação CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre CORS.
  
 **Habilitando o CORS para a API de Repositório**
  
 Veja a seguir um trecho do repositório api web.config, mostrando dois domínios listados nas configurações de aplicativo corsTrustedOrigin. Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis para a API de Repositório.
  
Lembre-se de incluir o protocolo exato, o nome do host e a porta (se algum). Não coloque nenhum caractere de barra (/) no final. Várias entradas podem ser especificadas separando-as por vírgulas.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


