---
title: Serviços de domínio do Active Directory para Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Serviços de domínio do Active Directory funciona como o serviço de diretório para redes do Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Serviços de domínio Active Directory também atuam como base no qual o Skype Business Server 2015 infra-estrutura de segurança está sendo construída. A finalidade desta seção é descrever como Skype para Business Server 2015 usa os serviços de domínio do Active Directory para criar uma ambiente confiável para mensagens Instantâneas, conferência Web, mídia e voz. Para obter detalhes sobre como preparar seu ambiente para serviços de domínio do Active Directory, consulte instalar Skype for Business Server 2015 na documentação de implantação. Para obter detalhes sobre a função dos serviços de domínio do Active Directory em redes do Windows Server, consulte a documentação para a versão do sistema operacional que você está usando.
ms.openlocfilehash: d0beaeba36db02e7b0e4ad76bfefa27a9a49a09d
ms.sourcegitcommit: 4eae947e339e728e5e1f338677860b910aafc029
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="active-directory-domain-services-for-skype-for-business-server-2015"></a>Serviços de domínio do Active Directory para Skype for Business Server 2015
 
Serviços de domínio do Active Directory funciona como o serviço de diretório para redes do Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Serviços de domínio Active Directory também atuam como base no qual o Skype Business Server 2015 infra-estrutura de segurança está sendo construída. A finalidade desta seção é descrever como Skype para Business Server 2015 usa os serviços de domínio do Active Directory para criar uma ambiente confiável para mensagens Instantâneas, conferência Web, mídia e voz. Para obter detalhes sobre como preparar seu ambiente para serviços de domínio do Active Directory, consulte [Instalar Skype para Business Server 2015](../../deploy/install/install.md) na documentação de implantação. Para obter detalhes sobre a função dos serviços de domínio do Active Directory em redes do Windows Server, consulte a documentação para a versão do sistema operacional que você está usando.
  
Skype para Business Server 2015 usa os serviços de domínio do Active Directory para armazenar:
  
- Configurações globais que necessitam de todos os servidores que executam o Skype para negócios 2015 de servidor em uma floresta.
    
- Informações de serviço que identificam as funções de todos os servidores que executam o Skype para negócios 2015 de servidor em uma floresta.
    
- Algumas configurações de usuário.
    
## <a name="active-directory-infrastructure"></a>Infraestrutura do Active Directory

Requisitos de infraestrutura do Active Directory incluem o seguinte:
  
- Requisitos do sistema operacional para controladores de domínio
    
- Requisitos de níveis funcionais de domínio e de floresta
    
- Requisitos de domínio do catálogo global
    
Para obter detalhes, consulte [requisitos de ambiente para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) na documentação de implantação.
  
## <a name="universal-groups"></a>Grupos Universais

Durante a preparação da floresta, Skype para Business Server 2015 cria vários grupos universais nos serviços de domínio Active Directory que têm permissão para acessar e gerenciar serviços e configurações globais. Esses grupos universais incluem:
  
- **Grupos Administrativos**. Esses grupos definem as funções básicas de administrador para uma Skype para rede Business Server. Durante a preparação da floresta, esses grupos de administrador são adicionados ao Skype para grupos de infraestrutura de Business Server.
    
- **Grupos de Serviços**. Esses grupos são contas de serviço necessárias para acessar vários serviços fornecidos pelo Skype para Business Server.
    
- **Grupos de infraestrutura**. Esses grupos fornecem permissão para acessar a áreas específicas do Skype a infra-estrutura de servidor de negócios. Eles funcionam como componentes dos grupos administrativos e você não deve modificá-los nem adicionar usuários diretamente a eles. Durante a preparação da floresta, grupos de serviços e de administração específicos são adicionados aos grupos de infraestrutura adequados.
    
Para obter detalhes sobre específicos grupos universais criados durante a preparação do AD para Skype para Business Server, bem como os grupos de serviço e administração obtém adicionados aos grupos de infraestrutura, consulte [alterações feitas pela preparação de floresta no Skype para negócios Servidor](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) na documentação de implantação.
  
> [!NOTE]
> Skype para Business Server 2015 oferece suporte a grupos universais no Windows Server 2012, bem como os sistemas operacionais Windows Server 2003 controladores de domínio. Os membros dos grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínio e podem receber permissões em qualquer domínio na árvore ou floresta de domínio. Suporte a grupos universais, combinado com a delegação do administrador, simplifica o gerenciamento de um Skype para implantação de servidor de negócios. Por exemplo, não é necessário adicionar um domínio a outro para permitir que um administrador os gerencie. 
  
## <a name="role-based-access-control"></a>Controle de Acesso Baseado em Função

