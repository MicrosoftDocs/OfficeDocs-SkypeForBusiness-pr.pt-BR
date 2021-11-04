---
title: API de repositório para CQD (Painel de Qualidade de Chamada) no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumo: saiba mais sobre a API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 21765c4766e7fc729988f2b8ba23241175a96584
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759693"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de repositório para CQD (Painel de Qualidade de Chamada) no Skype for Business Server
 
**Resumo:** Saiba mais sobre a API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A API repositório fornece acesso programático para o Painel de Qualidade de Chamada para Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API de repositório para Painel de Qualidade de Chamada

A API de repositório oferece uma interface de acesso a dados para o banco de dados do repositório. O repositório permite que o conteúdo seja organizado em uma estrutura de árvore ou gráfico para que os usuários possam agrupar-los de maneiras que façam sentido para os usuários. O repositório dá suporte a dois tipos gerais de usuários: o usuário do sistema, que é um usuário integrado que representa o repositório, e os usuários regulares que representam os usuários autorizados do repositório.
  
A API de repositório consiste em três serviços gerais: 
  
- [Serviço de Usuário para CQD](user-service.md) - para acessar Usuários.
    
- Serviço de Item para Painel de Qualidade [de Chamada (CQD)](item-service.md) - para acessar Itens e o conteúdo armazenado em Itens.
    
- [User Configurações Service for Call Quality Dashboard (CQD)](user-settings-service.md) - para acessar o Usuário Configurações.
    
O Painel de Qualidade de Chamada usa a API do Repositório para gerenciar as seguintes informações: 
  
- **User** - representação de Usuários que têm acesso ao repositório.
    
- **Relatório** - contém uma lista de consultas, armazenada como um conteúdo em itens de repositório.
    
- **Consulta** - usada para recuperar dados da API de Dados, armazenada como um conteúdo em itens de repositório.
    
- **Configuração do** Usuário - descreve um comportamento de aplicativo opcional para o usuário.
    
  **Suporte a CORS (Compartilhamento de Recursos entre Origens) para API de Repositório**
  
A API do Repositório dá suporte ao CORS (Compartilhamento de Recursos entre Origens). O CORS é um recurso HTTP que permite que um aplicativo Web em execução em um domínio acesse recursos em outro domínio. Os navegadores da Web [](https://www.w3.org/Security/wiki/Same_Origin_Policy) implementam uma restrição de segurança conhecida como política de mesma origem da Política de Mesma Origem que impede uma página da Web de chamar APIs em um domínio diferente. O CORS fornece uma maneira segura de permitir que um domínio (o domínio de origem) chame APIs em outro domínio. Consulte a [especificação do CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre o CORS.
  
 **Habilitando o CORS para API de Repositório**
  
 Veja a seguir um trecho da API de repositório web.config, mostrando dois domínios listados nas configurações do aplicativo corsTrustedOrigin. Todas as solicitações feitas pelos scripts carregados desses servidores são confiáveis pela API do Repositório.
  
Lembre-se de incluir o protocolo exato, o nome do host e a porta (se for o caso). Não coloque nenhum caractere de barra para frente (/) no final. Várias entradas podem ser especificadas separando-se com vírgulas.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


