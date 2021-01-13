---
title: Alterações feitas pela preparação da floresta no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Esta seção descreve os objetos e as configurações globais, além dos grupos universais de serviço e administração criados pela etapa de preparação de floresta.
ms.openlocfilehash: 4e8032cb91b012c710dc509708a813d55825f7a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831911"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Alterações feitas pela preparação da floresta no Skype for Business Server

Esta seção descreve os objetos e as configurações globais, além dos grupos universais de serviço e administração criados pela etapa de preparação de floresta.

## <a name="active-directory-global-settings-and-objects"></a>Objetos e configurações globais do Active Directory

Se você armazenar configurações globais no contêiner Configuração (como é o caso de todas as novas implantações do Skype for Business Server), a preparação da floresta usará o contêiner de Serviços existente e adiciona um objeto de Serviço **RTC** sob o objeto Configuration\Services. Sob a implantação do Serviço de RTC, a preparação da floresta adiciona um objeto **Configurações Globais** do tipo msRTCSIP-GlobalContainer. O objeto de configurações globais contém todas as configurações que se aplicam à implantação do Skype for Business Server. Se você armazenar as configurações globais no contêiner Sistema, a preparação da floresta usará um contêiner Microsoft sob o contêiner Sistema do domínio raiz e um objeto Serviço de RTC sob o objeto Sistema\Microsoft.

A preparação de floresta também adiciona um novo objeto **msRTCSIP-Domain** ao domínio raiz no qual o procedimento é executado.

## <a name="active-directory-universal-service-and-administration-groups"></a>Grupos universais de serviço e administração do Active Directory

A preparação de floresta cria grupos universais com base no domínio especificado e adiciona entradas de controle de acesso (ACEs) para esses grupos. Essa etapa cria os grupos universais nos contêineres Usuário do domínio especificado.

Os grupos universais permitem que os administradores acessem e gerenciem as configurações e serviços globais. A preparação da floresta adiciona os seguintes tipos de grupos universais:

- **Grupos administrativos** Esses grupos definem funções de administrador para uma rede do Skype for Business Server.

- **Grupos de infraestrutura** Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Skype for Business Server. Eles funcionam como componentes dos grupos administrativos. Não modifique esses grupos ou adicione usuários diretamente a eles.

- **Grupos de serviços** Esses grupos são contas de serviço necessárias para acessar vários serviços do Skype for Business Server.

A tabela seguir descreve os grupos administrativos.

**Grupos administrativos criados durante a preparação da floresta**

|**Grupo administrativo**|**Descrição**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permite que os membros gerenciem as configurações de servidor e de pool, incluindo todas as funções de servidor, configurações globais e usuários.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permite que os membros gerenciem configurações de usuário e movam usuários de um servidor ou pool para outro.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permite que os membros leiam configurações de servidor, pool e usuário.  <br/> |

A tabela seguir descreve os grupos de infraestrutura.

**Grupos de infraestrutura criados durante a preparação da floresta**

|**Grupo de infraestrutura**|**Descrição**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Concede acesso de gravação aos objetos de configuração global do Skype for Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede acesso somente leitura aos objetos de configuração global do Skype for Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede acesso somente leitura às configurações de usuário do Skype for Business Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede acesso somente leitura às configurações do Skype for Business Server. Este grupo não tem acesso às configurações no nível do pool, mas apenas às configurações específicas de um servidor individual.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede acesso somente leitura à configuração do Skype for Business Server e é colocado no grupo Administradores Locais dos aparelhos de filial que podem servivíveis durante a instalação.  <br/> |

A tabela seguir descreve os grupos de serviço.

**Grupos de serviço criados durante a preparação da floresta**

|**Grupo de serviço**|**Descrição**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Inclui contas de serviço usadas para executar servidores Front End e Standard Edition. Esse grupo permite aos servidores acesso de leitura/gravação às configurações globais do Skype for Business Server e aos objetos de usuário do Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Inclui contas de serviço usadas para executar Servidores de Conferência A/V, Serviços Web, Servidor de Mediação, Servidor de Arquivamento e Monitoring Server.  <br/> |
|RTCProxyUniversalServices  <br/> |Inclui contas de serviço usadas para executar os Servidores de Borda do Skype for Business Server.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Inclui servidores que podem participar da replicação do armazenamento de Gerenciamento Central do Skype for Business Server.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede acesso somente leitura às configurações do Skype for Business Server, mas permite a configuração para a instalação de um servidor de filial e implantação de aparelho de filial resvivível.  <br/> |

Em seguida, a preparação de floresta adiciona os grupos de serviço e administração aos grupos de infraestrutura apropriados, da seguinte maneira:

- RTCUniversalServerAdmins é adicionado a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins é adicionado como membro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins são adicionados como membros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

A preparação da floresta também cria os seguintes grupos RBAC (controle de acesso baseado na função):

- CSAdministrator

- CSArchivingAdministrator

- CSHelpDesk

- CSLocationAdministrator

- CSResponseGroupAdministrator

- CSServerAdministrator

- CSUserAdministrator

- CSViewOnlyAdministrator

- CSVoiceAdministrator

- CsPersistentChatAdministator

- CsResponseGroupManager

Para obter detalhes sobre as funções de RBAC e as tarefas permitidas para cada, consulte [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) na documentação Planejamento.

A preparação de floresta cria ACEs particulares e públicas. Ele cria ACEs privadas no contêiner de configurações globais usado pelo Skype for Business Server. Esse contêiner é usado somente pelo Skype for Business Server e está localizado no contêiner Configuração ou no contêiner Sistema no domínio raiz, dependendo de onde você armazena as configurações globais. As ACEs públicas criadas pela preparação de floresta estão listadas na tabela a seguir.

**ACEs públicas criadas pela preparação de floresta**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Ler contêiner do sistema de domínio raiz (não herdado) **\\**\* <br/>        | X  <br/>                            |
| Ler o contêiner DisplaySpecifiers da Configuração (não herdado)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>*AS ACEs que não são herdadas não concedem acesso a objetos filho nesses contêineres. As ACEs que são herdadas concedem acesso aos objetos filho desses contêineres.

No contêiner Configuração, no contexto de nomenclatura de configuração, a preparação de floresta executa as seguintes tarefas:

- Adiciona uma entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para a página **Propriedade RTC** dos atributos adminContextMenu e adminPropertyPages do especificador de exibição de idioma para usuários, contatos e InetOrgPersons (por exemplo, CN=user-Display,CN=409,CN=DisplaySpecifiers).

- Adiciona um objeto **RTCPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário e Contato.

- Adiciona um objeto **RTCUserSearchPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário, Contato, UO e DomainDNS.

- Adiciona **msRTCSIP-PrimaryUserAddress** sob o atributo **extraColumns** do especificador de exibição da UO (unidade organizacional) de cada idioma (por exemplo, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) e copia os valores do atributo **extraColumns** da exibição padrão (por exemplo, CN=default-Display, CN=409,CN=DisplaySpecifiers).

- Adiciona os atributos de filtragem **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** e **msRTCSIP-UserEnabled** sob o atributo **attributeDisplayNames** do especificador de exibição de cada idioma para os objetos Usuários, Contatos e InetOrgPerson (por exemplo, em inglês: CN=user-Display,CN=409,CN=DisplaySpecifiers).


