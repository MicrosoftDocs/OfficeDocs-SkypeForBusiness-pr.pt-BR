---
title: Serviços de Domínio do Active Directory para Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Os Serviços de Domínio Active Directory funcionam como o serviço de diretório para redes do Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Os Serviços de Domínio Active Directory também servem como a base na qual a infraestrutura de segurança do Skype for Business Server é criada. O objetivo desta seção é descrever como o Skype for Business Server usa os Serviços de Domínio Active Directory para criar um ambiente confiável para mensagens de IM, Webconferência, mídia e voz. Para obter detalhes sobre como preparar seu ambiente para os Serviços de Domínio Active Directory, consulte Install Skype for Business Server na documentação implantação. Para obter detalhes sobre a função dos Serviços de Domínio Active Directory em redes do Windows Server, consulte a documentação da versão do sistema operacional que você está usando.
ms.openlocfilehash: c4fea392fbabafa0852c21aa5b15118f2427319a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832321"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Serviços de Domínio do Active Directory para Skype for Business Server
 
Os Serviços de Domínio Active Directory funcionam como o serviço de diretório para redes do Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Os Serviços de Domínio Active Directory também servem como a base na qual a infraestrutura de segurança do Skype for Business Server é criada. O objetivo desta seção é descrever como o Skype for Business Server usa os Serviços de Domínio Active Directory para criar um ambiente confiável para mensagens de IM, Webconferência, mídia e voz. Para obter detalhes sobre como preparar seu ambiente para os Serviços de Domínio Active Directory, consulte [Install Skype for Business Server](../../deploy/install/install.md) na documentação implantação. Para obter detalhes sobre a função dos Serviços de Domínio Active Directory em redes do Windows Server, consulte a documentação da versão do sistema operacional que você está usando.
  
O Skype for Business Server usa os Serviços de Domínio Active Directory para armazenar:
  
- Configurações globais exigidas por todos os servidores que executam o Skype for Business Server em uma floresta.
    
- Informações de serviço que identificam as funções de todos os servidores que executam o Skype for Business Server em uma floresta.
    
- Algumas configurações de usuário.
    
## <a name="active-directory-infrastructure"></a>Infraestrutura do Active Directory

Os requisitos de infraestrutura do Active Directory incluem o seguinte:
  
- Requisitos do sistema operacional para controladores de domínio
    
- Requisitos de nível funcional de floresta e domínio
    
- Requisitos de domínio do catálogo global
    
