---
title: Principais recursos de segurança no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: O Skype for Business Server inclui vários recursos de segurança, incluindo autenticação de servidor para servidor, controle de acesso baseado em função e armazenamento centralizado de dados de configuração.
ms.openlocfilehash: cd86d1ac404cd2fe487f6f9369cc73df0d72c52f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296886"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Principais recursos de segurança no Skype for Business Server
 
O Skype for Business Server inclui vários recursos de segurança, incluindo autenticação de servidor para servidor, controle de acesso baseado em função e armazenamento centralizado de dados de configuração. 
  
Este artigo fornece uma visão geral de alto nível da segurança do Skype for Business Server. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Principais recursos de segurança no Skype for Business Server

Segurança é um tópico bastante amplo. A segurança é feita entre todos os recursos do Skype for Business Server, além de bancos de dados, serviços e hardware que compõem um ecossistema do Skype for Business Server. Este artigo descreve alguns dos recursos do Skype for Business Server em particular, projetados para segurança.
  
### <a name="planning-and-design-tools"></a>Ferramentas de Planejamento e Design

O Skype for Business Server fornece duas ferramentas para facilitar o planejamento e o design e reduzir a chance de configuração do Skype for Business Server. 
  
- A **ferramenta de planejamento de topologia** automatiza grande parte do processo de design da topologia. Você pode exportar os resultados da ferramenta de planejamento para o construtor de topologias, que é a ferramenta necessária para instalar cada servidor que está executando o Skype for Business Server.
    
- **O Construtor de Topologias** armazena todas as informações de configuração no repositório de Gerenciamento Central.
    
