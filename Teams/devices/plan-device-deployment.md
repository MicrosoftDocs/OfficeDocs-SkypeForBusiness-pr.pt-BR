---
title: Planejar sua implantação para dispositivos Teams telefone e displays
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: Este artigo fornece e visão geral das tarefas e etapas para implantar Teams telefones e exibições em sua organização.
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577788"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Planejar sua implantação para dispositivos Teams telefone e displays

Uma implantação bem-sucedida Teams dispositivos de telefone e Teams displays começa com o planejamento. Este artigo levará você pelas tarefas e etapas para implantar esses dispositivos em sua organização. Ele também fornece orientações sobre uso, licenciamento e integração de dispositivos com seu ambiente, pontos de toque e gerenciamento.

> [!TIP]
> [O Microsoft 365 de](https://adoption.microsoft.com/) adoção é um ótimo lugar para começar sua jornada de adoção com Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Tarefa 1: Quais são seus objetivos de implantação?

O planejamento da distribuição de Teams e displays em sua organização começa com suas metas de implantação. Teams dispositivos suportam o trabalho híbrido em salas de reunião, escritórios e outros espaços funcionais. Você precisará determinar onde esses dispositivos serão usados e por quem.

### <a name="objective-identify-your-device-personas"></a>Objetivo: identificar suas personas de dispositivo

Teams telefones e displays caberão em uma das duas personas: 

- Dispositivos pessoais
- Dispositivos de espaço compartilhado

Dispositivos pessoais e compartilhados têm funções e usos diferentes. 

**Dispositivos pessoais:** 

- Normalmente atribuído a um usuário, entrar com a conta desse usuário e habilitado com uma Teams de recurso para acessar o serviço.
- Pense em dispositivos pessoais como tendo uma relação um para um, com um dispositivo por usuário.
- Pode ser emparelhado com o cliente Teams desktop e usar recursos como Better Together
- Pode se conectar a um fone de ouvido, com fio ou sem fio
- Recursos adicionais em dispositivos pessoais incluem hot-desking e Tela Inicial. 

**Dispositivos de espaço compartilhado:**

- Execute uma função específica, como um telefone de área comum ou dispositivo de sala de reunião e exige uma conta dedicada e uma licença de recurso para acessar o serviço.
- Pense em dispositivos compartilhados como tendo uma relação um para muitos: um dispositivo compartilhado por muitos usuários.
- Implantado em espaços compartilhados, como salas de reunião, áreas de recepção ou pisos de manufatura. 
- Suas interfaces de usuário (interface do usuário) são específicas de suas funções, como a interface do usuário da Área Comum Telefone ou a interface do usuário da sala de reunião dependem da função e do posicionamento do dispositivo compartilhado.
- Exigir configuração e o fortalecimento opcional para garantir que as configurações não sejam alteradas ou para impedir que a conta saia. 
- Recursos adicionais em dispositivos de espaço compartilhado incluem pesquisa em telefones de área comum e hot-desking com tempo limite ocioso

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Objetivo: quantos dispositivos de espaço pessoal e compartilhado você precisa?

Agora que você identificou suas personas de dispositivo, você precisa determinar quais dispositivos certificados você deseja usar e quantos deles você precisa. Para ajudá-lo a tomar essa decisão, considere as seguintes perguntas: 

- Quantos dispositivos pessoais são necessários e quem terá um?
- Quantas salas ou espaços exigem dispositivos compartilhados? Cada espaço terá o mesmo tipo de dispositivo? 
- Seus dispositivos precisarão atender a requisitos específicos?
    - Exemplos incluem tamanho da tela, fator de formulário e fabricante ou modelo? Para ver uma lista de telefones e exibições certificados, [consulte Microsoft Teams dispositivos certificados.](teams-ip-phones.md)
-  Você precisa de Teams ou Teams displays? Para ver uma lista de recursos suportados por telefones Teams, consulte [Telefones](phones-for-teams.md#features-supported-by-teams-phones) para Microsoft Teams e para ver uma lista de recursos suportados por Teams displays, consulte [Microsoft Teams displays](teams-displays.md#features-supported-by-teams-displays).
- Você tem dispositivos suficientes para novos usuários ou um processo para novos pedidos e entrega?
- Você terá dispositivos de reposição disponíveis para manutenção ou em caso de problemas de hardware? Ser capaz de trocar um dispositivo rapidamente impede interrupções na experiência do usuário.

## <a name="task-2-what-are-your-licensing-requirements"></a>Tarefa 2: Quais são seus requisitos de licenciamento? 

Agora que você sabe quantos dispositivos você precisa, a próxima etapa é determinar quantas licenças são necessárias. Teams telefones e exibições exigem licenças para acessar Microsoft Teams e Microsoft 365.

Dispositivos compartilhados e pessoais precisarão de licenciamento diferente. Para dispositivos pessoais, licenças atribuídas a contas de usuário podem ser usadas. Dispositivos compartilhados precisam de licenças específicas para suas funções. Para telefones e exibições, as licenças aplicáveis são a licença Telefone Área [Comum](../set-up-common-area-phones.md#step-1---buy-the-licenses) para Microsoft Teams e a [licença Salas do Microsoft Teams Padrão .](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)

Para obter mais informações e comparar suas opções de licenciamento, [consulte Microsoft 365 planos de licenciamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 

## <a name="task-3-what-are-your-dependencies"></a>Tarefa 3: Quais são suas dependências? 

### <a name="objective-plan-your-device-identities"></a>Objetivo: Planejar suas identidades de dispositivo

As identidades permitem que os dispositivos acessem serviços de Microsoft 365, e eles devem facilitar a descoberta, o gerenciamento e a conexão dos dispositivos em sua organização. Para fazer isso, considere o seguinte ao planejar identidades de dispositivo:

- Nomes principais do usuário e seu formato e domínio
- Exibir nomes
- Descoberta de livro de endereços
- Tipos de dispositivo de espaço pessoal versus compartilhado
- Licenciamento de grupo versus usuário atribuído

### <a name="objective-review-conditional-access-policies"></a>Objetivo: Revisar políticas de Acesso Condicional

Azure Active Directory políticas de Acesso Condicional são requisitos adicionais que devem ser atendidos antes que um dispositivo possa ser conectado.

Conforme você planeja sua implantação

- Revise as políticas de Acesso Condicional existentes que podem afetar seus Teams e displays. Você pode fazer isso no Centro de Administração do Azure AD usando a ferramenta [What If](/azure/active-directory/conditional-access/what-if-tool) e logs [de entrada](/azure/active-directory/reports-monitoring/concept-sign-ins)

- Planejar novas regras, se necessário

- Use recursos de Acesso Condicional, como filtros de dispositivo, para aplicar regras Teams telefones e exibições.

>[!NOTE]
>Há algumas políticas de Acesso Condicional que os dispositivos Android não suportam. Para obter orientações e práticas recomendadas, consulte Dispositivos Android, consulte Práticas recomendadas de autenticação [para Teams dispositivos Android](authentication-best-practices-for-android-devices.md).

## <a name="task-4-prepare-your-environment"></a>Tarefa 4: Preparar seu ambiente

### <a name="objective-plan-network-basics"></a>Objetivo: Planejar noções básicas de rede

Teams Telefone dispositivos e exibições exigem acesso à Internet para se conectarem Teams e funcionarem conforme o esperado. Para preparar sua rede para implantação, considere o seguinte:

- Sua infraestrutura de rede tem capacidade suficiente? Considere portas de opção, pontos de acesso sem fio e outras coberturas.
- Se você usar VLANs e DHCP, seus escopos serão dimensionado de acordo?
- Avalie e teste os caminhos de rede de onde os dispositivos são implantados Microsoft 365. 
- Abra as portas de firewall e URLs necessárias para Microsoft 365 de acordo com as diretrizes.
- Revise e teste os requisitos e a configuração do E911 para precisão e conformidade do local. 
- Evite usar um servidor proxy e otimizar caminhos de mídia para confiabilidade e qualidade.

### <a name="objective-physical-considerations"></a>Objetivo: considerações físicas

Considere os espaços físicos em que seus Teams telefones e exibições serão usados.

Os principais aspectos incluem

- **Power:** Você tem saídas elétricas suficientes? Se o dispositivo precisar de uma fonte de energia externa, a que ponto você pode posicioná-lo em uma saída?
- **Posicionamento do dispositivo:** Onde seu dispositivo estará fisicamente? Review desk stands, wall mounts, and other accessories from the original equipment manufacturer (OEM).
- **Segurança:** O dispositivo precisa ser bloqueado em determinados espaços?
- **Acessibilidade:** O dispositivo atendem aos requisitos de acessibilidade de seu usuário principal? Considere onde ele é colocado, comprimento do fio e usabilidade do fone de ouvido ou do fone de ouvido.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Tarefa 5: Como você gerenciará dispositivos implantados?

Teams telefones e exibições são gerenciados de dois Microsoft 365 portais e seus respectivos módulos do PowerShell: 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory Admin Center

Usar o Centro de Administração do Azure AD para gerenciar

- Todas as tarefas relacionadas à identidade para Teams telefones e exibições
- Políticas de Acesso Condicional 
- Redefinições de senha

#### <a name="teams-admin-center"></a>Teams Admin Center

Usar o Teams de Administração para gerenciar

- [Configurações de dispositivo para Teams](../business-voice/manage-devices.md)
- [Perfis de configuração](device-management.md#use-configuration-profiles-in-teams)
- [Marcação de dispositivo](manage-device-tags.md)
- [Entrar e sair remoto](remote-sign-in-and-sign-out.md)
- Análise de chamada  
- Firmware
- Solução de problemas e download de logs

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager Admin Center (se você usar o Intune para gerenciamento de dispositivos)

Use o Endpoint Manager Admin Center para gerenciar: 

- Políticas de conformidade de dispositivos
- Restrições de registro
- Identificadores de dispositivo corporativo
- Filtros de dispositivo