Além de criar grupos de serviços e administração universais e de adicionar grupos de serviços e de administração aos grupos universais adequados, a preparação da floresta também cria grupos de Controle de acesso baseado em função (RBAC). Para obter detalhes sobre os grupos específicos de RBAC criados pela preparação de floresta, consulte [alterações feitas pela preparação da floresta no Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) na documentação de implantação. Para obter mais informações sobre grupos RBAC, consulte [o controle de acesso baseado em função (RBAC) para Skype para Business Server 2015](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de controle de acesso (ACEs) e Herança

A preparação da floresta cria ACEs privadas e públicas, adicionando ACEs nos grupos universais criados. Ela cria ACEs particulares específicos no contêiner configurações globais usado pelo Skype para Business Server. Este contêiner é usado somente pelo Skype para Business Server e está localizado no contêiner configuração ou o contêiner sistema no domínio raiz, dependendo de onde você pode armazenar configurações globais.
  
A etapa de preparação do domínio adiciona entradas de controle de acesso (ACEs) necessárias aos grupos universais que concedem permissões para hospedar e gerenciar usuários no domínio. A preparação do domínio cria ACEs no domínio raiz e três contêiners integrados: Usuário, Computadores e Controladores de Domínio.
  
Para obter detalhes sobre as ACEs públicas criadas e adicionadas pela preparação da floresta e preparação do domínio, consulte [alterações feitas pela preparação da floresta no Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) e [as alterações feitas pela preparação do domínio no Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) na Documentação de implantação.
  
As organizações geralmente bloqueiam os serviços de domínio Active Directory (AD DS) para ajudar a reduzir os riscos de segurança. No entanto, um ambiente de Active Directory bloqueado pode limitar as permissões exigidas Skype para Business Server 2015. Isso inclui remover ACEs dos contêineres e OUs e desabilitar a herança de permissões nos objetos de Usuário, Contato, InetOrgPerson ou Computador. Em um bloqueado para baixo do ambiente do Active Directory, a permissões devem ser definidas manualmente nos contêineres e OUs que requer que eles.
  
## <a name="server-information"></a>Informações do servidor

Durante a ativação, Skype para Business Server 2015 publica informações do servidor para os seguintes três locais nos serviços de domínio do Active Directory:
  
- O ponto de uma conexão de serviço (SCP) em cada objeto de computador do Active Directory correspondente a um computador físico no qual o Skype para Business Server 2015 está instalado.
    
- Objetos de servidor criados no contêiner da classe **msRTCSIP-Pools**.
    
- Servidores confiáveis especificados no construtor de topologia.
    
## <a name="service-connection-points"></a>Pontos de conexão de serviço

Cada Skype para objeto de negócios Server 2015 nos serviços de domínio do Active Directory tem um SCP chamado serviços RTC, que por sua vez contém um número de atributos que identificam cada computador e especifique os serviços que ele fornece. Entre o SCP mais importantes atributos são *serviceDNSName* , *serviceDNSNameType* , *serviceClassname* e *serviceBindingInformation* . Os aplicativos de gerenciamento de ativos de terceiros podem recuperar informações do servidor em uma implantação consultando esses e outros atributos SCP.
  
## <a name="active-directory-server-objects"></a>Objetos de servidor do Active Directory

Cada Skype para Business Server 2015 função de servidor tem um Active Directory correspondente cujos atributos definem os serviços fornecidos por essa função do objeto. Além disso, quando um servidor Standard Edition é ativado ou quando um pool Enterprise Edition é criado, o Skype para Business Server 2015 cria um novo objeto **msRTCSIP-Pool** no contêiner **msRTCSIP-Pools** . A classe **msRTCSIP-Pool** especifica o nome de domínio totalmente qualificado (FQDN) do pool, juntamente com a associação entre os componentes de front-end e back-end do pool. (Um servidor Standard Edition é considerado um pool lógico cujas extremidades frente e são colocadas em um único computador.)
  
## <a name="trusted-servers"></a>Servidores confiáveis

No Skype para Business Server 2015, servidores confiáveis são aqueles especificado quando você executa o construtor de topologia e publica sua topologia. A topologia publicada, incluindo todas informações de servidor, é armazenada no Repositório de Gerenciamento Central. Apenas servidores definidos no Repositório de Gerenciamento Central são confiáveis. No Skype para Business Server 2015, um servidor confiável é aquele que atenda aos seguintes critérios:
  
- O FQDN do servidor é apresentado na topologia armazenada no Repositório de gerenciamento central.
    
- O servidor apresenta um certificado válido de uma CA confiável. Para obter detalhes, consulte [requisitos de ambiente para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
    
Se algum desses critérios não for cumprido, o servidor não é confiável e a conexão será recusada. Esse requisito duplo impede um possível, se improvável, ataque no qual um servidor trapaceiro tenta capturar o FQDN de um servidor válido.
  
Além disso, para habilitar o Microsoft Office Communications Server 2007 R2 e implantações do Microsoft Office Communications Server 2007 para se comunicar com Skype para servidores de negócios Server 2015, Skype para Business Server 2015 cria contêiners durante a floresta preparação para reter as listas de servidores confiáveis para versões anteriores. A tabela a seguir descreve os contêineres criados para permitir a compatibilidade com implantações anteriores.
  
**Confiáveis listas de servidores e seus contêineres do Active Directory para compatibilidade com versões anteriores**

|**Lista de servidores confiáveis**|**Contêiner do Active Directory**|
|:-----|:-----|
|Servidor Standard Edition e Servidor Front-End do Pool Enterprise  <br/> |Configurações globais/Serviço RTC  <br/> |
|Servidores de Conferência  <br/> |Serviço RTC/MCUs Confiáveis  <br/> |
|Servidores de componentes da Web  <br/> |Serviço RTC/TrustedWebComponentsServers  <br/> |
|Servidor de Mediação e Servidores do Communicator Web Access, Servidor de Aplicativo, Registrador do QoE, Serviço de Conferência A/V (também servidores SIP de terceiros)  <br/> |Serviço RTC/Serviços confiáveis  <br/> |
|Servidores proxy  <br/> |Skype para Business Server 2015 não oferece suporte para compatibilidade com versões anteriores para servidores proxy  <br/> |
   

## <a name="see-also"></a>Consulte também

#### 
[Preparar o Active Directory para Skype para Business Server 2015](../../deploy/install/prepare-active-directory.md)