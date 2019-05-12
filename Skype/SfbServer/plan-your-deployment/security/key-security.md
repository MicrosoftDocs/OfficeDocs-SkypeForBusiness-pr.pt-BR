---
title: Recursos de segurança de chave no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype para Business Server inclui vários recursos de segurança, incluindo o armazenamento de dados de configuração centralizado, controle de acesso baseado em função e autenticação de servidor-para-servidor.
ms.openlocfilehash: 566090b27e22468e61112a0e81ad29a23dc6ae2e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897426"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Recursos de segurança de chave no Skype para Business Server
 
Skype para Business Server inclui vários recursos de segurança, incluindo o armazenamento de dados de configuração centralizado, controle de acesso baseado em função e autenticação de servidor-para-servidor. 
  
Este artigo fornece uma visão geral de alto nível dos Skype para Business Server security. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Recursos de segurança de chave no Skype para Business Server

Segurança é um tópico bastante amplo. Segurança atinge entre todos os recursos do Skype para Business Server, bem como bancos de dados, serviços e hardware que compõem um Skype para ecossistema de Business Server. Este artigo destaca alguns dos recursos do Skype para Business Server especificamente projetadas para segurança.
  
### <a name="planning-and-design-tools"></a>Ferramentas de Planejamento e Design

Skype para Business Server fornece duas ferramentas para facilitar o planejamento e projeto e para reduzir a chance de forma incorreta Configurando Skype para componentes de servidor de negócios. 
  
- **Ferramenta de planejamento de topologia** automatiza grande parte do processo de design de topologia. Você pode exportar os resultados da ferramenta de planejamento para o construtor de topologias, o que é a ferramenta que é necessário para instalar cada servidor que executa o Skype para Business Server.
    
- **O Construtor de Topologias** armazena todas as informações de configuração no repositório de Gerenciamento Central.
    
