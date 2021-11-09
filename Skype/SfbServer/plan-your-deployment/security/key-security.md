---
title: Principais recursos de segurança no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Server inclui vários recursos de segurança, incluindo autenticação de servidor para servidor, controle de acesso baseado em função e armazenamento centralizado de dados de configuração.
ms.openlocfilehash: c70d997dc29166b05376bbd6c1bcd7886d1c176b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848384"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Principais recursos de segurança no Skype for Business Server
 
Skype for Business Server inclui vários recursos de segurança, incluindo autenticação de servidor para servidor, controle de acesso baseado em função e armazenamento centralizado de dados de configuração. 
  
Este artigo fornece uma visão geral de alto nível da Skype for Business Server segurança. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Principais recursos de segurança no Skype for Business Server

Segurança é um tópico muito amplo. A segurança atinge todos os recursos de Skype for Business Server, bem como bancos de dados, serviços e hardware que comem um Skype for Business Server ecossistema. Este artigo descreve alguns dos recursos em Skype for Business Server em particular que são projetados para segurança.
  
### <a name="planning-and-design-tools"></a>Ferramentas de planejamento e design

Skype for Business Server fornece duas ferramentas para facilitar o planejamento e o design e reduzir a chance de configuração Skype for Business Server componentes. 
  
- **A Ferramenta de Planejamento de Topologia** automatiza grande parte do processo de design de topologia. Você pode exportar os resultados da Ferramenta de Planejamento para o Construtor de Topologias, que é a ferramenta necessária para instalar cada servidor executando Skype for Business Server.
    
- **O Construtor de Topologia** armazena todas as informações de configuração no armazenamento de Gerenciamento Central.
    
Para obter detalhes sobre essas ferramentas, [consulte Skype for Business Server Ferramentas de Gerenciamento.](../../management-tools/management-tools.md)
  
### <a name="central-management-store"></a>Central Management Store

Em Skype for Business Server, os dados de configuração sobre servidores e serviços fazem parte do armazenamento de Gerenciamento Central. O armazenamento de Gerenciamento Central fornece um armazenamento robusto e eschematizado dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação Skype for Business Server. Também valida os dados para garantir a consistência da configuração. Todas as alterações a esses dados de configuração ocorrem no armazenamento de Gerenciamento Central, eliminando problemas de "fora de sincronização". 
  
Cópias de somente leitura dos dados são replicadas a todos os servidores na topologia, incluindo Servidores de Borda e Aparelhos de Filia Persistente. A replicação é gerenciada por um serviço que, por padrão, é executado sob o contexto do serviço de Rede, reduzindo os direitos e permissões para os de um simples usuário no computador. 
  
### <a name="server-to-server-authentication"></a>Autenticação de servidor para servidor