Para obter detalhes, [consulte Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
  
## <a name="universal-groups"></a>Grupos universais

Durante a preparação da floresta, o Skype for Business Server cria vários grupos universais dentro dos Serviços de Domínio Active Directory que têm permissão para acessar e gerenciar configurações e serviços globais. Esses grupos universais incluem:
  
- **Grupos administrativos**. Esses grupos definem as funções de administrador fundamentais para uma rede do Skype for Business Server. Durante a preparação da floresta, esses grupos de administradores são adicionados aos grupos de infraestrutura do Skype for Business Server.
    
- **Grupos de serviço**. Esses grupos são contas de serviço necessárias para acessar vários serviços fornecidos pelo Skype for Business Server.
    
- **Grupos de infraestrutura**. Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Skype for Business Server. Eles funcionam como componentes de grupos administrativos e você não deve modificá-los ou adicionar usuários diretamente a eles. Durante a preparação da floresta, grupos de serviço e administração específicos são adicionados aos grupos de infraestrutura apropriados.
    
Para obter detalhes sobre os grupos universais específicos criados ao preparar o AD para o Skype for Business Server, bem como os grupos de serviço e administração adicionados aos grupos de infraestrutura, consulte [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.
  
> [!NOTE]
> O Skype for Business Server suporta os grupos universais no Windows Server 2012, bem como sistemas operacionais Windows Server 2003 para controladores de domínio. Os membros de grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínios e podem receber permissões em qualquer domínio na árvore ou floresta de domínios. O suporte a grupos universais, combinado com a delegação de administrador, simplifica o gerenciamento de uma implantação do Skype for Business Server. Por exemplo, não é necessário adicionar um domínio para outro para permitir que um administrador gerencie os dois. 
  
## <a name="role-based-access-control"></a>Controle de Acesso Baseado em Função

Além de criar grupos universais de serviço e administração e adicionar grupos de serviço e administração aos grupos universais apropriados, a preparação da floresta também cria grupos Role-Based controle de acesso (RBAC). Para obter detalhes sobre os grupos RBAC específicos criados pela preparação da floresta, consulte [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation. Para obter mais informações sobre grupos RBAC, consulte Controle de acesso baseado em função [(RBAC) para Skype for Business Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de Controle de Acesso (ACEs) e herança

A preparação de floresta cria ACEs particulares e públicas e adiciona as ACEs aos grupos universais criados. Ele cria ACEs privadas específicas no contêiner de configurações globais usado pelo Skype for Business Server. Esse contêiner é usado somente pelo Skype for Business Server e está localizado no contêiner Configuração ou no contêiner Sistema no domínio raiz, dependendo de onde você armazena as configurações globais.
  
A etapa de preparação do domínio adiciona ACEs (entradas de controle de acesso) a grupos universais que concedem permissões para hospedar e gerenciar usuários dentro do domínio. A preparação de domínio cria ACEs na raiz do domínio e três contêineres internos: Usuários, Computadores e Controladores de Domínio.
  
Para obter detalhes sobre as ACEs públicas criadas e adicionadas pela preparação da floresta e pela preparação do domínio, consulte Changes [made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) and Changes made by domain preparation in Skype for Business [Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) in the Deployment documentation.
  
As organizações geralmente bloqueiam o AD DS (Serviços de Domínio Active Directory) para ajudar a atenuar os riscos de segurança. No entanto, um ambiente bloqueado do Active Directory pode limitar as permissões que o Skype for Business Server exige. Isso pode incluir a remoção das ACEs de contêineres e OUs e a desabilitação da herança de permissões nos objetos User, Contact, InetOrgPerson ou Computer. Em um ambiente bloqueado do Active Directory, as permissões devem ser definidas manualmente em contêineres e UOs que necessitam deles.
  
## <a name="server-information"></a>Informações do servidor

Durante a ativação, o Skype for Business Server publica informações do servidor nos três seguintes locais nos Serviços de Domínio Active Directory:
  
- Um ponto de conexão de serviço (SCP) em cada objeto de computador do Active Directory correspondente a um computador físico no qual o Skype for Business Server está instalado.
    
- Objetos de servidor criados no contêiner da classe **msRTCSIP-Pools**.
    
- Servidores confiáveis especificados no Construtor de Topologias.
    
## <a name="service-connection-points"></a>Pontos de conexão de serviço

Cada objeto do Skype for Business Server nos Serviços de Domínio active Directory tem um SCP chamado RTC Services, que, por sua vez, contém vários atributos que identificam cada computador e especificam os serviços que ele fornece. Entre os atributos SCP mais importantes estão  *serviceDNSName*  , *serviceDNSNameType*  , *serviceClassname*  e *serviceBindingInformation*  . Os aplicativos de gerenciamento de ativos de terceiros podem recuperar informações do servidor em uma implantação consultando nesses e em outros atributos do SCP.
  
## <a name="active-directory-server-objects"></a>Objetos de servidor do Active Directory

Cada função de servidor do Skype for Business Server tem um objeto do Active Directory correspondente cujos atributos definem os serviços fornecidos por essa função. Além disso, quando um servidor Standard Edition é ativado ou quando um pool Enterprise Edition é criado, o Skype for Business Server cria um novo objeto **msRTCSIP-Pool** no contêiner **msRTCSIP-Pools.** A classe **msRTCSIP-Pool** especifica o FQDN (nome de domínio totalmente qualificado) do pool, juntamente com a associação entre os componentes de front-end e back-end do pool. (Um servidor Standard Edition é considerado um pool lógico cujos front-end e back-end são colocados em um único computador.)
  
## <a name="trusted-servers"></a>Servidores confiáveis

No Skype for Business Server, os servidores confiáveis são aqueles especificados quando você executar o Construtor de Topologias e publicar sua topologia. A topologia publicada, incluindo todas as informações do servidor, é armazenada no repositório de Gerenciamento Central. Somente os servidores definidos no repositório de Gerenciamento Central são confiáveis. No Skype for Business Server, um servidor confiável é aquele que atende aos seguintes critérios:
  
- O FQDN do servidor ocorre na topologia armazenada no repositório de Gerenciamento Central.
    
- O servidor apresenta um certificado válido de uma CA confiável. Para obter detalhes, [consulte Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or System requirements for Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
    
Quando um dos seguintes critérios está ausente, o servidor não é confiável e a conexão com ele é recusada. Esse requisito duplo impede um possível ataque, se improvável, no qual um servidor não-criminoso tenta assumir o FQDN de um servidor válido.
  
Além disso, para permitir que as implantações do Microsoft Office Communications Server 2007 R2 e do Microsoft Office Communications Server 2007 se comuniquem com servidores do Skype for Business Server, o Skype for Business Server cria contêineres durante a preparação da floresta para manter listas de servidores confiáveis para versões anteriores. A tabela a seguir descreve os contêineres criados para permitir a compatibilidade com implementações anteriores.
  
**Listas de servidores confiáveis e seus contêineres do Active Directory para compatibilidade com versões anteriores**

|**Lista de servidores confiáveis**|**Contêiner do Active Directory**|
|:-----|:-----|
|Servidores Standard Edition e Servidores Fron-End do pool Enterprise  <br/> |Serviço RTC/Configurações Globais  <br/> |
|Servidores de Conferência  <br/> |Serviço RTC/MCUs confiáveis  <br/> |
|Servidores de Web Components  <br/> |Serviço RTC/TrustedWebComponentsServers  <br/> |
|Servidores de Mediação e Servidores do Communicator Web Access, Servidor de Aplicativos, Registrador com QoE, Serviço de Conferência A/V (além de servidores SIP de terceiros)  <br/> |Serviço RTC/serviços confiáveis  <br/> |
|Servidores Proxy  <br/> |O Skype for Business Server não oferece suporte à compatibilidade com servidores proxy  <br/> |
   

## <a name="see-also"></a>Confira também

[Preparar o Active Directory para o Skype for Business Server](../../deploy/install/prepare-active-directory.md)