Para obter detalhes sobre essas ferramentas, consulte [ferramentas de gerenciamento do Skype for Business Server](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Repositório de Gerenciamento Central

No Skype for Business Server, os dados de configuração sobre servidores e serviços fazem parte do repositório de gerenciamento central. O repositório de gerenciamento central fornece um armazenamento robusto e schematized dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Skype for Business Server. Ele também valida os dados para assegurar a consistência da configuração. Todas as alterações a esses dados de configuração acontecem no repositório de gerenciamento central, eliminando problemas de "out-of-sync". 
  
Cópias somente leitura dos dados são replicadas para todos os servidores na topologia, incluindo Servidores de borda e Aparelhos de Filial Persistente. A replicação é gerenciada por um serviço que, por definição, é executado sob um contexto de serviço de rede, fazendo com que os direitos e permissões sejam reduzidos aos de um usuário comum do computador. 
  
### <a name="server-to-server-authentication"></a>Autenticação Servidor para Servidor

No Skype for Business Server, a autenticação pode ser configurada entre servidores usando o protocolo OAuth (autorização aberta). Por exemplo, você pode configurar o Skype for Business Server para se autenticar com um servidor que esteja executando o Microsoft Exchange Server 2016. Usando o protocolo OAuth, o servidor do Skype for Business e o Microsoft Exchange Server podem confiar uns com os outros. Isso possibilita a integração perfeita dos produtos. Para obter detalhes, consulte [gerenciar a autenticação de servidor para servidor (OAuth) e os aplicativos de parceiros no Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Gerenciamento baseado no Windows PowerShell e Interface de Gerenciamento baseada na Web

O Skype for Business Server oferece uma interface de gerenciamento poderosa, baseada na interface de linha de comando do Windows PowerShell. Inclui cmdlets para gerenciamento de segurança e recursos de segurança do Windows Power Shell padrão, habilitados para que os usuários não executem scripts inadvertidamente. Isso significa que os padrões do software são definidos automaticamente para maximizar a segurança e reduzir possíveis ataques. Para obter detalhes sobre o suporte ao gerenciamento do Windows PowerShell no Skype for Business Server, consulte [Shell de gerenciamento do Skype for Business Server](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Controle de Acesso Baseado em Função (RBAC)

O Skype for Business Server fornece controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança. Você pode usar o RBAC para acompanhar o princípio de "privilégio mínimo", em que os usuários recebem somente os direitos administrativos que seus trabalhos exigem. O Skype for Business Server oferece a capacidade de criar uma nova função e também a capacidade de modificar uma função existente. 
  
## <a name="network-address-translation-nat"></a>Conversão de Endereço de Rede (NAT)

O Skype for Business Server não oferece suporte ao uso de NAT (conversão de endereços de rede) na interface interna do servidor de borda, mas suporta colocar a interface externa do serviço de borda de acesso, serviço de borda de Webconferência e serviço de borda A/V atrás de um roteador ou firewall que executa a NAT (conversão de endereços de rede) para topologias de servidor de borda consolidadas simples e em escala. Múltiplos Servidores de Borda ocultos sob um balanceador de carga de hardware não podem usar o NAT. O balanceador de carga do DNS (Domain Name System) é obrigatório se múltiplos Servidores de Borda usarem o NAT em suas interfaces externas. Por sua vez, o uso do balanceador de carga do DNS permite reduzir o número de endereços de IP públicos por Servidor de Borda em um pool de Servidores de Borda. Para obter detalhes, consulte [cenários do servidor de borda no Skype for Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Se você federa com empresas em uma implantação da Microsoft Office Communications Server 2007 e precisa usar áudio/vídeo entre a sua empresa e a empresa federada, os requisitos de porta serão os da versão antiga do Servidor de Borda implantado. Por exemplo, os intervalos de porta necessários para essas versões mais antigas devem ser abertos para ambas as empresas até que o parceiro federado atualize seus servidores de borda para o Skype for Business Server. Neste momento, os requisitos de porta poderão ser revistos e reduzidos de acordo com a nova configuração. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Simplificar Certificados para Servidores de Borda

O Assistente de Implantação preenche nomes de identidade (SNs) e nomes de identidade alternativos (SANs) automaticamente, reduzindo possíveis inclusões desnecessárias e entradas potencialmente não seguras.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de Vida do Desenvolvimento da Segurança de Computação Confiável (SDL)

O Skype for Business Server foi projetado e desenvolvido em conformidade com o SDL ( [Security Development Lifecycle) da computação confiável da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=68761) .
  
- **Confiável por design** A primeira etapa na criação de um sistema de comunicação unificada mais seguro era criar modelos de ameaças e testar cada recurso como foi projetado. Além disso, a Microsoft executa testes de comportamento fora do esperado para encontrar vulnerabilidades na segurança resultantes de atitudes inesperadas do projeto. Os múltiplos aperfeiçoamentos relacionados à segurança foram criados dentro do código de processos e práticas. As ferramentas de construção em tempo detectam invasões de buffer e outras potenciais ameaças antes do código ser checado no produto final. Claro, é impossível detectar todas as ameaças de segurança desconhecidas. Nenhum sistema pode garantir segurança completa. No entanto, como o desenvolvimento de produto adotou princípios de design seguro desde o início, o Skype for Business Server incorpora tecnologias de segurança padrão do setor como parte fundamental de sua arquitetura.
    
- **Confiável por padrão** Por padrão, as comunicações de rede no Skype for Business Server são criptografadas. Como todos os servidores usam certificados e autenticação Kerberos, TLS, SSTP (protocolo de transporte em tempo real seguro) e outras técnicas de criptografia padrão do setor, incluindo criptografia AES (padrão de criptografia avançada) de 128 bits, praticamente todos os Skype para Os dados do Business Server estão protegidos na rede. Além disso, o controle de acesso baseado em função torna possível implantar servidores que executam o Skype for Business Server, para que cada função de servidor execute somente os serviços e tenha apenas as permissões relacionadas a esses serviços, que sejam apropriados para a função de servidor.
    
- **Confiável para implantação** Toda a documentação do Skype for Business Server inclui práticas recomendadas e recomendações para ajudá-lo a determinar e configurar os níveis de segurança ideais para a sua implantação e avaliar os riscos de segurança da ativação de opções não padrão.
    

