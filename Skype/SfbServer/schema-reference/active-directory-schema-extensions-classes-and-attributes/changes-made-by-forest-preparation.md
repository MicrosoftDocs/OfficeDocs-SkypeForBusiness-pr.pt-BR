---
title: Alterações feitas pela preparação de floresta no Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Esta seção descreve as configurações globais e objetos e os grupos universais de serviço e administração criados pela etapa de preparação de floresta.
ms.openlocfilehash: 9ceece01d6f5184eb58f0906dd61540c2dcf2084
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244334"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Alterações feitas pela preparação de floresta no Skype para Business Server

Esta seção descreve as configurações globais e objetos e os grupos universais de serviço e administração criados pela etapa de preparação de floresta.

## <a name="active-directory-global-settings-and-objects"></a>Objetos e configurações globais do active Directory

Se você armazena as configurações globais no contêiner configuração (como é o caso para todos os novos Skype para implantações de servidor de negócios), a preparação da floresta usa o contêiner serviços existente e adiciona um objeto **Serviço RTC** sob a configuração \ Serviços objeto. Objeto serviço RTC, a preparação de floresta adiciona um objeto de **Configurações globais** do tipo msRTCSIP-GlobalContainer. O objeto de configurações globais mantém todas as configurações que se aplicam ao Skype para implantação de servidor de negócios. Se você armazenar configurações globais no contêiner do sistema, a preparação da floresta usa um recipiente de Microsoft sob o contêiner sistema do domínio raiz e um objeto serviço RTC o objeto System\Microsoft.

A preparação da floresta também adiciona um novo objeto **msRTCSIP-Domain** ao domínio raiz no qual o procedimento é executado.

## <a name="active-directory-universal-service-and-administration-groups"></a>Grupos de administração e serviço Universal do Active Directory

A preparação da floresta cria grupos universais com base no domínio especificado e adiciona entradas de controle de acesso (ACEs) para esses grupos. Essa etapa cria os grupos universais nos contêineres usuário do domínio que você especificar.

Grupos universais permitem que administradores acessar e gerenciar serviços e configurações globais. Preparação de floresta adiciona os seguintes tipos de grupos universais:

- **Grupos administrativos** Esses grupos definem as funções de administrador para uma Skype para rede Business Server.

- **Grupos de infraestrutura** Esses grupos fornecem permissão para acessar a áreas específicas do Skype a infra-estrutura de servidor de negócios. Eles funcionam como componentes de grupos administrativos. Você não deve modificar esses grupos ou adicionar usuários diretamente a eles.

- **Grupos de serviço** Esses grupos são contas de serviço necessárias para acessar vários Skype para serviços de Business Server.

A tabela a seguir descreve os grupos administrativos.

**Grupos administrativos criados durante a preparação da floresta**

|**Grupo administrativo**|**Descrição**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permite que os membros gerenciem configurações de pool, incluindo todas as funções de servidor e servidor, configurações globais e usuários.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permite que os membros gerenciem configurações de usuário e movam usuários de um servidor ou pool para outro.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permite que os membros leiam configurações de servidor, pool e usuário.  <br/> |

A tabela a seguir descreve os grupos de infraestrutura.

**Grupos de infraestrutura criados durante a preparação da floresta**

|**Grupo de infraestrutura**|**Descrição**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Concede acesso de gravação aos objetos de configuração global do Skype para Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede acesso somente leitura aos objetos de configuração global do Skype para Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede acesso somente leitura às Skype para configurações de usuário do servidor de negócios.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede acesso somente leitura às Skype pelas configurações do servidor de negócios. Este grupo não tem acesso às configurações de nível de pool, apenas às configurações específicas para um servidor individual.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede acesso somente leitura ao Skype para configuração do servidor de negócios e são colocados no grupo Local de administradores de aparelhos de filial persistente durante a instalação.  <br/> |

A tabela a seguir descreve os grupos de serviço.

**Grupos de serviço criados durante a preparação da floresta**

