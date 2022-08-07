---
title: Planejar sua implantação para dispositivos de telefone e exibições do Teams
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
description: Este artigo fornece e visão geral das tarefas e das etapas para implantar telefones e exibições do Teams em sua organização.
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: 5172d230823088141c58e3d2b58e1c3b579268b3
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272386"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Planejar sua implantação para dispositivos de telefone e exibições do Teams

Uma implantação bem-sucedida de dispositivos de telefone do Teams e exibições do Teams começa com o planejamento. Este artigo explicará as tarefas e as etapas para implantar esses dispositivos em sua organização. Ele também fornece diretrizes sobre o uso, licenciamento e integração de dispositivos com seu ambiente, pontos de toque e gerenciamento.

> [!TIP]
> [O Hub de Adoção do Microsoft 365](https://adoption.microsoft.com/) é um ótimo lugar para começar sua jornada de adoção com o Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Tarefa 1: Quais são seus objetivos de implantação?

O planejamento da distribuição de telefones e displays do Teams em sua organização começa com suas metas de implantação. Os dispositivos do Teams dão suporte ao trabalho híbrido em salas de reunião, escritórios e outros espaços funcionais. Você precisará determinar onde esses dispositivos serão usados e por quem.

### <a name="objective-identify-your-device-personas"></a>Objetivo: identificar as personas do dispositivo

Os telefones e as telas do Teams caberão em uma das duas personas: 

- Dispositivos pessoais
- Dispositivos de espaço compartilhado

Dispositivos pessoais e compartilhados têm funções e usos diferentes. 

**Dispositivos pessoais:** 

- Normalmente atribuído a um usuário, conectado com a conta desse usuário e habilitado com uma licença de recurso do Teams para acessar o serviço.
- Pense em dispositivos pessoais como tendo uma relação um-para-um, com um dispositivo por usuário.
- Pode ser emparelhado com o cliente da área de trabalho do Teams e usar recursos como o Better Together
- Pode se conectar a um headset, com ou sem fio
- Recursos adicionais em dispositivos pessoais incluem mesa quente e tela inicial. 

**Dispositivos de espaço compartilhado:**

- Execute uma função específica, como um telefone de área comum ou dispositivo de sala de reunião e exija uma conta dedicada e uma licença de recurso para acessar o serviço.
- Pense em dispositivos compartilhados como tendo uma relação um-para-muitos: um dispositivo compartilhado por muitos usuários.
- Implantado em espaços compartilhados, como salas de reunião, áreas de recepção ou pisos de fabricação. 
- Suas interfaces do usuário (UI) são específicas para sua função, como interface do usuário do Telefone de Área Comum ou interface do usuário da sala de reunião dependem da função e do posicionamento do dispositivo compartilhado.
- Exigir configuração e proteção opcional para garantir que as configurações não sejam alteradas ou para impedir que a conta saia. 
- Recursos adicionais em dispositivos de espaço compartilhado incluem pesquisa em telefones de área comum e mesa quente com tempo limite ocioso

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Objetivo: quantos dispositivos de espaço pessoal e compartilhado você precisa?

Agora que você identificou suas personas de dispositivo, você precisa determinar quais dispositivos certificados deseja usar e quantos deles você precisa. Para ajudá-lo a tomar essa decisão, considere as seguintes perguntas: 

- Quantos dispositivos pessoais são necessários e quem terá um?
- Quantas salas ou espaços exigem dispositivos compartilhados? Cada espaço terá o mesmo tipo de dispositivo? 
- Seus dispositivos precisarão atender a requisitos específicos?
    - Os exemplos incluem tamanho da tela, fator forma e fabricante ou modelo? Para obter uma lista de telefones e monitores certificados, consulte [dispositivos certificados do Microsoft Teams](teams-ip-phones.md).
-  Você precisa de telefones do Teams ou exibições do Teams? Para obter uma lista dos recursos compatíveis com telefones do Teams, consulte [Telefones para Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones) e para obter uma lista de recursos compatíveis com as exibições do Teams, consulte as exibições do [Microsoft Teams](teams-displays.md#features-supported-by-teams-displays).
- Você tem dispositivos suficientes para novos usuários ou um processo para novos pedidos e entrega?
- Você terá dispositivos sobressalentes disponíveis para manutenção ou em caso de problemas de hardware? A capacidade de trocar um dispositivo impede rapidamente interrupções na experiência do usuário.

## <a name="task-2-what-are-your-licensing-requirements"></a>Tarefa 2: Quais são seus requisitos de licenciamento? 

Agora que você sabe quantos dispositivos precisa, a próxima etapa é determinar quantas licenças são necessárias. Telefones e exibições do Teams exigem licenças para acessar o Microsoft Teams e o Microsoft 365.

Dispositivos compartilhados e pessoais precisarão de licenciamento diferente. Para dispositivos pessoais, licenças atribuídas a contas de usuário podem ser usadas. Dispositivos compartilhados precisam de licenças específicas para sua função. Para telefones e monitores, as licenças aplicáveis são a licença [do Common Area Phone para o Microsoft Teams](../set-up-common-area-phones.md#step-1---buy-the-licenses) e a [licença Salas do Microsoft Teams Padrão uso.](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)

Para obter mais informações e comparar suas opções de licenciamento, consulte [planos de licenciamento do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1). 

## <a name="task-3-what-are-your-dependencies"></a>Tarefa 3: Quais são suas dependências? 

### <a name="objective-plan-your-device-identities"></a>Objetivo: Planejar as identidades do dispositivo

As identidades permitem que os dispositivos acessem os serviços do Microsoft 365 e devem facilitar a descoberta, o gerenciamento e a conexão dos dispositivos em sua organização. Para fazer isso, considere o seguinte ao planejar identidades de dispositivo:

- Nomes de entidade de usuário e seu formato e domínio
- Exibir nomes
- Descoberta de catálogo de endereços
- Tipos de dispositivo de espaço pessoal versus compartilhado
- Licenciamento atribuído por grupo versus usuário

### <a name="objective-review-conditional-access-policies"></a>Objetivo: Examinar políticas de Acesso Condicional

As políticas de Acesso Condicional do Azure Active Directory são requisitos adicionais que devem ser atendidos antes que um dispositivo possa ser conectado.

Ao planejar sua implantação

- Examine as políticas de Acesso Condicional existentes que podem afetar os telefones e as exibições do Teams. Você pode fazer isso no centro Azure AD Administração usando a ferramenta [What If](/azure/active-directory/conditional-access/what-if-tool) e os [logs de entrada](/azure/active-directory/reports-monitoring/concept-sign-ins)

- Planejar novas regras, se necessário

- Use recursos de Acesso Condicional, como filtros de dispositivo, para aplicar regras a telefones e exibições do Teams.

>[!NOTE]
>Há algumas políticas de Acesso Condicional que os dispositivos Android não dão suporte. Para obter diretrizes e práticas recomendadas, consulte dispositivos Android, consulte as práticas recomendadas de autenticação [para dispositivos Android do Teams](authentication-best-practices-for-android-devices.md).

## <a name="task-4-prepare-your-environment"></a>Tarefa 4: Preparar seu ambiente

### <a name="objective-plan-network-basics"></a>Objetivo: Planejar noções básicas de rede

Os dispositivos e as exibições do Teams Phone exigem acesso à Internet para se conectarem ao Teams e funcionarem conforme o esperado. Para preparar sua rede para implantação, considere o seguinte:

- Sua infraestrutura de rede tem capacidade suficiente? Considere alternar portas, pontos de acesso sem fio e outras coberturas.
- Se você usar VLANs e DHCP, seus escopos serão dimensionados adequadamente?
- Avaliar e testar caminhos de rede de onde os dispositivos são implantados no Microsoft 365. 
- Abra as portas de firewall e as URLs necessárias para o Microsoft 365 de acordo com as diretrizes.
- Examine e teste os requisitos e a configuração do E911 para obter a precisão e a conformidade do local. 
- Evite usar um servidor proxy e otimizar caminhos de mídia para confiabilidade e qualidade.

### <a name="objective-physical-considerations"></a>Objetivo: Considerações físicas

Considere os espaços físicos em que seus telefones e exibições do Teams serão usados.

Os principais aspectos incluem

- **Poder:** Você tem tomadas elétricas suficientes? Se o dispositivo precisar de uma fonte de alimentação externa, quão perto você pode posicioná-lo em uma saída?
- **Posicionamento do dispositivo:** Onde seu dispositivo estará fisicamente? Suportes de mesa de revisão, montagens de parede e outros acessórios do fabricante original do equipamento (OEM).
- **Segurança:** Seu dispositivo precisa ser bloqueado em determinados espaços?
- **Acessibilidade:** O dispositivo atende aos requisitos de acessibilidade de seu usuário primário? Considere onde ele está colocado, comprimento do fio e usabilidade do fone de ouvido ou do fone de ouvido.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Tarefa 5: como você gerenciará dispositivos implantados?

Os telefones e as telas do Teams são gerenciados de dois a três portais do Microsoft 365 e seus respectivos módulos do PowerShell: 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory Administração Center

Usar o Azure AD Administração central para gerenciar

- Todas as tarefas relacionadas à identidade para telefones e exibições do Teams
- Políticas de acesso condicional 
- Redefinições de senha

#### <a name="teams-admin-center"></a>Teams Administração Center

Usar o Centro de Administração Teams para gerenciar

- [Configurações de dispositivo para o Teams](../business-voice/manage-devices.md)
- [Perfis de configuração](device-management.md#use-configuration-profiles-in-teams)
- [Marcação de dispositivo](manage-device-tags.md)
- [Entrada e saída remotas](remote-sign-in-and-sign-out.md)
- Análise de chamadas  
- Firmware
- Solução de problemas e download de logs

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager Administração Center (se você usar o Intune para gerenciamento de dispositivos)

Use o Endpoint Manager Administração Center para gerenciar: 

- Políticas de conformidade do dispositivo
- Restrições de registro
- Identificadores de dispositivo corporativo
- Filtros de dispositivo