Para obter detalhes sobre essas ferramentas, consulte [Skype para ferramentas de gerenciamento de servidor de negócios](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Repositório de Gerenciamento Central

Skype para Business Server, dados de configuração sobre os servidores e serviços faz parte do repositório de gerenciamento Central. Repositório de gerenciamento Central fornece um armazenamento robusto e esquematizado dos dados necessários para definir, configurar, manter, administrar, descrevem e operar uma Skype para implantação de servidor de negócios. Ele também valida os dados para assegurar a consistência da configuração. Todas as alterações a esses dados de configuração ocorrem no repositório de gerenciamento Central, eliminando problemas de "fora de sincronia". 
  
Cópias somente leitura dos dados são replicadas para todos os servidores na topologia, incluindo Servidores de borda e Aparelhos de Filial Persistente. A replicação é gerenciada por um serviço que, por definição, é executado sob um contexto de serviço de rede, fazendo com que os direitos e permissões sejam reduzidos aos de um usuário comum do computador. 
  
### <a name="server-to-server-authentication"></a>Autenticação Servidor para Servidor

No Skype para Business Server, a autenticação pode ser configurada entre servidores, usando o protocolo de autorização aberta (OAuth). Por exemplo, você pode configurar Skype para Business Server autenticar com um servidor que está executando o Microsoft Exchange Server 2016. Usando o protocolo OAuth, o Skype para Business Server e o Microsoft Exchange Server pode confiar umas às outras. Isso possibilita a integração perfeita dos produtos. Para obter detalhes, consulte [gerenciar autenticação de servidor-para-servidor (OAuth) e aplicativos de parceiros no Skype para Business Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Gerenciamento baseado no Windows PowerShell e Interface de Gerenciamento baseada na Web

Skype para Business Server oferece uma interface de gerenciamento poderoso, baseada na interface de linha de comando do Windows PowerShell. Inclui cmdlets para gerenciamento de segurança e recursos de segurança do Windows Power Shell padrão, habilitados para que os usuários não executem scripts inadvertidamente. Isso significa que os padrões do software são definidos automaticamente para maximizar a segurança e reduzir possíveis ataques. Para obter detalhes sobre o suporte de gerenciamento do Windows PowerShell no Skype para Business Server, consulte [Skype do Shell de gerenciamento do servidor de negócios](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Controle de Acesso Baseado em Função (RBAC)

Skype para Business Server fornece o controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança. Você pode usar o RBAC para siga o princípio de "privilégio mínimo," em quais usuários recebem apenas os direitos administrativos que exigem seus trabalhos. Skype para Business Server fornece a capacidade de criar uma nova função e também a capacidade de modificar uma função existente. 
  
## <a name="network-address-translation-nat"></a>Conversão de Endereço de Rede (NAT)

Skype para Business Server não suporta o uso de conversão de endereço de rede (NAT) na interface interna do servidor de borda, mas ele oferece suporte para colocar a interface externa do serviço de borda de acesso, serviço de borda de webconferência e uma / serviço de borda V por trás de um roteador ou firewall que realiza a conversão de endereço de rede (NAT) para única ou escalonável consolidados topologias de servidor de borda. Múltiplos Servidores de Borda ocultos sob um balanceador de carga de hardware não podem usar o NAT. O balanceador de carga do DNS (Domain Name System) é obrigatório se múltiplos Servidores de Borda usarem o NAT em suas interfaces externas. Por sua vez, o uso do balanceador de carga do DNS permite reduzir o número de endereços de IP públicos por Servidor de Borda em um pool de Servidores de Borda. Para obter detalhes, consulte [os cenários de servidor de borda no Skype para Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Se você federa com empresas em uma implantação da Microsoft Office Communications Server 2007 e precisa usar áudio/vídeo entre a sua empresa e a empresa federada, os requisitos de porta serão os da versão antiga do Servidor de Borda implantado. Por exemplo, os intervalos de porta necessários para aqueles mais antigos versões devem ser abertas para ambas as empresas até que o parceiro federado atualize seus servidores de borda para Skype para Business Server. Neste momento, os requisitos de porta poderão ser revistos e reduzidos de acordo com a nova configuração. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Simplificar Certificados para Servidores de Borda

O Assistente de Implantação preenche nomes de identidade (SNs) e nomes de identidade alternativos (SANs) automaticamente, reduzindo possíveis inclusões desnecessárias e entradas potencialmente não seguras.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de Vida do Desenvolvimento da Segurança de Computação Confiável (SDL)

Skype para Business Server é projetado e desenvolvido em conformidade com o [Microsoft Trustworthy Computing Security Development Lifecycle](https://go.microsoft.com/fwlink/p/?linkid=68761) (SDL).
  
- **Confiável por Design** A primeira etapa na criação de um sistema de comunicação unificado mais seguro era criar modelos de risco e testar cada recurso, como ele foi criado. Além disso, a Microsoft executa testes de comportamento fora do esperado para encontrar vulnerabilidades na segurança resultantes de atitudes inesperadas do projeto. Os múltiplos aperfeiçoamentos relacionados à segurança foram criados dentro do código de processos e práticas. As ferramentas de construção em tempo detectam invasões de buffer e outras potenciais ameaças antes do código ser checado no produto final. Claro, é impossível detectar todas as ameaças de segurança desconhecidas. Nenhum sistema pode garantir segurança completa. No entanto, porque o desenvolvimento do produto abraçou os princípios de design seguro desde o início, Skype para Business Server incorpora tecnologias de segurança padrão do setor como parte fundamental de sua arquitetura.
    
- **Confiável por padrão** Por padrão, as comunicações de rede do Skype para Business Server são criptografadas. Como todos os servidores usam certificados e autenticação Kerberos, TLS, Secure Real-time Transport Protocol (SRTP) e outras técnicas de criptografia padrão da indústria, incluindo a criptografia padrão de criptografia avançada (AES) de 128 bits, praticamente todas as Skype para Dados do servidor de negócios são protegidos na rede. Além disso, o controle de acesso baseado em função torna possível implantar servidores que executam o Skype para Business Server para que cada função de servidor é executado apenas os serviços e tem apenas as permissões relacionadas a esses serviços, que são apropriados para a função de servidor.
    
- **Confiável por implantação** Todos os Skype para documentação Business Server inclui práticas recomendadas e recomendações para ajudá-lo a determinar e configurar os níveis de segurança ideal para sua implantação e avaliar os riscos de segurança de ativação de opções de não-padrão.
    

