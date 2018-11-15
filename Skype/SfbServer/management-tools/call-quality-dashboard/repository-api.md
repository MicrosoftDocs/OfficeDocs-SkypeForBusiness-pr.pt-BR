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
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530910"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API do repositório para o painel de qualidade de chamada (CQD) no Skype para Business Server
 
**Resumo:** Saiba mais sobre o API de repositório para o painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
A API do repositório fornece acesso programático para painel de controle de qualidade de chamada para Skype para Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API do repositório para o painel de controle de qualidade de chamada

API do repositório oferece uma interface de acesso de dados ao banco de dados de repositório. O repositório permite que o conteúdo a ser organizados em uma estrutura de árvore ou gráfico, de forma que os usuários podem agrupar das maneiras que fazem sentido para os usuários. O repositório suporta dois tipos gerais de usuários: usuário do sistema, o que é um usuário interno representando o repositório e usuários regulares que representam os usuários autorizados do repositório.
  
API do repositório consiste em três serviços gerais: 
  
- [Serviço de usuário para CQD](user-service.md) - para acessar os usuários.
    
- [Serviço de item para o painel de qualidade de chamada (CQD)](item-service.md) - para acessar os itens e o conteúdo armazenado em itens.
    
- [Serviço de configurações de usuário para o painel de qualidade de chamada (CQD)](user-settings-service.md) - para acessar as configurações do usuário.
    
Painel de controle de qualidade de chamada usa API de repositório para gerenciar as seguintes informações: 
  
- **Usuário** - representação dos usuários que têm acesso ao repositório.
    
- **Relatório** - contém uma lista de consultas, armazenado como um itens no repositório de conteúdo.
    
- **Consulta** - usado para recuperar dados da API de dados, armazenado como um itens no repositório de conteúdo.
    
- **Configuração do usuário** - descreve um comportamento de aplicativo opcional para o usuário.
    
  **Compartilhamento (CORS) suporte para API do repositório de recursos de entre origens**
  
API do repositório oferece suporte a compartilhamento de recursos entre origens (CORS). CORS é um recurso HTTP que permite que um aplicativo da web em execução em um domínio para acessar recursos em outro domínio. Navegadores da Web implementam uma restrição de segurança conhecida como política de mesma origem da [Política de mesma origem](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impede que uma página da web de APIs de chamada em um domínio diferente. CORS fornece uma maneira segura para permitir que um domínio (o domínio de origem) para chamadas de APIs em outro domínio. Consulte a [especificação de CORS](https://www.w3.org/TR/cors/) para obter detalhes sobre CORS.
  
 **Habilitando CORS para API do repositório**
  
 A seguir está um trecho de API do repositório Web. config, mostrando dois domínios listados nas configurações do aplicativo corsTrustedOrigin. Todas as solicitações feitas pelos scripts carregados a partir desses servidores são confiáveis pelo API de repositório.
  
Lembre-se de incluir o protocolo exato, nome do host e porta (se houver). Não para colocar qualquer um encaminhar barra invertida caractere (/) no final. Várias entradas podem ser especificadas separando-os com vírgulas.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


