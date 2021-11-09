---
title: Alterações feitas pela preparação da floresta em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Esta seção descreve os objetos e as configurações globais, além dos grupos universais de serviço e administração criados pela etapa de preparação de floresta.
ms.openlocfilehash: 8226c2e9b692699902faa751fafe14424e43ed45
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828634"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Alterações feitas pela preparação da floresta em Skype for Business Server

Esta seção descreve os objetos e as configurações globais, além dos grupos universais de serviço e administração criados pela etapa de preparação de floresta.

## <a name="active-directory-global-settings-and-objects"></a>Objetos e configurações globais do Active Directory

Se você armazenar configurações globais no contêiner De configuração (como é o caso de todas as novas implantações de Skype for Business Server), a preparação da floresta usará o contêiner de Serviços existente e adiciona um **objeto RTC Service** no objeto Configuration\Services. Sob a implantação do Serviço de RTC, a preparação da floresta adiciona um objeto **Configurações Globais** do tipo msRTCSIP-GlobalContainer. O objeto de configurações globais contém todas as configurações que se aplicam à implantação Skype for Business Server global. Se você armazenar as configurações globais no contêiner Sistema, a preparação da floresta usará um contêiner Microsoft sob o contêiner Sistema do domínio raiz e um objeto Serviço de RTC sob o objeto Sistema\Microsoft.

A preparação de floresta também adiciona um novo objeto **msRTCSIP-Domain** ao domínio raiz no qual o procedimento é executado.

## <a name="active-directory-universal-service-and-administration-groups"></a>Grupos universais de serviço e administração do Active Directory

A preparação de floresta cria grupos universais com base no domínio especificado e adiciona entradas de controle de acesso (ACEs) para esses grupos. Essa etapa cria os grupos universais nos contêineres Usuário do domínio especificado.

Os grupos universais permitem que os administradores acessem e gerenciem as configurações e serviços globais. A preparação da floresta adiciona os seguintes tipos de grupos universais:

- **Grupos administrativos** Esses grupos definem funções de administrador para uma Skype for Business Server rede.

- **Grupos de infraestrutura** Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura de Skype for Business Server. Eles funcionam como componentes dos grupos administrativos. Não modifique esses grupos ou adicione usuários diretamente a eles.

- **Grupos de serviços** Esses grupos são contas de serviço que são necessárias para acessar vários Skype for Business Server serviços.

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
|RTCUniversalGlobalWriteGroup  <br/> |Concede acesso de gravação a objetos de configuração global para Skype for Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede acesso somente leitura a objetos de configuração global para Skype for Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede acesso somente leitura a Skype for Business Server do usuário.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede acesso somente leitura a Skype for Business Server configurações. Este grupo não tem acesso às configurações no nível do pool, mas apenas às configurações específicas de um servidor individual.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede acesso somente leitura à configuração Skype for Business Server e é colocado no grupo Administradores Locais dos dispositivos de filial que podem servivíveis durante a instalação.  <br/> |

A tabela seguir descreve os grupos de serviço.

**Grupos de serviço criados durante a preparação da floresta**

|**Grupo de serviço**|**Descrição**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Inclui contas de serviço usadas para executar servidores front-end e Edição Standard servidores. Esse grupo permite aos servidores acesso de leitura/gravação Skype for Business Server configurações globais e objetos de usuário do Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Inclui contas de serviço usadas para executar Servidores de Conferência A/V, Serviços Web, Servidor de Mediação, Servidor de Arquivamento e Servidor de Monitoramento.  <br/> |
|RTCProxyUniversalServices  <br/> |Inclui contas de serviço usadas para executar Skype for Business Server Servidores de Borda.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Inclui servidores que podem participar da replicação do Skype for Business Server do Armazenamento de Gerenciamento Central.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede acesso somente leitura a Skype for Business Server configurações, mas permite a configuração para a instalação de um servidor de filial e implantação de dispositivos de filial suportáveis.  <br/> |

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

Para obter detalhes sobre as funções de RBAC e as tarefas permitidas para cada, consulte [Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) na documentação Planejamento.

A preparação de floresta cria ACEs particulares e públicas. Ele cria ACEs privadas no contêiner de configurações globais usado por Skype for Business Server. Esse contêiner é usado apenas por Skype for Business Server e está localizado no contêiner Configuration ou no contêiner System no domínio raiz, dependendo de onde você armazena as configurações globais. As ACEs públicas criadas pela preparação de floresta estão listadas na tabela a seguir.

**ACEs públicas criadas pela preparação de floresta**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Ler o contêiner do sistema de domínio raiz (não herdado) **\\**\* <br/>        | X  <br/>                            |
| Ler o contêiner DisplaySpecifiers da Configuração (não herdado)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>*ACEs que não são herdadas não concedem acesso a objetos filho sob esses contêineres. As ACEs que são herdadas concedem acesso aos objetos filho desses contêineres.

No contêiner Configuração, no contexto de nomenclatura de configuração, a preparação de floresta executa as seguintes tarefas:

- Adiciona uma entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para a página **Propriedade RTC** dos atributos adminContextMenu e adminPropertyPages do especificador de exibição de idioma para usuários, contatos e InetOrgPersons (por exemplo, CN=user-Display,CN=409,CN=DisplaySpecifiers).

- Adiciona um objeto **RTCPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário e Contato.

- Adiciona um objeto **RTCUserSearchPropertySet** do tipo **controlAccessRight** em **Extended-Rights**, que se aplica às classes Usuário, Contato, UO e DomainDNS.

- Adiciona **msRTCSIP-PrimaryUserAddress** sob o atributo **extraColumns** do especificador de exibição da UO (unidade organizacional) de cada idioma (por exemplo, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) e copia os valores do atributo **extraColumns** da exibição padrão (por exemplo, CN=default-Display, CN=409,CN=DisplaySpecifiers).

- Adiciona os atributos de filtragem **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** e **msRTCSIP-UserEnabled** sob o atributo **attributeDisplayNames** do especificador de exibição de cada idioma para os objetos Usuários, Contatos e InetOrgPerson (por exemplo, em inglês: CN=user-Display,CN=409,CN=DisplaySpecifiers).