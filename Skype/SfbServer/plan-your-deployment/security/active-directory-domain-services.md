---
title: Serviços de domínio do Active Directory para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: O serviços de domínio Active Directory funciona como o serviço de diretório para redes Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Os serviços de domínio Active Directory também servem como a base na qual a infraestrutura de segurança do Skype for Business Server é criada. A finalidade desta seção é descrever como o Skype for Business Server usa os serviços de domínio do Active Directory para criar um ambiente confiável para mensagens instantâneas, conferências na Web, mídia e voz. Para obter detalhes sobre como preparar seu ambiente para os serviços de domínio Active Directory, consulte instalar o Skype for Business Server na documentação de implantação. Para obter detalhes sobre a função dos serviços de domínio do Active Directory nas redes do Windows Server, consulte a documentação da versão do sistema operacional que você está usando.
ms.openlocfilehash: 4458d49bf2f57284ac29c68bb40f3979761d5c50
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297005"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Serviços de domínio do Active Directory para o Skype for Business Server
 
O serviços de domínio Active Directory funciona como o serviço de diretório para redes Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Os serviços de domínio Active Directory também servem como a base na qual a infraestrutura de segurança do Skype for Business Server é criada. A finalidade desta seção é descrever como o Skype for Business Server usa os serviços de domínio do Active Directory para criar um ambiente confiável para mensagens instantâneas, conferências na Web, mídia e voz. Para obter detalhes sobre como preparar seu ambiente para os serviços de domínio Active Directory, consulte [instalar o Skype for Business Server](../../deploy/install/install.md) na documentação de implantação. Para obter detalhes sobre a função dos serviços de domínio do Active Directory nas redes do Windows Server, consulte a documentação da versão do sistema operacional que você está usando.
  
O Skype for Business Server usa os serviços de domínio do Active Directory para armazenar:
  
- Configurações globais em que todos os servidores que executam o Skype for Business Server em uma floresta exigem.
    
- Informações do serviço que identificam as funções de todos os servidores que executam o Skype for Business Server em uma floresta.
    
- Algumas configurações de usuário.
    
## <a name="active-directory-infrastructure"></a>Infraestrutura do Active Directory

Os requisitos de infraestrutura do Active Directory incluem o seguinte:
  
- Requisitos do sistema operacional para controladores de domínio
    
- Requisitos de níveis funcionais de domínio e de floresta
    
- Requisitos de domínio do catálogo global
    
