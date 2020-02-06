---
title: Alterações feitas pela preparação da floresta no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Esta seção descreve as configurações globais e os objetos, e o serviço universal e os grupos de administração criados pela etapa de preparação da floresta.
ms.openlocfilehash: 26917915d89aff721e74f094eb8ad5bb72db3cf6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815529"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Alterações feitas pela preparação da floresta no Skype for Business Server

Esta seção descreve as configurações globais e os objetos, e o serviço universal e os grupos de administração criados pela etapa de preparação da floresta.

## <a name="active-directory-global-settings-and-objects"></a>Objetos e configurações globais do Active Directory

Se você armazenar configurações globais no contêiner de configuração (como é o caso de todas as novas implantações do Skype for Business Server), a preparação da floresta usará o contêiner de serviços existentes e adicionará um objeto de **serviço RTC** no objeto Configuration\Services. No objeto de serviço RTC, a preparação da floresta adiciona um objeto de **configurações globais** do tipo MsRTCSIP-GlobalContainer. O objeto de configurações globais armazena todas as configurações que se aplicam à implantação do Skype for Business Server. Se você armazenar configurações globais no contêiner do sistema, a preparação da floresta usará um contêiner da Microsoft no contêiner do sistema do domínio raiz e um objeto de serviço RTC sob o objeto System\Microsoft.

A preparação da floresta também adiciona um novo objeto **msRTCSIP-Domain** para o domínio raiz no qual o procedimento é executado.

## <a name="active-directory-universal-service-and-administration-groups"></a>Grupos de administração e serviço universal do Active Directory

A preparação da floresta cria grupos universais baseados no domínio que você especifica e adiciona entradas de controle de acesso (ACEs) a esses grupos. Esta etapa cria os grupos universais nos contêineres de usuários do domínio que você especificar.

Os grupos universais permitem que os administradores acessem e gerenciem serviços e configurações globais. A preparação da floresta adiciona os seguintes tipos de grupos universais:

- **Grupos administrativos** Esses grupos definem funções de administrador para uma rede do Skype for Business Server.

- **Grupos de infraestrutura** Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Skype for Business Server. Elas funcionam como componentes de grupos administrativos. Você não deve modificar esses grupos ou adicionar usuários diretamente a eles.

- **Grupos de serviços** Esses grupos são contas de serviço que são necessárias para acessar vários serviços do Skype for Business Server.

A tabela a seguir descreve os grupos administrativos.

**Grupos administrativos criados durante a preparação da floresta**

|**Grupo administrativo**|**Descrição**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permite que os membros gerenciem as configurações do servidor e do pool, incluindo todas as funções do servidor, configurações globais e usuários.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permite que os membros gerenciem as configurações do usuário e movam os usuários de um servidor ou pool para outro.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permite que os membros leiam configurações de servidor, pool e usuário.  <br/> |

A tabela a seguir descreve os grupos de infraestrutura.

**Grupos de infraestrutura criados durante a preparação da floresta**

|**Grupo de infraestrutura**|**Descrição**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Concede acesso de gravação a objetos de configuração global para o Skype for Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede acesso somente leitura aos objetos de configuração global para o Skype for Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede acesso somente leitura às configurações de usuário do Skype for Business Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede acesso somente leitura às configurações do Skype for Business Server. Esse grupo não tem acesso às configurações do nível do pool, somente para configurações específicas de um servidor individual.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede acesso somente leitura à configuração do Skype for Business Server e é colocado no grupo local de administradores dos aparelhos de ramificação sobreviventes durante a instalação.  <br/> |

A tabela a seguir descreve os grupos de serviços.

**Grupos de serviço criados durante a preparação da floresta**

|**Grupo de serviços**|**Descrição**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Inclui contas de serviço usadas para executar servidores front-end Server e Standard Edition. Esse grupo permite que os servidores tenham acesso de leitura/gravação às configurações globais do Skype for Business Server e aos objetos de usuário do Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Inclui contas de serviço usadas para executar servidores de conferência A/V, serviços Web, servidor de mediação, servidor de arquivamento e Monitoring Server.  <br/> |
|RTCProxyUniversalServices  <br/> |Inclui contas de serviço usadas para executar servidores do Skype for Business Server Edge.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Inclui servidores que podem participar da replicação do repositório de gerenciamento central do Skype for Business Server.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede acesso somente leitura às configurações do Skype for Business Server, mas permite a configuração de um servidor de ramificação sobreviventes e a implantação de dispositivos em filiais sobreviventes.  <br/> |

A preparação da floresta adiciona grupos de serviços e de administração aos grupos de infraestrutura apropriados, da seguinte maneira:

- RTCUniversalServerAdmins é adicionado a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins é adicionado como membro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins são adicionados como membros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

A preparação da floresta também cria os seguintes grupos de controle de acesso baseado na função (RBAC):

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

Para obter detalhes sobre as funções RBAC e as tarefas permitidas para cada uma, consulte [controle de acesso baseado em função](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) na documentação de planejamento.

A preparação da floresta cria ACEs públicas e privadas. Ele cria ACEs privadas no contêiner de configurações globais usado pelo Skype for Business Server. Esse contêiner é usado apenas pelo Skype for Business Server e está localizado no contêiner de configuração ou no contêiner do sistema do domínio raiz, dependendo de onde você armazenou as configurações globais. As ACEs públicas criadas pela preparação da floresta são listadas na tabela a seguir.

**ACEs públicas criadas pela preparação da floresta**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Ler contêiner do sistema de domínio raiz (não herdado)**\\**\* <br/>        | X  <br/>                            |
| Ler o contêiner DisplaySpecifiers da configuração (não herdado)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* ACEs que não são herdadas não concedem acesso a objetos filho sob esses contêineres. ACEs que são herdadas conceder acesso a objetos filho sob esses contêineres.

No contêiner de configuração, no contexto de nomenclatura de configuração, a preparação da floresta executa as seguintes tarefas:

- Adiciona uma entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para a página de **Propriedades RTC** nos atributos adminContextMenu e adminPropertyPages do especificador de exibição de idioma para usuários, contatos e inetOrgPersons (por exemplo, CN = user-Display, CN = 409, CN = DisplaySpecifiers).

- Adiciona um objeto **RTCPropertySet** do tipo **ControlAccessRight** em **direitos estendidos** que se aplicam às classes de usuário e de contato.

- Adiciona um objeto **RTCUserSearchPropertySet** do tipo **ControlAccessRight** em **direitos estendidos** que se aplicam às classes usuário, contato, UO e DomainDNS.

- Adiciona **msRTCSIP-PrimaryUserAddress** sob o atributo **extraColumns** de cada especificador de exibição de unidade organizacional (ou) de idioma (por exemplo, CN = ORGANIZATIONALUNIT-display, CN = 409, CN = DisplaySpecifiers) e copia os valores do atributo **extraColumns** da exibição padrão (por exemplo, CN = Default-display, CN = 409, CN = DisplaySpecifiers).

- Adiciona atributos de filtragem **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**e **msRTCSIP-UserEnabled** sob o atributo **attributeDisplayNames** de cada especificador de exibição de idioma para os objetos usuários, contatos e INETORGPERSON (por exemplo, em inglês: CN = usuário-exibição, CN = 409, CN = DisplaySpecifiers).