|**Grupo de serviço**|**Descrição**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Inclui contas de serviço usadas para executar o servidor Front-End e servidores Standard Edition. Este grupo permite que os servidores de acesso de leitura/gravação para Skype para configurações globais do servidor de negócios e objetos de usuário do Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Inclui contas de serviço usadas para executar A / V Conferencing Servers, serviços Web, servidor de mediação, o servidor de arquivamento e Monitoring Server.  <br/> |
|RTCProxyUniversalServices  <br/> |Inclui contas de serviço usadas para executar o Skype para servidores de borda do servidor de negócios.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Inclui servidores que podem participar Skype para replicação do repositório de gerenciamento Central do Business Server.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede acesso somente leitura às Skype pelas configurações do servidor de negócios, mas permite a configuração para a instalação de um servidor de filial persistente e a implantação de aparelho de filial persistente.  <br/> |

A preparação da floresta, em seguida, adiciona os grupos de serviço e administração aos grupos de infraestrutura apropriados, da seguinte maneira:

- RTCUniversalServerAdmins é adicionado a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins é adicionado como um membro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins são adicionados como membros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

A preparação da floresta também cria os seguintes grupos de acesso baseado em função (RBAC) do controle:

- CSAdministrator

- Função CSArchivingAdministrator

- CSHelpDesk

- CSLocationAdministrator

- CSResponseGroupAdministrator

- CSServerAdministrator

- CSUserAdministrator

- CSViewOnlyAdministrator

- CSVoiceAdministrator

- CsPersistentChatAdministator

- CsResponseGroupManager

Para obter detalhes sobre as funções RBAC e as tarefas permitidas para cada um, consulte [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) na documentação de planejamento.

A preparação da floresta cria ACEs públicas e privadas. Ela cria ACEs particulares no contêiner configurações globais usado pelo Skype para Business Server. Este contêiner é usado somente pelo Skype para Business Server e está localizado no contêiner configuração ou o contêiner sistema no domínio raiz, dependendo de onde você pode armazenar configurações globais. As ACEs públicas criadas pela preparação da floresta estão listadas na tabela a seguir.

**ACEs públicas criadas pela preparação da floresta**

|**ACE**|**RTCUniversalGlobalReadOnlyGroup**|
|:-----|:-----|
|Ler o contêiner do sistema (não herdado) do domínio raiz**\*** <br/> |X  <br/> |
|Contêiner DisplaySpecifiers de configuração de leitura (não herdado)  <br/> |X  <br/> |

> [!NOTE]
> **\*** As aCEs que não são herdadas não concedem acesso aos objetos filho desses contêineres. ACEs são herdadas concedem acesso aos objetos filho desses contêineres.

No contêiner configuração, sob o contexto de nomenclatura de configuração, a preparação da floresta executa as seguintes tarefas:

- Adiciona uma entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para a página **propriedade RTC** admincontextmenu e adminPropertyPages atributos da linguagem exibem especificador para usuários, contatos e InetOrgPersons (por exemplo, CN = User-Display, CN = 409, CN = DisplaySpecifiers).

- Adiciona um objeto **RTCPropertySet** do tipo **controlAccessRight** em **Extended-Rights** que se aplica às classes usuário e contato.

- Adiciona um objeto **RTCUserSearchPropertySet** do tipo **controlAccessRight** em **Extended-Rights** que se aplica às classes usuário, contato, UO e DomainDNS.

- Adiciona **msRTCSIP-PrimaryUserAddress** sob o atributo **extraColumns** do especificador de exibição de unidade organizacional (UO) cada idioma (por exemplo, CN = organizationalUnit-Display, CN = 409, CN = DisplaySpecifiers) e copia os valores da atributo **extraColumns** da exibição padrão (por exemplo, CN = default-Display, CN = 409, CN = DisplaySpecifiers).

- Adiciona **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**e **msRTCSIP-UserEnabled** filtrando atributos ao atributo **attributeDisplayNames** de cada idioma exibem especificador para usuários, contatos, e objetos InetOrgPerson (por exemplo, em inglês: CN = user-Display, CN = 409, CN = DisplaySpecifiers).