No Skype for Business Server, a autenticação pode ser configurada entre servidores usando o protocolo Open Authorization (OAuth). Por exemplo, você pode configurar Skype for Business Server autenticar com um servidor que está executando Microsoft Exchange Server 2016. Usando o protocolo OAuth, os Skype for Business Server e os Microsoft Exchange Server podem confiar uns nos outros. Isso fornece a capacidade de integrar os produtos de maneira perfeita. Para obter detalhes, consulte [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell gerenciamento baseado em web e interface de gerenciamento baseada na Web

Skype for Business Server fornece uma interface de gerenciamento poderosa, criada Windows PowerShell interface de linha de comando. Ela inclui cmdlets para o gerenciamento de segurança e os recursos de segurança do Windows PowerShell estão habilitados por padrão, de modo que os usuários não podem executar scripts com facilidade ou sem ter conhecimento. Isso significa que os padrões do software são definidos para ajudar automaticamente a maximizar a segurança e a reduzir os meios para ataques. Para obter detalhes sobre Windows PowerShell de gerenciamento no Skype for Business Server, [consulte Skype for Business Server Management Shell](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Controle de acesso baseado em função (RBAC)

Skype for Business Server fornece controle de acesso baseado em função (RBAC) para permitir que você delegar tarefas administrativas enquanto mantém altos padrões de segurança. É possível usar o RBAC para seguir o princípio de "privilégios mínimos", no qual os usuários recebem somente os direitos administrativos que seus trabalhos exigem. Skype for Business Server a capacidade de criar uma nova função e também a capacidade de modificar uma função existente. 
  
## <a name="network-address-translation-nat"></a>Nat (Conversão de Endereço de Rede)

O Skype for Business Server não dá suporte ao uso de NAT (conversão de endereço de rede) na interface interna do Servidor de Borda, mas oferece suporte à colocação da interface externa do serviço de Borda de Acesso, do serviço de Borda de WebConferência e do serviço de Borda A/V atrás de um roteador ou firewall que executa NAT (conversão de endereço de rede) para topologias consolidadas do Servidor de Borda única e dimensionada. Vários Servidores de Borda atrás de um balanceador de carga de hardware não podem usar NAT. Se vários Servidores de Borda usarem NAT em suas interfaces externas, o balanceamento de carga DNS (Sistema de Nomes de Domínio) será necessário. Por sua vez, o uso do balanceamento de carga DNS permite reduzir o número de endereços IP públicos por Servidor de Borda em um pool de Servidor de Borda. Para obter detalhes, consulte [Cenários do Servidor de Borda em Skype for Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Se você se federar com empresas com uma implantação do Microsoft Office Communications Server 2007 e precisar usar áudio/vídeo entre sua empresa e a empresa federada, os requisitos de porta serão aqueles para a versão mais antiga dos Servidores de Borda implantados. Por exemplo, os intervalos de porta necessários para essas versões mais antigas devem ser abertos para ambas as empresas até que o parceiro federado atualize seus Servidores de Borda para Skype for Business Server. A qualquer momento, os requisitos de porta podem ser revisados e reduzidos de acordo com a nova configuração. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificados simplificados para servidores de borda

O Assistente de Implantação pode preencher automaticamente os SNs (nomes de entidade) e os SANs (nomes de entidade alternativos), reduzindo a possibilidade de inclusão de entradas desnecessárias e possivelmente perigosas.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de vida de desenvolvimento de segurança de computação confiável (SDL)

Skype for Business Server é projetado e desenvolvido em conformidade com o [SDL (Ciclo](/previous-versions/ms995349(v=msdn.10)) de Vida de Desenvolvimento de Segurança de Computação Confiável) da Microsoft.
  
- **Confiável por design** A primeira etapa na criação de um sistema de comunicações unificada mais seguro era projetar modelos de ameaça e testar cada recurso conforme ele foi projetado. Além disso, a Microsoft realiza testes fora do comportamento projetado para encontrar vulnerabilidades de segurança resultantes do comportamento inesperado do produto. Diversos aprimoramentos relacionados à segurança foram integrados ao processo e práticas de codificação. As ferramentas de tempo de compilação detectam estouros de buffer e outras possíveis ameaças de segurança antes que o código seja verificado no produto final. É claro que é impossível estar preparado para todas as ameaças de segurança desconhecidas. Nenhum sistema pode garantir a segurança completa. No entanto, como o desenvolvimento de produtos adotou princípios de design seguro desde o início, o Skype for Business Server incorpora tecnologias de segurança padrão do setor como uma parte fundamental de sua arquitetura.
    
- **Confiável por padrão** Por padrão, as comunicações de rede Skype for Business Server são criptografadas. Como todos os servidores usam certificados e autenticação Kerberos, TLS, Protocolo de Transporte seguro Real-Time (SRTP) e outras técnicas de criptografia padrão do setor, incluindo criptografia AES (Advanced Encryption Standard) de 128 bits, praticamente todos os Skype for Business Server dados são protegidos na rede. Além disso, o controle de acesso baseado em função possibilita a implantação de servidores que executam o Skype for Business Server para que cada função de servidor executa apenas os serviços e tenha apenas as permissões relacionadas a esses serviços, apropriadas para a função de servidor.
    
- **Confiável pela implantação** Toda Skype for Business Server documentação inclui práticas recomendadas e recomendações para ajudá-lo a determinar e configurar os níveis de segurança ideais para sua implantação e avaliar os riscos de segurança da ativação de opções não padrão.