Para obter detalhes, consulte [requisitos ambientais para o Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos do servidor para o Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
## <a name="universal-groups"></a>Grupos Universais

Durante a preparação da floresta, o Skype for Business Server cria vários grupos universais dentro dos serviços de domínio do Active Directory que têm permissão para acessar e gerenciar configurações e serviços globais. Esses grupos universais incluem:
  
- **Grupos Administrativos**. Esses grupos definem as funções de administrador fundamentais para uma rede do Skype for Business Server. Durante a preparação da floresta, esses grupos de administradores são adicionados aos grupos de infraestrutura do Skype for Business Server.
    
- **Grupos de Serviços**. Esses grupos são contas de serviço que são necessárias para acessar vários serviços fornecidos pelo Skype for Business Server.
    
- **Grupos de infraestrutura**. Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Skype for Business Server. Eles funcionam como componentes dos grupos administrativos e você não deve modificá-los nem adicionar usuários diretamente a eles. Durante a preparação da floresta, grupos de serviços e de administração específicos são adicionados aos grupos de infraestrutura adequados.
    
Para obter detalhes sobre os grupos universais específicos criados ao preparar o anúncio para o Skype for Business Server, bem como os grupos de serviços e administração que são adicionados aos grupos de infraestrutura, consulte [as alterações feitas pela preparação da floresta no Skype for Business Servidor](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) na documentação de implantação.
  
> [!NOTE]
> O Skype for Business Server oferece suporte aos grupos universais do Windows Server 2012, bem como aos sistemas operacionais Windows Server 2003 para controladores de domínio. Os membros dos grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínio e podem receber permissões em qualquer domínio na árvore ou floresta de domínio. O suporte a grupos universais, combinado com delegação de administrador, simplifica o gerenciamento de uma implantação do Skype for Business Server. Por exemplo, não é necessário adicionar um domínio a outro para permitir que um administrador os gerencie. 
  
## <a name="role-based-access-control"></a>Controle de Acesso Baseado em Função

Além de criar grupos de serviços e administração universais e de adicionar grupos de serviços e de administração aos grupos universais adequados, a preparação da floresta também cria grupos de Controle de acesso baseado em função (RBAC). Para obter mais detalhes sobre os grupos de RBAC específicos criados pela preparação da floresta, consulte [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) na Documentação de implantação. Para obter mais informações sobre grupos RBAC, consulte [controle de acesso baseado em função (RBAC) para o Skype for Business Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de controle de acesso (ACEs) e Herança

A preparação da floresta cria ACEs privadas e públicas, adicionando ACEs nos grupos universais criados. Ele cria ACEs particulares específicas no contêiner de configurações globais usado pelo Skype for Business Server. Esse contêiner é usado apenas pelo Skype for Business Server e está localizado no contêiner de configuração ou no contêiner do sistema do domínio raiz, dependendo de onde você armazenou as configurações globais.
  
A etapa de preparação do domínio adiciona entradas de controle de acesso (ACEs) necessárias aos grupos universais que concedem permissões para hospedar e gerenciar usuários no domínio. A preparação do domínio cria ACEs no domínio raiz e três contêiners integrados: Usuário, Computadores e Controladores de Domínio.
  
Para obter detalhes sobre os ases públicos criados e adicionados pela preparação da floresta e pela preparação do domínio, confira [as alterações feitas pela preparação da floresta no Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) e [alterações feitas pela preparação do domínio no Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) no Documentação de implantação.
  
Geralmente, as organizações bloqueiam os serviços de domínio Active Directory (AD DS) para ajudar a reduzir os riscos de segurança. No entanto, um ambiente do Active Directory bloqueado pode limitar as permissões exigidas pelo Skype for Business Server. Isso inclui remover ACEs dos contêineres e OUs e desabilitar a herança de permissões nos objetos de Usuário, Contato, InetOrgPerson ou Computador. Em um ambiente bloqueado do Active Directory, as permissões devem ser definidas manualmente em contêineres e UOs que exigem.
  
## <a name="server-information"></a>Informações do servidor

Durante a ativação, o Skype for Business Server publica as informações do servidor nos três seguintes locais nos serviços de domínio Active Directory:
  
- Um SCP (ponto de conexão de serviço) em cada objeto de computador do Active Directory correspondente a um computador físico no qual o Skype for Business Server está instalado.
    
- Objetos de servidor criados no contêiner da classe **msRTCSIP-Pools**.
    
- Servidores confiáveis especificados no construtor de topologias.
    
## <a name="service-connection-points"></a>Pontos de conexão de serviço

Cada objeto do Skype for Business Server nos serviços de domínio Active Directory tem um SCP chamado RTC Services, que, por sua vez, contém vários atributos que identificam cada computador e especificam os serviços que ele fornece. Entre os atributos SCP mais importantes são *serviceDNSName* , *ServiceDNSNameType* , ** inclassname e *ServiceBindingInformation* . Os aplicativos de gerenciamento de ativos de terceiros podem recuperar informações do servidor em uma implantação consultando esses e outros atributos SCP.
  
## <a name="active-directory-server-objects"></a>Objetos de servidor do Active Directory

Cada função de servidor do Skype for Business Server tem um objeto do Active Directory correspondente cujos atributos definem os serviços fornecidos por essa função. Além disso, quando um servidor Standard Edition é ativado ou quando um pool da Enterprise Edition é criado, o Skype for Business Server cria um novo objeto **msRTCSIP-pool** no contêiner **msRTCSIP-Pools** . A classe **msRTCSIP-Pool** especifica o nome de domínio totalmente qualificado (FQDN) do pool, juntamente com a associação entre os componentes de front-end e back-end do pool. (Um servidor Standard Edition é considerado um pool lógico cujas extremidades dianteiras e posteriores são posicionadas em um único computador.)
  
## <a name="trusted-servers"></a>Servidores confiáveis

No Skype for Business Server, os servidores confiáveis são aqueles especificados quando você executa o construtor de topologias e publica a topologia. A topologia publicada, incluindo todas informações de servidor, é armazenada no Repositório de Gerenciamento Central. Apenas servidores definidos no Repositório de Gerenciamento Central são confiáveis. No Skype for Business Server, um servidor confiável é aquele que atende aos seguintes critérios:
  
- O FQDN do servidor é apresentado na topologia armazenada no Repositório de gerenciamento central.
    
- O servidor apresenta um certificado válido de uma CA confiável. Para obter detalhes, consulte [requisitos ambientais para o Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos do sistema para o Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
Se algum desses critérios não for cumprido, o servidor não é confiável e a conexão será recusada. Esse requisito duplo evita um ataque possível, se improvável, em que um servidor invasor tenta tomar o valor de um FQDN do servidor válido.
  
Além disso, para habilitar as implantações do Microsoft Office Communications Server 2007 R2 e do Microsoft Office Communications Server 2007 para se comunicar com os servidores do Skype for Business Server, o Skype for Business Server cria contêineres durante a preparação da floresta para armazenar listas de servidores confiáveis para versões anteriores. A tabela a seguir descreve os contêineres criados para permitir a compatibilidade com implantações anteriores.
  
**Listas de servidores confiáveis e seus contêineres do Active Directory para compatibilidade com versões anteriores**

|**Lista de servidor confiável**|**Contêiner do Active Directory**|
|:-----|:-----|
|Servidor Standard Edition e Servidor Front-End do Pool Enterprise  <br/> |Configurações globais/Serviço RTC  <br/> |
|Servidores de Conferência  <br/> |Serviço RTC/MCUs Confiáveis  <br/> |
|Servidores de componentes da Web  <br/> |Serviço RTC/TrustedWebComponentsServers  <br/> |
|Servidor de Mediação e Servidores do Communicator Web Access, Servidor de Aplicativo, Registrador do QoE, Serviço de Conferência A/V (também servidores SIP de terceiros)  <br/> |Serviço RTC/Serviços confiáveis  <br/> |
|Servidores proxy  <br/> |O Skype for Business Server não é compatível com a compatibilidade com versões anteriores dos servidores proxy  <br/> |
   

## <a name="see-also"></a>Confira também

[Preparar o Active Directory para o Skype for Business Server](../../deploy/install/prepare-active-directory.md)
